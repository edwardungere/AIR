# Splunk 

## Overview
- Splunk is a Security Information & Event Manager that can ingest massive amounts of data from machines, logs, and other IT/Business operations. It is built on multiple, seperate components that form a coherent and efficient pipeline.
  
### 1. Forwarders/Inputs:
  - Collects data from remote machines/instances
    
### 2. Indexer:
  - Processes and stores data for quick retrieval
  - Creates and manages repositories of data recieved from forwarders
  - Parses, transforms, and indexes for searching
  - Handles search requests from the search head for fast retrieval of data
        
### 3. Search Head:
  - Analyzes and visualizes data
  - Provides user-interface, Splunk Web, and REST API for searching, reporting, and visualization
  - Supports schedules searches, alerts, and dashboards

## Deployment
- Splunk can be deployed as a SaaS (Splunk Cloud Platform)
- Or has an on-premis solution (Splunk Enterprise)
- Capabilities can be extended through Observability Cloud or SOAR

## Cybersecurity Use-cases
- Enables visibility and detecting to cyber threats effciciently and in real-time
- Correlates data across multiple systems
- Identifies and detects bottlenecks and system information

## Components of Splunk

### 1. Forwarders/Inputs

#### 1.1 Universal Forwarder
- Lighweight, Splunk agent
- Securely and efficiently forwards raw data from systems to remote sources or heavy forwarders
- Supports multiple systems and data types for forwarding
- Syslog, CSV, JSON, XML, custom formats
- input.conf specifies monitored directories/files
- Supports SSL/TLS

#### 1.2 Heavy Forwarder
- Sends data to other Splunk instances or third party systems
- Used for Pre-processing: Parses, filters, route, and masks data
- Useful for large log streams, sensitive data, and selective routing
- Suports custome scripts

### 2. Indexer
  
#### 2.1 Event Index
- An event consists of a set of values associated with a timestamp

#### 2.2 Metric Index
- A metric consist of a timestamp and measurement, can also contain a dimension
- A measurement consists of a metric name and its value
- A dimension contains additional information about the metric

### 3. Search Head

#### 3.1 Search Processing Langauge (SPL)
- Parses, filters, analyzes, and transforms data
- Similar to Unix syntax
- Key commands include: search, stats, eval, rex, table, sort
- Advanced: Sub-searches, lookups, and other complex analytical quieries

#### 3.2 Search Processing Langauge 2 (SPL2)
- Supports SQL syntax
- More concise with greater functionality
- More consistent syntax than previous version
- Backwards comptaible with SPL

#### 3.3 Dashboards
- Used for visualization and interactive interface for data
- Includes Panels, charts (bar, line, pie), tables, and event viewers
- Configured via XML or Splunk Web UI
