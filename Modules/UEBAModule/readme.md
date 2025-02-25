# Get-UEBAInsights

## Description
This module will check the incident account entities to see if there are any User Entity Behavior Analytics events with an investigation priority.

## Suported Entity Types
* Account

## Trigger Parameters

|Parameter|Expected Values|Description|
|---|---|---|
|AddIncidentComments|Yes/No|When set to yes, the results of the query will be added to the Sentinel Incident Comments|
|Base Module Body|Body (dynamic content)|The Body should be selected from the Dynamic content of the Base-Module response|
|LookbackInDays|1-90|This defines how far back to look through the UEBA tables in Sentinel|
|MinimumInvestigationPriority|1-10|Only BehaviourAnalytics records with an InvestirgationPriority of >= this value will be considered|

## Return Properties

|Property|Description|
|---|---|
|AllEntityEventCount|Count of all related BehaviorAnalytics records|
|AllEntityInvestigationPriorityAverage|Average investigation priority of all related BehaviorAnalytics records|
|AllEntityInvestigationPriorityMax|Maximum investigation priority of all related BehaviorAnalytics records|
|AllEntityInvestigationPrioritySum|Sum of investigation priority of all related BehaviorAnalytics records|
|DetailedResults|An array of UEBA investigration priority values by UserPrincipalName|
|InvestigationPrioritiesFound|true if any investigation priorities are found in all related BehaviorAnalytics records, otherwise false|
|ModuleName|The internal Name of the Playbook|

## Sample Return

```
{
  "AllEntityEventCount": 222,
  "AllEntityInvestigationPriorityAverage": 4.031073446327683,
  "AllEntityInvestigationPriorityMax": 5,
  "AllEntityInvestigationPrioritySum": 899,
  "DetailedResults": [
    {
      "InvestigationPrioritySum": 180,
      "InvestigationPriorityAverage": 4,
      "InvestigationPriorityMax": 4,
      "EventCount": 45,
      "UserPrincipalName": "user1@contoso.com"
    },
    {
      "InvestigationPrioritySum": 719,
      "InvestigationPriorityAverage": 4.062146892655368,
      "InvestigationPriorityMax": 5,
      "EventCount": 177,
      "UserPrincipalName": "user2@contoso.com"
    }
  ],
  "InvestigationPrioritiesFound": true,
  "ModuleName": "UEBAModule"
}
```

## Deployment

To deploy the Sentinel Triage AssistanT visit the [deployment documentation](/Docs/deployment.md).
