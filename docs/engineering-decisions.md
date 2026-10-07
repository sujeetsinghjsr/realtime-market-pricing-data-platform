# Engineering Decisions

## Kafka for real-time streaming

Kafka provides a durable, decoupled event-streaming layer between the Java feed application and downstream processing.

## Java for application processing

The real-time application layer was implemented in Java. This repository documents the role of Java without reproducing proprietary production code.

## Python for transformation

Python was used for transformation/normalization logic. Keeping transformation responsibilities explicit makes source-specific mapping easier to understand and test.

## Redis for low-latency pricing

Redis is appropriate for fast access to current pricing information where downstream consumers need low-latency reads.

## Oracle for persistent/reference data

Oracle supports persistent/reference/operational information required by the platform.

## Validate before publication

Known invalid or suspicious market-data events should not be blindly distributed.

## Do not expose confidential implementation

This repository intentionally does not include:

- production source code
- real exchange identifiers
- client names
- credentials
- production topic names
- internal hostnames
- proprietary schemas
- confidential operational thresholds

## Production considerations

A production implementation should additionally consider:

- Kafka partitioning and ordering
- consumer groups
- replay/recovery
- idempotency
- back-pressure
- feed failover
- high availability
- Redis consistency strategy
- Oracle connection pooling
- latency monitoring
- observability
- access control
- encryption
- disaster recovery
- CI/CD
