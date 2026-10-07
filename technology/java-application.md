# Java Application Layer

## Role

The real-time application was built in Java and formed part of the market-data ingestion/application layer.

Conceptual responsibilities:

```text
Receive Feed
    |
    v
Parse / Identify Source
    |
    v
Create Internal Event
    |
    v
Publish to Kafka
```

## Engineering considerations

- Connection/session management with upstream feeds
- Message parsing
- Source identification
- Error handling
- Kafka producer reliability
- Logging and correlation
- Graceful recovery
- Monitoring

Production source code is intentionally not included.
