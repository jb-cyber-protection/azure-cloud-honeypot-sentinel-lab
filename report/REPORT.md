# Azure Cloud Honeypot & Microsoft Sentinel Lab – Final Report

## Executive Summary

This project deployed an intentionally exposed Linux virtual machine in Microsoft Azure to simulate a real-world internet-facing asset. Authentication and system logs were ingested into Azure Log Analytics and monitored using Microsoft Sentinel.

The objective was to build a production-style cloud security monitoring pipeline, develop custom KQL detections, and analyze real attacker traffic.

---

## Architecture Overview

Internet  
→ Public IP  
→ Honeypot VM (Linux)  
→ Azure Monitor Agent  
→ Log Analytics Workspace  
→ Microsoft Sentinel  
→ Analytics Rules & Workbooks  

---

## Infrastructure Deployed

- 1 Linux VM (vm-honeypot-01)
- Standard public IP (static)
- Network Security Group (SSH + HTTP exposed)
- Log Analytics workspace (law-honeypot-01)
- Microsoft Sentinel enabled
- Custom KQL detection pack (6 detections)
- SOC-style workbook dashboard

---

## Observed Attacker Activity

Within hours of exposure, the honeypot received:

- Repeated SSH brute-force attempts
- Credential spraying attempts against common usernames
- Multiple source IP addresses targeting the VM
- Automated scanning behavior

Common usernames targeted:
- root
- admin
- test
- ubuntu

Attack traffic originated from multiple geographic regions.

---

## Detection Engineering Summary

Six custom KQL detections were developed:

1. SSH brute force from single IP
2. Credential spray (multiple IPs targeting same username)
3. Username enumeration from single IP
4. Off-hours authentication spike
5. New source IP detection
6. Successful SSH login detection

At least two detections were validated using real ingested log data.

---

## Workbook & Monitoring

A Sentinel workbook titled:

Azure Honeypot – Attack Monitoring Dashboard

was created to visualize:

- Authentication failure trends
- Top attacking IPs
- Most targeted usernames
- Successful SSH logins

This mirrors a simplified SOC monitoring view.

---

## Cost Summary

Cost control measures included:

- Single VM deployment
- Auto-shutdown enabled
- No premium services (Firewall/NAT Gateway)
- Limited log ingestion scope

The lab was kept within the planned monthly budget.

---

## Lessons Learned

- Internet-facing VMs receive attack traffic almost immediately.
- Syslog collection requires explicit configuration via Data Collection Rules.
- Detection thresholds must be tuned based on real data volume.
- Microsoft Sentinel integrates seamlessly with Log Analytics for SIEM use cases.
- Cost governance must be implemented before deployment.

---

## Conclusion

This lab demonstrates hands-on capability in:

- Azure infrastructure deployment
- Cloud-native telemetry ingestion
- Microsoft Sentinel SIEM configuration
- KQL detection engineering
- Threat monitoring & analysis
- Cost-aware cloud security operations

The project replicates a realistic enterprise cloud security monitoring workflow.
