# splunk-sysmon-threat-hunting

## Overview
This project demonstrates a practical implementation of a security monitoring and threat hunting pipeline using Splunk Enterprise.
The lab focuses on analyzing high-fidelity endpoint telemetry provided by Windows Sysmon and the Aurora Incident Response Agent. 
The goal was to build interactive dashboards that translate raw, unstructured event data into actionable security insights, focusing on process forensics and registry integrity.

## Features
- **Automated Log Parsing:** Used rex to extract custom fields from raw data where standard CIM mapping was unavailable.
- **Process Access Auditing:** Monitoring of GrantedAccess rights and CallTrace to detect potential credential dumping (e.g., LSASS access).
- **Behavioral Analysis:** Dashboards tracking the Top 10 source images and suspicious process hierarchies.
- **Event Distribution:** Real-time breakdown of Sysmon EventIDs (1, 7, 11, 12, 13) to monitor system health and security posture.

## Tech Stack
- Splunk Enterprise
- Windows Sysmon & Aurora Agent
- SPL (Search Processing Language)
- Publicly available Sysmon datasets (Security Research Datasets via GitHub)

## Usage
1. Ingest the dataset:
   Upload your Sysmon/Aurora logs to a dedicated index (e.g., `threat_lab_sysmon`).
2. Install parsing Add-ons:
   Install the `Splunk Add-on for Microsoft Windows` to ensure proper field extraction and CIM mapping.
3. Execute Analysis:
   Navigate to **Search & Reporting** and use the provided SPL queries to hunt for threats.
4. Build Dashboards:
   Create new dashboard panels and paste the SPL queries to visualize event distributions and forensic data.
