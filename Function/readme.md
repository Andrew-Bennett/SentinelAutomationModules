# STAT API Function

## Description
This Azure function will be used by some of the Sentinel automation modules to assist in data processing tasks that are not easily done inside a Logic app.  This function provides capabilities such as:

* Sorting an Array of Objects by one or more properties of the objects

## Trigger Parameters

Trigger name: **processdata**

The following properties are required for all actions performed by this function:

|Property|Description|
|---|---|
|action|The data operation to execute on the data array|
|data|This array or object contains the data to be processed|

### Supported Actions

#### sortObjectArray

This action will sort an array of JSON objects by one or more sort keys.

Action Specific Properties:

|Property|Mandatory|Description|
|---|---|---|
|sortorder|False|asc (ascending) or desc (descending) search order. Default is ascending|
|sortkeys|True|An array of keys to sort the data by. (Ex. ["id","name"] will sort first by id, and then name|

#### changePropertyCase

This action will change the case of properties in a JSON object

Action Specific Properties:

|Property|Mandatory|Description|
|---|---|---|
|properties|True|An array of properties in the JSON object to change the casing on|
|case|True|The type of case change operation you want to perform (upper, lower, or title)|

## Return Properties

|Property|Description|
|---|---|
|{} or []|JSON Object or Array containing the processed data|

## Sample Input Body

```
{
    "sortorder": "asc",
    "sortkeys": ["id","name"],
    "action": "sortObjectArray",
    "data": [
        {
            "id": 30,
            "name": "entry 30"
        },
        {
            "id": 5,
            "name": "entry 5b"
        },
        {
            "id": 5,
            "name": "entry 5a"
        }
    ]
}
```

## Sample Return

```
[
    {
        "id": 5,
        "name": "entry 5a"
    },
    {
        "id": 5,
        "name": "entry 5b"
    },
    {
        "id": 30,
        "name": "entry 30"
    }
]
```

## Deployment

Deployment of this function is included with the main Sentinel Triage AssistanT  [deployment template](/Deploy/readme.md).