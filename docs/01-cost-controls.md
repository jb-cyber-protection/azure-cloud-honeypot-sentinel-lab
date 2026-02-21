# Cost Controls & Budget Governance

## Monthly Budget

A £30 monthly Azure budget has been configured to prevent unexpected spend during this lab.

Alert thresholds:
- 50% (£15)
- 80% (£24)
- 100% (£30)

Email notifications are enabled for all thresholds.

## Cost Control Strategy

To maintain predictable spend:

- Only one Linux VM will be deployed.
- Auto-shutdown will be enabled on the VM.
- No additional premium networking services (NAT Gateway, Azure Firewall).
- Log retention will be limited.
- Microsoft Sentinel ingestion volume will be monitored.

## Kill Switch

If costs approach threshold:

1. Stop the VM immediately.
2. Review Log Analytics ingestion volume.
3. Delete the entire Resource Group to stop all charges.

Deleting the resource group removes:
- VM
- Disk
- Public IP
- Log Analytics
- Sentinel
- All associated resources

This guarantees billing stops.
