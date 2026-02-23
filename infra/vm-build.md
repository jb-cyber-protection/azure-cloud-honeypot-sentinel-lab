# Honeypot VM Deployment

## VM Configuration

Name: vm-honeypot-01  
Region: West Europe  
Size: Standard_D2s_v3  
OS: Ubuntu Server 22.04 LTS  
Authentication: SSH key-based (RSA 4096)

## Networking

Public IP: pip-honeypot-01 (Standard SKU, Static)
Inbound Port Allowed: 22 (SSH)

## Security Configuration

- SSH key authentication only
- Password login disabled
- Boot diagnostics enabled

## Cost Controls

- Auto-shutdown enabled (22:00 daily)
- Single VM deployment
- No additional premium services enabled

## Verification Steps

- VM deployed successfully
- Public IP confirmed
- SSH access validated from MacBook
- whoami returned "azureuser"
