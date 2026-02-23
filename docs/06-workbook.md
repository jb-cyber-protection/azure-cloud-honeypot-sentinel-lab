# Azure Honeypot – Attack Monitoring Dashboard

## Overview

This workbook provides a SOC-style monitoring view for the Azure honeypot environment. It visualizes authentication activity, attacker behavior, and high-signal events using Microsoft Sentinel.

The dashboard is designed to mirror a real-world cloud security monitoring workflow.

---

## Workbook Name

Azure Honeypot – Attack Monitoring Dashboard

---

## Purpose

The goal of this workbook is to:

- Visualize SSH brute-force activity
- Identify top attacking IP addresses
- Highlight targeted usernames
- Surface successful SSH logins
- Provide rapid situational awareness for analysts

---

## Panels Included

### 1) SSH Authentication Failures Over Time
Displays failed SSH authentication attempts grouped by time interval.
Used to detect spikes and brute-force bursts.

### 2) Top Attacking IPs (Last 24 Hours)
Ranks source IP addresses by number of failed authentication attempts.
Helps identify persistent or aggressive attackers.

### 3) Top Targeted Usernames
Shows which usernames attackers attempt most frequently.
Useful for detecting credential spraying patterns.

### 4) Successful SSH Logins
Displays successful SSH authentication events.
Acts as a high-signal event for investigation and validation.

---

## Data Source

All panels use:

- Syslog table
- Linux auth/authpriv facility logs
- Azure Monitor Agent ingestion
- Microsoft Sentinel SIEM layer

---

## Detection Value

This workbook provides:

- Rapid visibility into active attack patterns
- Context for detection rule tuning
- Evidence of real-world unsolicited traffic
- Foundation for incident investigation

---

## Analyst Usage

An analyst can use this dashboard to:

- Detect brute-force activity
- Investigate source IP trends
- Monitor login activity
- Identify anomalies in authentication behavior
