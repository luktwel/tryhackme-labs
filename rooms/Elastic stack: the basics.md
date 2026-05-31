# TryHackMe — Elastic Stack: SIEM Fundamentals

- **Platform:** TryHackMe
- **Category:** Security Operations / SIEM

---

## Introduction

This writeup covers my hands-on exploration of the Elastic Stack (ELK Stack) as a SIEM tool. Coming from a Splunk background, I approached this with a focus on how the core concepts translate between platforms — log ingestion, filtering, querying, and visualization. Understanding multiple SIEM tools is valuable in a SOC environment, as different organizations use different platforms.

---

## What is the Elastic Stack?

The Elastic Stack is an open-source SIEM solution built from four components that work together:

| Component | Role |
|-----------|------|
| **Elasticsearch** | Full-text search and analytics engine for JSON-formatted documents |
| **Logstash** | Data processing pipeline — filters, normalizes, and routes data from multiple sources to a destination (e.g. Kibana) |
| **Kibana** | Web-based visualization tool that works alongside Elasticsearch to analyze and visualize data |
| **Beats** | Lightweight host-based agents that forward endpoint data back to Elasticsearch |

---

## The Discover Tab

The Discover tab is the primary interface for a SOC analyst working in Kibana. This is where ingested log data is displayed and explored. Much like Splunk's search interface, it supports filtering by time, source, country, and other fields.

### Index Patterns

Kibana uses **index patterns** to determine which data to retrieve and from which ingested source. For this room, the `vpn_connections` index was used throughout.

### Fields Pane

The Fields Pane allows you to filter logs for specific values within a given field — for example `ip`, `destination`, `location`, or `source`. Filters can be layered by selecting a field and using the **Add Filter** option next to the search bar.

### Filters Applied in This Room

**Time-based filter:** Events were filtered between `31/01/2021` and `02/02/2022` using the date & time range picker.

> 📸 *Screenshot: date & time range filter set between 31/01/2021 and 02/02/2022*

---

**Field-based filter:** Filtering on `UserName : emanda` to identify which source IP had the highest number of hits.

> 📸 *Screenshot: source IP breakdown with UserName filter set to emanda*

---

**Exclusion filter:** Filtering on a specific IP address while excluding connections originating from New York — demonstrating how negative filters work in Kibana.

> 📸 *Screenshot: filter excluding New York as source location*

---

## KQL — Kibana Query Language

KQL (Kibana Query Language) is Kibana's built-in query language, similar in purpose to SPL in Splunk. It supports two search modes: free text search and field-based search.

### Free Text Search

Free text search filters across all data for a specific word or phrase. The term must be written exactly as it appears in the data to return results.

KQL supports wildcards using `*`, similar to SPL:

```
United*
```

This would return all records containing a word starting with "United".

### Logical Operators

KQL supports the same logical operators as most query languages:

| Operator | Usage |
|----------|-------|
| `AND` | Match both conditions — e.g. `America AND New York` |
| `OR` | Match either condition — e.g. `America OR New York` |
| `NOT` | Exclude a condition — e.g. `NOT America` |

### Field-Based Search

Field-based search requires specifying both a field name and the value to search for within it:

```
Source_ip : 238.163.231.224 AND UserName : Suleman
```

This example filters for a specific source IP address **and** a specific username simultaneously.

### Query Examples

**Filtering by country and multiple users:**

```
Source_Country : "United States" AND (UserName : "Albert" OR UserName : "James")
```

> 📸 *Screenshot: KQL query filtering on United States with users Albert and James*

---

**Finding VPN connections after a user was terminated:**

To find connections made after user Johnny Brown was terminated on 1 January 2022, I used a field-based filter on `UserName : "Johnny Brown"` and inspected the timeline graph to identify activity after the termination date.

> 📸 *Screenshot: UserName filter applied for Johnny Brown with timeline graph visible*

---

## The Visualisation Tab

The Visualisation tab allows log data to be represented in different chart types for a clearer overview. This is particularly useful during investigations when you need to spot trends or outliers at a glance.

### Correlations

The Correlations feature lets you drop multiple fields into a visualization table to examine relationships between them. For example:

```
Source_Country : "United States" AND Source_State : "New York" AND Source_ip : *
```

This correlation table shows all connections from New York, United States, grouped by source IP — useful for geographic analysis of access patterns.

> 📸 *Screenshot: correlation table with Source_Country, Source_State, and Source_ip fields*

---

### Tables

KQL supports creating table views for structured data output, similar to the `| table` command in SPL. Tables were used to answer several of the room's questions by giving a clean, column-based view of the relevant fields.

> 📸 *Screenshot: table view created to answer room questions*

---

## Dashboards

Dashboards in Kibana allow you to save and combine custom visualizations into a single view. Once built, a dashboard gives quick access to the exact charts and filters you've configured, without needing to rebuild queries each time.

This is particularly useful in a SOC context, where analysts may want a persistent overview of specific metrics — for example: active VPN sessions by country, failed login attempts over time, or top source IPs by connection volume.

---

## Key Takeaways

- The Elastic Stack and Splunk share the same underlying concepts — log ingestion, field-based filtering, query languages with logical operators, and visualization dashboards. Transferable knowledge between platforms is real and valuable.
- KQL is more straightforward than SPL for basic filtering, but SPL offers more powerful transformational commands (e.g. `stats`, `eval`, `timechart`).
- Index patterns in Kibana serve a similar role to indexes in Splunk — they define the data scope for your queries.
- The Fields Pane is an efficient way to narrow down large datasets without writing complex queries.
- Dashboards are a practical tool for persistent SOC monitoring views.

---

*Written as part of my cybersecurity learning journey on TryHackMe. This writeup documents my personal workflow and understanding — answers to specific questions are intentionally omitted.*





