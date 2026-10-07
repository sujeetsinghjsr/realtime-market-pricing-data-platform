# Architecture

## Objective

Provide a reliable real-time market pricing distribution flow from 28 external stock exchange feeds to downstream banking clients.

## Logical components

### 1. External exchange feeds

External exchanges provide real-time pricing events.

### 2. Java real-time feed application

The Java application handles the real-time application/feed-processing layer and sends market-data events into Kafka.

### 3. Apache Kafka

Kafka provides the real-time event-streaming layer. It decouples ingestion from downstream processing and allows consumers to process events independently.

### 4. Python transformation layer

Python handles transformation and normalization logic required to convert source-specific market-data events into a common representation.

### 5. Data quality validation

Pricing events are checked for mandatory fields, price consistency, timestamps, freshness, duplicates and other relevant controls.

### 6. Redis

Redis provides low-latency access to current real-time pricing information for downstream applications where appropriate.

### 7. Oracle

Oracle provides persistent/reference/operational data used by the platform.

### 8. Exception and investigation flow

Invalid or suspicious events are captured for investigation rather than blindly distributed.

## Key design principle

The real-time path needs to balance:

1. Low latency.
2. Reliable data quality.
3. Operational recoverability.

The validation layer should therefore focus on fast, high-value checks while supporting deeper investigation outside the critical publication path.
