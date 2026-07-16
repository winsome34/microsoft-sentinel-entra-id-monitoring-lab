# Microsoft Sentinel SIEM Deployment & Microsoft Entra ID Monitoring Lab

## Overview

This project demonstrates the deployment and configuration of Microsoft Sentinel as a cloud-native Security Information and Event Management (SIEM) solution integrated with Microsoft Entra ID. The lab focuses on collecting identity telemetry, validating data ingestion, and performing threat hunting using Kusto Query Language (KQL) within Microsoft Defender.

## Objectives

- Deploy Microsoft Sentinel
- Configure a Log Analytics Workspace
- Integrate Microsoft Entra ID with Microsoft Sentinel
- Collect and monitor identity-related logs
- Validate data ingestion
- Perform threat hunting using KQL
- Build a foundation for incident detection and response

---

## Environment

| Component | Configuration |
|----------|---------------|
| Cloud Platform | Microsoft Azure |
| SIEM | Microsoft Sentinel |
| Identity Provider | Microsoft Entra ID |
| Log Analytics Workspace | LAW-SOC-LAB |
| Resource Group | rg-soc-lab |
| Region | East US |

---

## Technologies Used

- Microsoft Azure
- Microsoft Sentinel
- Microsoft Entra ID
- Microsoft Defender XDR
- Azure Monitor
- Log Analytics Workspace
- Kusto Query Language (KQL)

---

## Project Architecture

```text
Microsoft Entra ID
        │
        ▼
Diagnostic Settings
        │
        ▼
Log Analytics Workspace
        │
        ▼
Microsoft Sentinel
        │
        ▼
Microsoft Defender Portal
        │
        ▼
KQL Threat Hunting
```

---

## Implementation Steps

### Step 1: Configure Log Analytics Workspace

- Used an existing Log Analytics Workspace (`LAW-SOC-LAB`)
- Verified workspace configuration and connectivity

### Step 2: Enable Microsoft Sentinel

- Enabled Microsoft Sentinel on the Log Analytics Workspace
- Confirmed successful deployment

### Step 3: Install Microsoft Entra ID Solution

Installed the Microsoft Entra ID solution from the Sentinel Content Hub, including:

- Data Connector
- Analytics Rule Templates
- Workbooks
- Playbooks

### Step 4: Configure Microsoft Entra ID Data Connector

Successfully connected Microsoft Entra ID to Microsoft Sentinel.

Enabled data sources include:

- Sign-in Logs
- Audit Logs
- Non-Interactive Sign-in Logs
- Service Principal Sign-in Logs
- Risk-related identity tables (where available)

### Step 5: Validate Data Ingestion

Verified that Microsoft Entra ID logs were successfully ingested into Microsoft Sentinel.

### Step 6: Execute KQL Queries

Example query:

```kusto
SigninLogs
| project TimeGenerated,
          UserPrincipalName,
          IPAddress,
          AppDisplayName,
          ResultType,
          ResultDescription
| sort by TimeGenerated desc
| take 20
```

This query retrieves recent Microsoft Entra ID sign-in events for investigation.

---

## Skills Demonstrated

- Microsoft Sentinel deployment
- Microsoft Entra ID monitoring
- Cloud SIEM configuration
- Log ingestion validation
- Identity monitoring
- Kusto Query Language (KQL)
- Microsoft Defender integration
- Security monitoring

---

## Best Practices

- Enable Multi-Factor Authentication (MFA) for privileged accounts.
- Apply the principle of least privilege using Role-Based Access Control (RBAC).
- Configure Microsoft Entra ID Diagnostic Settings to send logs to Microsoft Sentinel.
- Regularly monitor sign-in and audit logs for suspicious activity.
- Use KQL to proactively hunt for identity threats.
- Enable Analytics Rules to automatically generate incidents.
- Monitor privileged role assignments and administrative changes.
- Review Microsoft Secure Score recommendations regularly.
- Validate data connectors and workspace health periodically.
- Test detections using simulated security events.

---

## Future Enhancements

- Create custom Analytics Rules
- Build Microsoft Sentinel Workbooks
- Implement Automation Rules
- Configure Logic Apps Playbooks
- Detect password spray attacks
- Monitor impossible travel events
- Investigate incidents using Microsoft Defender
- Implement User and Entity Behavior Analytics (UEBA)

---

## Screenshots

Include screenshots demonstrating:

- Log Analytics Workspace
- Microsoft Sentinel Overview
- Microsoft Entra ID Data Connector
- Content Hub Installation
- Advanced Hunting
- KQL Query Results
- Analytics Rules
- Workbooks

---

## Learning Outcomes

Through this lab, I gained practical experience deploying Microsoft Sentinel, integrating Microsoft Entra ID, validating identity log ingestion, and performing threat hunting using Kusto Query Language. This project strengthened my understanding of cloud SIEM architecture, identity monitoring, and Microsoft security operations.

---

## Author

**Oni Victor Kehinde**

SOC Analyst | Cloud Security | Microsoft Sentinel | Microsoft Entra ID

- LinkedIn: (https://www.linkedin.com/in/onivictor-cybersecurity/)
- GitHub: https://github.com/winsome34/microsoft-sentinel-entra-id-monitoring-lab/new/main?filename=README.md 
