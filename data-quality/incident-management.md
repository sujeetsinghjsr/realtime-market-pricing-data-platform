# Data Quality Incident Management

## Example

A downstream client reports that the displayed price for an instrument does not match another market source.

## Investigation flow

```text
Client Report
     |
     v
Identify instrument + exchange + timestamp
     |
     v
Check Kafka event
     |
     v
Check Java application processing
     |
     v
Check Python transformation
     |
     v
Check validation result
     |
     v
Check Redis current value
     |
     v
Check Oracle/reference information
     |
     v
Compare source vs published values
     |
     v
Identify root cause
```

## Possible root causes

- Upstream exchange feed issue
- Incorrect source mapping
- Instrument identifier mismatch
- Parsing issue
- Timestamp issue
- Stale event
- Duplicate event
- Transformation/normalization issue
- Redis refresh issue
- Publication delay

## Operational objective

The investigation should establish:

1. What value was received?
2. From which exchange?
3. When was it received?
4. What Kafka event was produced?
5. What transformations were applied?
6. What validations were applied?
7. What value was available in Redis?
8. What value was ultimately published?
9. Where did the discrepancy originate?
