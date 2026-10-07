# Apache Kafka Design

## Role

Kafka acts as the real-time event-streaming layer between the Java application and downstream processing.

Conceptually:

```text
Java Application
      |
      v
Kafka Producer
      |
      v
Market Data Topic
      |
      +------------------+
      |                  |
      v                  v
Python Consumer      Other Consumers
      |
      v
Validation / Processing
```

## Production design considerations

### Topics

Topic design should reflect business/domain boundaries rather than creating unnecessary topics for every field.

### Partitions

Partitioning should support throughput while preserving required ordering characteristics.

Possible partitioning keys could include an instrument identifier or another business key, depending on the actual processing requirement.

### Consumer groups

Different downstream processing applications can consume the same event stream independently using consumer groups.

### Replay

Kafka retention can support replay/reprocessing after a downstream processing failure, subject to the actual retention and recovery design.

### Idempotency

Consumers should be designed to avoid creating incorrect duplicate state when an event is replayed.

The exact production topic names, partition counts and retention values are intentionally omitted.
