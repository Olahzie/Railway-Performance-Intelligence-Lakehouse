# Project Overview

Real-time railway performance analytics platform built using the Databricks Lakehouse architecture, Apache Kafka, PySpark Structured Streaming, and Delta Lake.

This project ingests live train movement data, enriches it with weather and operational reference data, processes it through a Medallion Architecture (Bronze → Silver → Gold), and delivers real-time KPIs for railway operations, reliability monitoring, and performance analytics.


## Problem Statement
### Background

Modern railway systems generate massive volumes of operational data every second from train movements, station events, schedules, route operations, and external environmental services such as weather systems. This data is highly dynamic, time-sensitive, and often arrives in semi-structured streaming formats, making it difficult for railway operators to monitor network performance, identify disruptions, and analyze operational efficiency in real time.

Traditional reporting systems are often batch-oriented and lack the scalability and responsiveness required to process continuous railway event streams. As a result, railway operators struggle with delayed operational visibility, inconsistent performance reporting, and limited predictive insights into service reliability and network congestion.

## Business Need

Railway operations teams require a unified real-time analytics platform capable of ingesting, processing, enriching, and analyzing live train movement and operational data to support:

* Real-time operational monitoring
* Delay and congestion management
* Reliability and punctuality analysis
* Weather impact assessment
* Route and station performance tracking
* Executive and strategic reporting

The organization wants to build a scalable Lakehouse platform on Databricks that consolidates streaming railway data into a centralized architecture for operational intelligence and business analytics.

## Objectives

Design and implement a real-time Railway Performance Intelligence Lakehouse capable of:

* Ingesting live train movement and operational streaming data from Kafka and external APIs
* Processing high-volume streaming data using PySpark Structured Streaming
* Applying Medallion Architecture (Bronze → Silver → Gold) using Delta Lake
* Performing incremental transformations, CDC merges, deduplication, and data quality checks
* Enriching train events with weather and reference data
* Generating operational KPIs and reliability metrics for dashboarding and reporting
* Supporting scalable analytics and near real-time decision-making

## Key Requirements

### Real-Time Data Ingestion
* Consume train movement events from Kafka streams
* Handle high-throughput streaming data reliably
* Support late-arriving and duplicate events

Data Sources

* [Network Rail Open Data Platform](https://wiki.openraildata.com/index.php/Train_Movement) : This is a real-time API that generates train movement data from all train companies across UK. The following image shows the data description from the API.

![UK rail network](https://github.com/Olahzie/Railway-Performance-Intelligence-Lakehouse/blob/main/rail_data_description.png)

* [Open Weather API](https://openweathermap.org/): Real-time weather data for any place in the world using the city name.

### Data Processing & Quality
* Perform schema validation and enforcement
* Deduplicate train movement events
* Implement watermarking and checkpointing
* Support incremental MERGE operations with Delta Lake

### Data Modeling
* Build dimensional models with fact and dimension tables
* Separate transactional train movement data from reference and master data
* Create optimized Gold KPI tables for analytics

### Operational Analytics
Generate KPIs such as:
* On-time arrival percentage
* Average delay
* Severe delay rate
* Congestion index
* Train reliability index
* Weather impact metrics
* Station compliance rate

### Governance & Reliability
* Ensure auditability and fault tolerance
* Enable schema evolution and transactional consistency
* Maintain reliable streaming recovery using checkpoints

### Reporting & Visualization

![BI Dashboard](https://github.com/Olahzie/Railway-Performance-Intelligence-Lakehouse/blob/main/Dashboard%20BI-1.png)

![BI Dashboard](https://github.com/Olahzie/Railway-Performance-Intelligence-Lakehouse/blob/main/Dashboard%20BI-2.png)

![BI Dashboard](https://github.com/Olahzie/Railway-Performance-Intelligence-Lakehouse/blob/main/Dashboard%20BI-3.png)




### Expected Outcome

A production-ready Railway Performance Intelligence Lakehouse that transforms real-time train movement data into actionable operational insights, enabling railway stakeholders to improve punctuality, monitor disruptions, optimize network efficiency, and enhance overall service reliability through scalable real-time analytics.

# Architecture Diagram
![Railway Architecture](https://github.com/Olahzie/Railway-Performance-Intelligence-Lakehouse/blob/main/Lakehouse%20Architecture.png)
