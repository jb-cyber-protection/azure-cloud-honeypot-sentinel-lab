# Cleanup Procedure

## Purpose

To fully decommission the honeypot lab and stop all Azure billing.

---

## Steps

1. Navigate to Azure Portal.
2. Go to Resource Groups.
3. Select:

rg-honeypot-sentinel-lab

4. Click Delete Resource Group.
5. Type the resource group name to confirm.
6. Confirm deletion.

---

## Resources Removed

Deleting the resource group removes:

- Virtual Machine
- OS Disk
- Public IP
- Network Security Group
- Log Analytics Workspace
- Microsoft Sentinel instance
- Data Collection Rules
- All associated components

---

## Verification

After deletion:

- Confirm resource group no longer exists.
- Check Cost Management → ensure no active billable resources remain.
- Verify no running virtual machines in subscription.

---

## Important

Always delete the resource group when the lab is complete to prevent ongoing charges.

