# Resource Governance & Tagging Strategy

## Resource Group

All honeypot resources are deployed inside:

rg-honeypot-sentinel-lab

This ensures:
- Centralized management
- Simplified cost tracking
- One-click cleanup
- Clear project isolation

## Tagging Standard

The following tags are applied to the resource group:

project = honeypot  
environment = lab  
owner = jb-cyber-protection  

These tags allow:
- Cost filtering by project
- Resource organization
- Governance alignment with enterprise practices

## Governance Principles

- All resources must be deployed inside the dedicated resource group.
- No production resources are used.
- Deleting the resource group fully decommissions the lab.
