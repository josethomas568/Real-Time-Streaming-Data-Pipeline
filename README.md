# Real-Time News Data Pipeline: Spark Structured Streaming & Kafka

A scalable, fault-tolerant streaming data pipeline designed to ingest, process, and analyze live news feeds using Apache Kafka and Apache Spark Structured Streaming.

## Project Overview
This project demonstrates an end-to-end real-time data engineering architecture. It connects to the live NewsAPI, streams the incoming JSON payloads through an Apache Kafka message broker, and processes the continuous data stream using Spark Structured Streaming to extract real-time insights from global news cycles.

## Tech Stack & Architecture
* **Language:** Python
* **Message Broker:** Apache Kafka
* **Stream Processing:** Apache Spark (Structured Streaming)
* **Data Source:** NewsAPI (REST)
* **Deployment/Environment:** (e.g., Local / Databricks / Google Cloud)

## Pipeline Methodology
1. **Data Ingestion (Producers):** A custom Python Kafka producer connects to the NewsAPI, fetching live articles and publishing the raw JSON payloads to a dedicated Kafka topic.
2. **Stream Processing:** Apache Spark subscribes to the Kafka topic, reading the data as a continuous stream. 
3. **Data Transformations:** The Spark Structured Streaming engine applies real-time schema enforcement, cleans the text, and extracts key metadata (e.g., publication timestamps, source domains, author names).
4. **Sink/Storage:** The processed data frames are continuously written to a downstream sink for querying and visualization.

## How to Run
1. Start the Zookeeper and Kafka server instances.
2. Add your `NEWS_API_KEY` to the environment variables.
3. Run the Kafka producer script: `python news_producer.py`
4. Submit the Spark streaming job: `spark-submit spark_streaming_consumer.py`

---
Developed as a demonstration of real-time data engineering and distributed processing capabilities.
