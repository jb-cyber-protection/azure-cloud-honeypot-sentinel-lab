# Microsoft Sentinel Setup

## Workspace

Sentinel was enabled on the existing Log Analytics workspace:

law-honeypot-01

## SIEM Configuration

Microsoft Sentinel provides:

- Centralized log analysis
- Detection rule creation
- Incident management
- Hunting queries
- Dashboards and workbooks

## Data Flow

vm-honeypot-01  
→ Azure Monitor Agent  
→ Log Analytics Workspace  
→ Microsoft Sentinel  

## Verification

Sentinel was verified by:

- Running Syslog queries in Sentinel Logs
- Confirming authentication logs were visible
- Confirming Azure Monitor Agent connector status

## Purpose

Sentinel acts as the SIEM layer for:

- Brute-force detection
- Suspicious login monitoring
- Incident investigation
- Detection engineering using KQL
