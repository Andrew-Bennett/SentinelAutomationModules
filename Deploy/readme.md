# Deploy the full solution

This template is used to deploy or update the Microsoft Sentinel Triage AssistanT (STAT) solution.

## Deployment Considerations

The Microsoft Sentinel Triage AssistanT (STAT) creates a series of Logic Apps, API connections, and a Logic Apps Custom Connector.  To use the STAT solution these items must be deployed in the same subscription and datacenter region as the Microsoft Sentinel playbooks which will use the solution.  In the event you would like to use STAT from multiple subscriptions or datacenter regions, a deployment of STAT will need to be created in each location.

#### Deploying Multiple Copies of STAT

In most cases it is only necessary to deploy STAT a single time, but in some circumstances such as when it needs to be available from multiple subscriptions or in multiple data center regions the solution may need to be deployed more than once.  If you must deploy STAT in multiple subscriptions or multiple datacenters it is recommended to use the advanced setup option and choose unique names for each logic app.  Using the same names in multiple deployments may result in issues with the GrantPermissions.ps1 script as the script presently relies on finding the logic apps by name.

## Upgrade Considerations

To upgrade the Microsoft Sentinel Triage AssistanT you can simply deploy the solution again, using the same settings as your original deployment.  This will update all of the STAT components but will maintain any existing connections to other logic apps you have a built and you will not be required to reassign the permissions as they will also be maintained.  When upgrading an advanced mode deployment, it is important that you use the same module names as the original deployment, otherwise new logic apps will be created.

## Quick Deployment

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fbriandelmsft%2FSentinelAutomationModules%2Fmain%2FDeploy%2Fazuredeploy.json/createUIDefinitionUri/https%3A%2F%2Fraw.githubusercontent.com%2Fbriandelmsft%2FSentinelAutomationModules%2Fmain%2FDeploy%2FcreateUiDefinition.json)

## Post Deployment

* Run [GrantPermissions.ps1](GrantPermissions.ps1) to grant the necessary API and RBAC permissions to the logic apps deployed by this template.
