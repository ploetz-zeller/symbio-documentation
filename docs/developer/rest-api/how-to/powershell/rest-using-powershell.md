# Symbio REST access using Powershell

## Pre-requisites

- Authentication token that is active and valid
- Required parameters: 
	- Server name
	- Storage collection name
	- Storage name
	- REST authentication token

## Executing a REST command using Powershell
The Invoke-RestMethod cmdlet sends HTTP and HTTPS requests to Representational State Transfer (REST) web services that returns richly structured data.

PowerShell formats the response based to the data type. 

For more information please have a look at the documentation on Microsoft: [Microsoft documentation](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/invoke-restmethod?view=powershell-6)

## Example script to get released processes or documents
```powershell
	function Fetch_Data {
		[CmdletBinding()]
		# Parameters for collecting data
		param(
			# Server address parameter
			[Parameter(Mandatory=$true, HelpMessage="Please enter the server address!", Position=1)]
			[ValidateNotNullOrEmpty()]
			[string]$address,

			# Collection name parameter
			[Parameter(Mandatory=$true, HelpMessage="Please enter the collection name!", Position=2)]
			[ValidateNotNullOrEmpty()]
			[string]$collection,

			# Storage name parameter
			[Parameter(Mandatory=$true, HelpMessage="Please enter the storage name!", Position=3)]
			[ValidateNotNullOrEmpty()]
			[string]$storage,

			# REST API Token parameter
			[Parameter(Mandatory=$true, HelpMessage="Please enter the REST API token!", Position=4)]
			[ValidateNotNullOrEmpty()]
			[string]$token,
		
			# Export data to file parameter. False is default. Parameter is not mandatory
			[Parameter(Mandatory=$false, HelpMessage="Export result in json file?", Position=5)]
			[bool]$fileExport = $false
		)

		Process
		{
			try
			{
				$params = @{
				    Uri = "https://$($address)/$($collection)/$($storage)/_api/rest/facets/processes/views/lastReleasedProcesses/elements"
				    Headers = @{ 'symbio-auth-token' =  $token; 'api-version' = '2.0' }
				    Method = 'GET'
				    ContentType = 'application/json'
				}

				# Response of the API request. Data will be taken with depth of 10 levels
				$result = Invoke-RestMethod @params | ConvertTo-Json -Depth 10

				# Converting from JSON to table data (Easier for customization of fields and ordering)
				$tableResult = $result | ConvertFrom-Json

				$valuesResult = ''

				# All data is putting to one table object
				$hash = @{}
				foreach($row in $tableResult.PSObject.Properties){
				if($row.Value -is [int]) { continue }
					$hash[$row.Name] = $row.Value
					$valuesResult = $hash[$row.Name]
				}

				$arrayOfElements = New-Object System.Collections.ArrayList

				# Mapping all data to fields which will be shown to the final data
				foreach($element in $valuesResult)
				{
					$parameters = [ordered]@{
						Name = $element.attributes.Name
						State = $element.attributes.state1
						Type = $element.type
						LinkAddress = $element.attributes.links.'127'.fullAddress
						LinkTitle = $element.attributes.links.'127'.title
					} 
					[void]$arrayOfElements.Add($parameters)
				}

				# Checking if the data is not empty
				if($arrayOfElements.Count -lt 1)
				{
					Write-Host "Response returned 0 elements. Please check input parameters, and try again..."
				}
				else
				{
                    # If the data isn't empty, it's checking if parameter export to file is True
                    $file_export = $fileExport
                    $today = Get-Date -Format yyyy-MM-ddTHH-mm-ss-ff
                    if($file_export -eq $true) 
                    {
                        $arrayOfElements | ConvertTo-Json | Out-File ".\processes$($today).json"
                    }
                    else { $arrayOfElements | ConvertTo-Json }
				}
			}
			catch [System.Management.Automation.CommandNotFoundException]
			{
				Write-Host "Command not found. Please execute again..."
				Write-Host $_.ScriptStackTrace
			}
			catch [System.Net.WebException],[System.SystemException]
			{
				Write-Host "Web error. Please check input parameters and try again."
				Write-Host $_.ScriptStackTrace
			}
		}
	}
```
## Example output

The script can output the json directly, or create a file with the same content, depending on the $fileExport parameter.

```json
	[
		{
			"Name":  {
						 "1033":  "Sub Process 1",
						 "1031":  "Teilprozess 1"
					 },
			"State":  null,
			"Type":  "subProcess",
			"LinkAddress":  null,
			"LinkTitle":  null
		},
		{
			"Name":  {
						 "1033":  "Sub Process 2",
						 "1031":  "Teilprozess 2"
					 },
			"State":  "InProgress",
			"Type":  "subProcess",
			"LinkAddress":  null,
			"LinkTitle":  null
		},
		{
			"Name":  {
						 "1033":  "Sub Process 3",
						 "1031":  "Teilprozess 3"
					 },
			"State":  null,
			"Type":  "subProcess",
			"LinkAddress":  null,
			"LinkTitle":  null
		},
	]
```

## How to call the Powershell script
You can save the script in a ****.ps file.
The parameters are:
1. Server name
1. Storage collection name
1. Storage name
1. Authentication token
1. File export (true/false) (Optional parameter)

### Running it with user input
When running the the script file without parameters, the script will prompt you to enter the required values. Using !? at that point will give you a hint on the required value.

### Running inline
You can also run the script and provide the required parameters at runtime.
Example:
```
	run.ps -address <servername> -collection <collection-name> -storage <storage-name> -token <auth-token> -dataType 1 -fileExport false
```