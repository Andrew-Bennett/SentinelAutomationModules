# Automation Modules Home

Automation Modules make it easier to perform routine tasks by using a common set of callable Logic Apps

## Available Modules

* Base
* Azure Active Directory Risks
* File Insights
* Microsoft Cloud App Security
* Microsoft Defender for Endpoint
* Office 365 Out of Office
* Microsoft Sentinel Related Alerts
* Microsoft Sentinel User Entity Behavior Analytics
* Microsoft Sentinel Watchlists

### Base Module

The Base module processes incident data and prepares it for consumption by other modules.  This includes enriching entity data with Azure AD lookups and IP data with Geo location information.

### Azure Active Directory Risks

Module Description

### File Insights

Module Description

### Microsoft Cloud App Security

Module Description

### Microsoft Defender for Endpoint

Module Description

### Office 365 Out of Office

The Out Of Office module takes user entity data and determines if the user has an Out of Office message set on their Office 365 mailbox.

### Microsoft Sentinel Related Alerts

The Related Alerts module takes the incident entity data and determines if other alerts about those same entities exist in Azure Sentinel within a specified timeframe.

### Microsoft Sentinel User Entity Behavior Analytics

The UEBA module allows you to take user entity data and lookup those users in the BehaviorAnalytics table to identity activities performed by the user that deviate from their previous patterns of behavior.

### Microsoft Sentinel Watchlists

The Azure Sentinel Watchlists module allows you to compare entity data from an incident against a watchlist to determine if that entity is present.  This supports watchlists containing columns with UserPrincipalNames, IP Addresses, or CIDR address blocks.