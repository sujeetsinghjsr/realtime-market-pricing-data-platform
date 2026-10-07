# Business Requirement

## Objective

A banking market-data platform receives real-time pricing feeds from 28 external stock exchanges and publishes normalized real-time pricing information to downstream clients.

## Example pricing attributes

- Bid
- Ask
- Open
- Close
- High
- Low
- Volume

## Functional requirements

1. Receive real-time events from multiple exchanges.
2. Process incoming feeds through a Java application layer.
3. Stream market-data events using Apache Kafka.
4. Transform and normalize source-specific data using Python.
5. Validate critical data-quality rules.
6. Prevent invalid/suspicious events from being blindly distributed.
7. Maintain current pricing in a low-latency Redis layer where appropriate.
8. Use Oracle for persistent/reference/operational information.
9. Publish validated pricing data to downstream consumers.
10. Support operational investigation of client-reported pricing discrepancies.
11. Monitor feed health and data freshness.

The repository intentionally uses generalized terminology and synthetic examples rather than confidential client/exchange details.
