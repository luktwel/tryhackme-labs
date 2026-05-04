# Splunk Basics — TryHackMe

## What is Splunk?
Splunk is a SIEM platform that collects, processes 
and indexes log data, making it searchable for 
SOC analysts to detect and investigate threats.

## Core Components

| Component   | Function                                        |
|-------------|-------------------------------------------------|
| Forwarder   | Collects data and sends it to the indexer       |
| Indexer     | Receives data and stores it as events           |
| Search Head | Allows searching through events using SPL       |

## Data Ingestion
Splunk can ingest any type of data — JSON, CSV, 
raw logs, etc. It automatically transforms raw 
data into individual searchable events.

## Practical Exercise
A VPN log file (vpn.json) was uploaded into Splunk 
to demonstrate how raw JSON data is automatically 
processed into events.

Queries used:
- Searching for a specific IP address
- Filtering by username
- Excluding countries from results

## What I Learned
- How the 3 main Splunk components work together
- How to upload and inspect raw log data in Splunk
- Basic SPL queries for filtering and searching
