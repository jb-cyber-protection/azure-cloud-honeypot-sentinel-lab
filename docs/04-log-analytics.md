# Log Analytics Workspace & Telemetry Ingestion

## Workspace Details

Name: law-honeypot-01  
Region: West Europe  
Pricing Tier: Pay-as-you-go  

The Log Analytics workspace is used as the central log store for the honeypot environment.

## Agent Configuration

The Azure Monitor Agent (AMA) was enabled on:

vm-honeypot-01

A Data Collection Rule (DCR) was configured to collect:

- Syslog (Facilities: auth, authpriv)
- Heartbeat

## Verification

Log ingestion was verified using the following queries:

### Heartbeat Check
Heartbeat
| take 10


This confirms the VM is actively reporting to Azure Monitor.

### Syslog Authentication Logs
Syslog
| where Facility in ("auth","authpriv")
| order by TimeGenerated desc
| take 20


This confirms SSH login activity is being ingested.

## Purpose

This telemetry enables:

- Monitoring authentication attempts
- Detecting brute-force behavior
- Tracking suspicious login activity
- Feeding data into Microsoft Sentinel for SIEM detection

## Status

Log ingestion successfully validated.
