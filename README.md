# ️ SOC Week 2: SIEM Threat Detection with Splunk

## **Project Overview**
This repository documents my Week 2 SOC Analyst training, focusing on deploying Splunk Enterprise, ingesting Linux authentication logs, and writing SPL (Search Processing Language) queries to detect suspicious activity.

## **✅ What I Accomplished**
- **Deployed Splunk Enterprise** on an Ubuntu virtual machine.
- **Ingested and parsed** `/var/log/auth.log` for security monitoring.
- **Wrote custom SPL queries** to analyze logs and identify potential threats.
- **Created visualizations** to track event timelines and host anomalies.

## **🔍 Detection Queries Used**

### 1. Failed Login Detection
Identifying the total volume of failed authentication attempts.
```spl
index=main "Failed" | stats count
```

### 2. Event Timeline Analysis
Tracking the volume of events over time to identify spikes in activity.
```spl
index=main | timechart count
```

### 3. Host Anomaly Detection
Grouping events by host and filtering for high-volume activity to spot compromised or targeted systems.
```spl
index=main | stats count by host | where count > 5
```

## **🛠️ Tools & Technologies**
- Splunk Enterprise
- SPL (Search Processing Language)
- Ubuntu Linux
- VirtualBox

## **📊 Visualizations**
*(See uploaded screenshots in this repository for search results and timecharts)*

## **💡 Key Learnings**
- The importance of log ingestion and parsing for effective SIEM operations.
- How to use `stats`, `timechart`, and `where` commands to filter and visualize data.
- Troubleshooting virtual machine resource constraints (RAM and Disk Space) during deployment.
- Finalized Week 2 documentation
