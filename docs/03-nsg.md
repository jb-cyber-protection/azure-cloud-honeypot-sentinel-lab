# Network Security Group Configuration

## Objective

The Network Security Group (NSG) was configured to intentionally expose limited services in order to attract unsolicited internet traffic while maintaining controlled attack surface.

## Inbound Rules

Allowed:

- TCP 22 (SSH)
- TCP 80 (HTTP)

All other inbound traffic is denied by default.

## Rationale

Port 22 (SSH):
Exposed to attract brute-force login attempts and credential spraying attacks.

Port 80 (HTTP):
Exposed to attract automated web scanning, bot traffic, and reconnaissance attempts.

All other ports remain blocked to:

- Minimise unnecessary exposure
- Maintain controlled testing scope
- Reduce risk of unintended compromise

## Security Posture

- No broad "Allow All" rules
- Default DenyAllInbound rule remains active
- Exposure intentionally limited to two monitored services
