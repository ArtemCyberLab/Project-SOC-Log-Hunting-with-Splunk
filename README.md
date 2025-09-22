SOC Log Hunting with Splunk
Overview

This project focuses on exploring Splunk in the context of SOC analytics. The main emphasis is on log hunting: data ingestion and normalization, applying SPL queries, building metrics, and drawing conclusions.

Project Goals

Understand Splunk architecture (Forwarder, Indexer, Search Head).

Upload VPN logs and create the VPN_Logs index.

Analyze logs using SPL queries.

Extract key indicators of user and IP activity.

Prerequisites

Basic SIEM knowledge.

Access to Splunk (AttackBox/VPN).

Log file VPN_logs.

Methodology

Deployed the Splunk lab and connected via browser.

In Splunk: Add Data → Upload → VPN_logs → create index VPN_Logs.

Executed a series of SPL queries to count events and filter by UserName, Source_ip, and Source_Country.

Results

Total number of events: 2862

Events related to user Maleena: 60

Name associated with IP 107.14.182.38: Smith

Events excluding France: 2814

VPN events from IP 107.3.206.58: 14

SPL Query Examples
index="VPN_Logs" | stats count
index="VPN_Logs" UserName="Maleena" | stats count
index="VPN_Logs" Source_ip="107.14.182.38" | stats values(Name)
index="VPN_Logs" Source_Country!="France" | stats count
index="VPN_Logs" Source_ip="107.3.206.58" | stats count

Analysis

Splunk efficiently indexes and processes logs.

Filtering by users and IPs makes it easy to spot anomalies.

Geographical analysis provides insights into activity distribution.

Conclusions

This research demonstrated that Splunk is a convenient and powerful tool for SOC analytics. Even basic queries allow for extracting valuable information about user behavior and network connections. Future improvements could include building dashboards, setting up automated alerts, and correlating data from multiple sources.
