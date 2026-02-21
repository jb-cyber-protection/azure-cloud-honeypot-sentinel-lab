# Azure Cloud Honeypot + Microsoft Sentinel Lab

This repository contains a real-world Azure cloud security lab using Microsoft Sentinel to monitor an intentionally exposed Linux VM (honeypot). The lab captures unsolicited attacker traffic, ingests logs into Azure Log Analytics, and applies custom KQL detections to identify suspicious authentication patterns and attacker behavior.

## Architecture
Internet → Public IP → Honeypot VM → Log Analytics → Microsoft Sentinel → Detections & Dashboards

See: `docs/00-architecture.md`

## What This Demonstrates
- Azure infrastructure deployment (VM, networking, governance)
- Network Security Group configuration (controlled exposure)
- Cloud logging and telemetry ingestion (Log Analytics)
- SIEM configuration and monitoring (Microsoft Sentinel)
- Detection engineering using KQL (analytics rules + tuning)
- Dashboarding and investigation workflows
- Cost controls and cleanup discipline

## Repository Structure
- `docs/` — build notes, architecture, cost controls, cleanup
- `infra/` — deployment notes (and optional IaC later)
- `detections/kql/` — KQL queries and analytics rule logic
- `dashboards/` — workbook/dashboard exports or screenshots
- `evidence/` — screenshots proving each step worked
- `report/` — final report and findings

## Safety / Ethics
This project is defensive-only. Do not scan or attack systems you do not own. Only observe and analyze traffic reaching resources you deployed.

## Quick Start
1) Complete Issues 1–10 in order.
2) Capture evidence screenshots as you go (store in `evidence/`).
3) Finish with `docs/99-cleanup.md` to remove resources and stop charges.
