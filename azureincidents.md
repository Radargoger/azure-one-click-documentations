# Microsoft Azure Sentinel Incident/Alert Integration 

SOCRadar integrates with Microsoft Azure Sentinel to synchronize incidents and support coordinated investigation across both platforms.

## 🚀 What This Integration Enables
*Centralized monitoring of SOCRadar alarms in Azure Sentinel.
*Continuous alignment between detection and response workflows.
*Consistent incident lifecycle across both platforms.
*Reduced manual tracking between systems.

## 🔄 Bi-Directional Workflow
*SOCRadar alarms are ingested into Azure Sentinel.
*Analysts investigate and manage incidents within Sentinel.
*Status updates in Azure are reflected back into SOCRadar.
*Both platforms maintain a consistent incident state.

## 📋 Prerequisites
*Microsoft Sentinel workspace[cite: 92].
*SOCRadar API Key[cite: 93].
*Company ID[cite: 94].

## ⚙️ Configuration Parameters

### Required Parameters
| Parameter | Description |
| :--- | :--- |
| **WorkspaceName** |Your Sentinel workspace name (e.g., my-sentinel-workspace, NOT the Workspace ID/GUID). |
| **SocradarApiKey** |Your SOCRadar API key. |
| **Company Id** |Your SOCRadar company ID. |

>**Note:** You can find your Workspace Name in Azure Portal → Log Analytics workspaces → your workspace → Overview → "Name" field.

### Optional Parameters
| Parameter | Default | Description |
| :--- | :--- | :--- |
| **PollingIntervalMinutes** | 5 |How often to check for alarms (1-60 min). |
| **InitialLookbackMinutes** | 600 |First run lookback (default: 10 hours). |
| **EnableAuditLogging** | true |Log operations to Log Analytics. |
| **EnableAlarmsTable** | true |Store alarms in SOCRadar_Alarms_CL table for analytics. |
| **EnableWorkbook** | true |Deploy SOCRadar Analytics Dashboard. |
| **TableRetentionDays** | 365 |Data retention (30-730 days). |

## 🛠️ What Gets Deployed
***SOCRadar-Alarm-Import**: Imports alarms from SOCRadar as Sentinel incidents.
***SOCRadar-Alarm-Sync**: Syncs closed incidents back to SOCRadar.
***SOCRadar_Alarms_CL**: Custom table for alarm analytics (if EnableAlarmsTable=true).
***SOCRadar Analytics Dashboard**: Workbook with charts and tables (if EnableWorkbook=true).
***SOCRadarAuditLog_CL**: Audit log table (if EnableAuditLogging=true).
* **Data Collection Endpoint & Rules**: For data ingestion.

## 📊 Dashboard & Analytics
After configuration, an Azure Workbook is created to monitor the SOCRadar integration. The dashboard provides operational visibility into:
*Alarm ingestion and synchronization activity.
*Severity and status distribution.
* Alarm trends over time.
*Top alarm categories across SOCRadar modules.
*Recent alarm imports and audit events.

## ⏳ Post-Deployment
Logic Apps are configured to start 3 minutes after deployment to allow Azure role propagation[.No manual action required - they will start automatically.

## 📞 Support
Support: integration@socradar.io
