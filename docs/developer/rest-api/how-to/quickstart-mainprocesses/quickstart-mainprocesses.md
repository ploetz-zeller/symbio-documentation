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

### Get help
To create objects according to the Symbio Rest response with corresponding properties, the JSON key should be known. A `/help` at the end of the Uri will give you a detailed answer, which will show the possible keys.

```c#
Uri symbioUri = new Uri("https://Server/Collection/Database/_api/rest/facets/processes/views/tree/elements/Origin Key of Category/help");
```

The `key` element would be a possible property of the objects or another object with its own properties.

For example, here is an excerpt from the help response in JSON format:

```json
{
    "key": "name",
    "displayNames": {
        "1031": "Name",
        "1033": "Name"
    },
    "descriptions": {
        "1031": "Name des Elements.",
        "1033": "Name of element."
    },
    "tooltips": {
        "1031": "Name des Elements.",
        "1033": "Name of element."
    },
    "attribute": {
        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral,                  PublicKeyToken=b77a5c561934e089",
        "dataType": "MultiLineText",
        "isInvariantCulture": false
    }
},
{
    "key": "typeName",
    "displayNames": {
        "1031": "Typ",
        "1033": "Type"
    },
    "descriptions": {
        "1031": "",
        "1033": ""
    },
    "tooltips": {
        "1031": "",
        "1033": ""
    }
},
{
    "key": "version",
    "displayNames": {
        "1031": "Version",
        "1033": "Version"
    },
    "descriptions": {
        "1031": "",
        "1033": ""
    },
    "tooltips": {
        "1031": "",
        "1033": ""
    },
    "attribute": {
        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
        "dataType": "SingleLineText",
        "isInvariantCulture": true
    }
},
{
    "key": "state1",
    "displayNames": {
        "1031": "Status",
        "1033": "State"
    },
    "descriptions": {
        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
        "1033": "Current phase of an element's lifecycle."
    },
    "tooltips": {
        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
        "1033": "Current phase of an element's lifecycle."
    },
    "attribute": {
        "type": "Symbio.Base.Framework.Method.ISelectableValue, Symbio.Base.Framework, Version=0.0.1815.0, Culture=neutral, PublicKeyToken=null",
        "dataType": "SelectionValue",
        "isInvariantCulture": true,
        "selectableValues": [
        {
            "key": "show",
            "displayNames": {
                "1031": "Status",
                "1033": "State"
            },
            "descriptions": {
                "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                "1033": "Current phase of an element's lifecycle."
            },
            "tooltips": {
                "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                "1033": "Current phase of an element's lifecycle."
            }
        },
        {
            "key": "hide",
            "displayNames": {
                "1031": "Status",
                "1033": "State"
            },
            "descriptions": {
                "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                "1033": "Current phase of an element's lifecycle."
            },
            "tooltips": {
                "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                "1033": "Current phase of an element's lifecycle."
            }
        }]
    }
},
```
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

# FAQ's




Impressum
=======================================================================================================

 **publisher**

 Ploetz + Zeller GmbH

 Einsteinring 41-43

 85609 München

 Tel.: +49 89 890635 – 0

 Fax: +49 89 890635 – 55

 E-Mail: info@p-und-z.de  |
|-------------------------|

| **IMPRESSUM**                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|
Ploetz + Zeller GmbH accepts no liability for the correctness and completeness of the presentation/image in the document. The described and possible functionalities of the software refer to the respective version status. Customer-specific adaptations are not included. The information in this document is subject to change at any time. Ploetz + Zeller GmbH is not obliged to inform about the updates of the document.


 This documentation as well as all contributions, representations and illustrations contained therein are protected by copyright. Any use not expressly permitted by copyright law requires the prior consent of Ploetz + Zeller GmbH. This applies in particular to reproductions, adaptations, translations, microfilming as well as storage and processing in electronic systems.

 Ploetz + Zeller GmbH regards the information, knowledge and illustrations contained in this documentation as its sole property. The documentation or the information, knowledge and illustrations contained therein may not be made available, published or otherwise disseminated to third parties, either in whole or in part, directly or indirectly, without the prior written consent of Ploetz + Zeller GmbH.
                                                                                                                                                                                                                                                                                                                                                                                                         Ploetz + Zeller GmbH reserves the right to assert all relevant rights, in particular in the event of patents being granted. The handing over of the documentation does not create any claim to a license or use.

 Subject to technical modifications. Product names used are trademarks or registered trademarks of their respective owners.

 Symbio® is a registered trademark of PLOETZ + ZELLER GmbH, Munich.                                                                                                                                                                                                                                                                                                                                                                                                     |


| Ploetz + Zeller GmbH

 Einsteinring 41-43

 85609 München                                              |
| Phone: +49 89 890635 – 0

 Fax: +49 89 890635 – 55

 E-Mail: <info@p-und-z.de>

 ©2018 Ploetz + Zeller GmbH                                 |


