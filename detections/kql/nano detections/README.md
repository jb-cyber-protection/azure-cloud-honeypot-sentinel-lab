# Detection Pack (KQL)

This folder contains KQL queries used to detect suspicious activity against the Azure honeypot VM.

Notes:
- Queries are designed for Linux Syslog ingestion via Azure Monitor Agent (AMA).
- Most detections focus on SSH brute force, credential spraying patterns, and unusual spikes.
- Tuning guidance is included in each query file.

Validation:
- At least two detections are validated using real ingested log data (see evidence screenshots).
