---
title: "CrisisCast"
collection: projects
type: Big Data Pipeline
permalink: /projects/crisiscast
excerpt: "Built a real-time crisis detection pipeline using Kafka, PySpark, and a locally hosted LLM classifier."
header:
  image: /images/crisiscast.png
---

Developed a real-time emergency detection pipeline using Reddit data streams.

- Ingested Reddit data via Apache Kafka and processed with Spark Structured Streaming
- Integrated a locally hosted LLM classifier to tag crisis posts
- Stored enriched metadata in MongoDB and semantic vectors (1,000+ embeddings) in Qdrant using Sentence Transformers
- Built an interactive Plotly dashboard to visualize crisis trends and support semantic search across live posts
- Dockerized for reproducibility and real-time deployment

