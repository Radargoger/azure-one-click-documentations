# Microsoft Azure Sentinel Integration (Bi-Directional)

[cite_start]SOCRadar integrates with Microsoft Azure Sentinel to synchronize incidents and support coordinated investigation across both platforms[cite: 3].

## 🚀 What This Integration Enables
* [cite_start]Centralized monitoring of SOCRadar alarms in Azure Sentinel[cite: 87].
* [cite_start]Continuous alignment between detection and response workflows[cite: 88].
* [cite_start]Consistent incident lifecycle across both platforms[cite: 89].
* [cite_start]Reduced manual tracking between systems[cite: 90].

## 🔄 Bi-Directional Workflow
* [cite_start]SOCRadar alarms are ingested into Azure Sentinel[cite: 5].
* [cite_start]Analysts investigate and manage incidents within Sentinel[cite: 6].
* [cite_start]Status updates in Azure are reflected back into SOCRadar[cite: 7].
* [cite_start]Both platforms maintain a consistent incident state[cite: 8].

## 📋 Prerequisites
* [cite_start]Microsoft Sentinel workspace[cite: 92].
* [cite_start]SOCRadar API Key[cite: 93].
* [cite_start]Company ID[cite: 94].

## ⚙️ Configuration Parameters

### Required Parameters
| Parameter | Description |
| :--- | :--- |
| **WorkspaceName** | [cite_start]Your Sentinel workspace name (e.g., my-sentinel-workspace, NOT the Workspace ID/GUID)[cite: 99]. |
| **SocradarApiKey** | [cite_start]Your SOCRadar API key[cite: 99]. |
| **Company Id** | [cite_start]Your SOCRadar company ID[cite: 99]. |

> [cite_start]**Note:** You can find your Workspace Name in Azure Portal → Log Analytics workspaces → your workspace → Overview → "Name" field[cite: 100].

### Optional Parameters
| Parameter | Default | Description |
| :--- | :--- | :--- |
| **PollingIntervalMinutes** | 5 | [cite_start]How often to check for alarms (1-60 min)[cite: 102]. |
| **InitialLookbackMinutes** | 600 | [cite_start]First run lookback (default: 10 hours)[cite: 102]. |
| **EnableAuditLogging** | true | [cite_start]Log operations to Log Analytics[cite: 102]. |
| **EnableAlarmsTable** | true | [cite_start]Store alarms in SOCRadar_Alarms_CL table for analytics[cite: 102]. |
| **EnableWorkbook** | true | [cite_start]Deploy SOCRadar Analytics Dashboard[cite: 102]. |
| **TableRetentionDays** | 365 | [cite_start]Data retention (30-730 days)[cite: 102]. |

## 🛠️ What Gets Deployed
* [cite_start]**SOCRadar-Alarm-Import**: Imports alarms from SOCRadar as Sentinel incidents[cite: 104].
* [cite_start]**SOCRadar-Alarm-Sync**: Syncs closed incidents back to SOCRadar[cite: 105].
* [cite_start]**SOCRadar_Alarms_CL**: Custom table for alarm analytics (if EnableAlarmsTable=true)[cite: 106].
* [cite_start]**SOCRadar Analytics Dashboard**: Workbook with charts and tables (if EnableWorkbook=true)[cite: 107].
* [cite_start]**SOCRadarAuditLog_CL**: Audit log table (if EnableAuditLogging=true)[cite: 108].
* **Data Collection Endpoint & Rules**: For data ingestion[cite: 109].

## 📊 Dashboard & Analytics
After configuration, an Azure Workbook is created to monitor the SOCRadar integration[cite: 70]. The dashboard provides operational visibility into:
* [cite_start]Alarm ingestion and synchronization activity[cite: 72].
* [cite_start]Severity and status distribution[cite: 81].
* Alarm trends over time[cite: 82].
* [cite_start]Top alarm categories across SOCRadar modules[cite: 83].
* [cite_start]Recent alarm imports and audit events[cite: 84].

## ⏳ Post-Deployment
[cite_start]Logic Apps are configured to start 3 minutes after deployment to allow Azure role propagation[cite: 134]. [cite_start]No manual action required - they will start automatically[cite: 135].

## 📞 Support
[cite_start]Support: integration@socradar.io [cite: 140]
