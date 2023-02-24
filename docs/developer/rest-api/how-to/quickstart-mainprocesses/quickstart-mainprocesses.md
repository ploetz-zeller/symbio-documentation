---
uid: qsMainProcesses
---
<!--[Reference](xref:QSMainProcesses)
-->
| Status: March 2018   | ©2018 Ploetz + Zeller GmbH   |
|--------------------|------------------------------|


# Quickstart

## Get all released main processes by code

### New Project

In this example, a post request is made in the context of a C# console application, which returns JSON as the result. This JSON can be converted into objects and reused as required.
<!--
> [!NOTE]

> [!WARNING]

> [!IMPORTANT]

> [!Caution]
-->
!!! info
    A Post Request is required at the beginning. Here is an example:

```c#
private static Facets SendPost(Uri baseUri, string requestUri = null)
{
    using (WebRequestHandler handler = new WebRequestHandler())
    {
        using (HttpClient hc = new HttpClient(handler))
        {
            if (!string.IsNullOrEmpty(requestUri))
                hc.BaseAddress = baseUri;

            hc.DefaultRequestHeaders.Add("symbio-auth-token", "token key");
            HttpResponseMessage hrm = hc.PostAsync(string.IsNullOrEmpty(requestUri) ? baseUri.AbsoluteUri : requestUri, null).Result;
            hrm.EnsureSuccessStatusCode();
            string returnString = hrm.Content.ReadAsStringAsync().Result;

            Facets facets = JsonConvert.DeserializeObject<Facets>(returnString, new JsonSerializerSettings() { Converters = new[] { new KeyValuePairConverter() } });

            return facets;
        }
    }
}
```
This example also shows a token that you need to be authenticated. It is appended to the request header.
```c#
hc.DefaultRequestHeaders.Add("symbio-auth-token", "token key");
```
### Add or create new Token
The above mentioned token is created in Symbio by an administrator. For more information see [Authentication mit Tokens](xref:authtoken)
### Build Uri
The construction of all valid uris can be found in the Reference category.This example we starts with an overview of all facets. A request is sent and JSON creates a new faceted object from the response.

The object:
```c#
internal class Facets
{
    public int Count { get; set; }
    public List<Values> Values { get; set; }
}
```
Deserializing the response string:
```c#
Facets facets = JsonConvert.DeserializeObject<Facets>(returnString, new JsonSerializerSettings  (){ Converters = new[] { new KeyValuePairConverter() } });
```
Due to the Symbio JSON structure, it is important to create objects for different layers during deserialization. In this example, the primary goal should be the main process level.

The target Uri contains the current layer and its child elements. Here is an example for the category `Management Processes` where all child elements are listed:
```c#
Uri symbioUri = new Uri("https://Server/Collection/Database/_api/rest/facets/processes/views/tree/elements/Origin Key of Category/");
```
Facets contain processes, processes contain views and views contain elements.

Objects must be created for each layer. For example:
```c#
internal class Values
{
    public string Id { get; set; }
    public string Type { get; set; }
    public Attributes Attributes { get; set; }
    public List<Children> Children { get; set; }
    public List<Content> Content { get; set; }
}

internal class Attributes
{
    public Dictionary<int, string> Name { get; set; }
    public Dictionary<int, string> State1 { get; set; }
}

internal class Children
{
    public string Id { get; set; }
    public string VersionId { get; set; }
    public string Type { get; set; }
    public string ExpandUri { get; set; }
}

internal class Content
{
    public string Id { get; set; }
    public string VersionId { get; set; }
    public string ExpandUri { get; set; }
}
```
The Facets class contains the list of values. The values contain a list of subobjects and attribute objects. In this way, all properties can be addressed and used separately after deserialization, for example for filtering.

### Filter on client

Finally, an example of how all this information is combined to use the objects and their properties. As a reminder, the goal was to keep and list main processes in released status. A request is made for each level, so that you get all the main processes under all categories. From this set, only the processes with the value `released` are then output in the attribute `state1` of the process.

```c#
private static void Main(string[] args)
{
    Uri symbioUri = new Uri("https://Server/Collection/Database/_api/rest/facets/");

    Facets rootsElements = SendPost(symbioUri, "processes/views/tree/elements/");
    foreach (var child in rootsElements.Values.FirstOrDefault(x => x.Type == "processHouse").Children)
    {
        Facets processeContainers = SendPost(new Uri(child.ExpandUri));

        Console.WriteLine(processeContainers.Values.First().Attributes.Name.First().Value);
        if (processeContainers.Values.First().Content != null)
        {
            foreach (var process in processeContainers.Values.First().Content)
            {
                Facets processes = SendPost(new Uri(process.ExpandUri));

                if (processes.Values.First().Attributes.State1.First().Value == "released")
                {
                    Console.WriteLine("     " + processes.Values.First().Attributes.Name.First().Value);
                }
            }
        }
    }
    Console.Read();
}
```

#### Errors

Read more here: [Rest API error handling](xref:error)
