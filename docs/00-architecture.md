# Architecture Overview

## Purpose
This lab simulates a real-world cloud security monitoring environment in Microsoft Azure. An intentionally exposed Linux VM acts as a honeypot to attract unsolicited internet traffic. Logs are ingested into Log Analytics and monitored with Microsoft Sentinel using KQL detections.

## High-Level Data Flow
Internet → Public IP → Honeypot VM → Log Analytics Workspace → Microsoft Sentinel → Analytics Rules / Alerts → Dashboards / Investigation

## Components

### 1) Honeypot VM (Linux)
A small Azure Linux VM deployed with a public IP. It is deliberately exposed on a limited set of ports to attract scanning and authentication attempts.

### 2) Network Security Group (NSG)
Controls inbound exposure. Only selected inbound ports are allowed; all other inbound traffic is blocked by default.

### 3) Log Analytics Workspace
Central log storage and query layer. VM logs are ingested here and queried using KQL.

### 4) Microsoft Sentinel
SIEM layer on top of the Log Analytics workspace. Used to:
- Create analytics rules (scheduled KQL detections)
- Generate incidents/alerts
- Build workbooks/dashboards for visibility

## Scope (Issue-Level)
- Deploy 1 Linux VM honeypot with controlled exposure
- Ingest authentication/security telemetry into Log Analytics
- Enable Microsoft Sentinel and build KQL detections
- Create dashboards/workbooks for attacker activity
- Produce a final report and cleanup guide

## Out of Scope
- Attacking or scanning systems you do not own
- Multi-VM deployments or enterprise networking (NAT Gateway/Azure Firewall)
- Storing sensitive data; public evidence should be redacted where appropriate
