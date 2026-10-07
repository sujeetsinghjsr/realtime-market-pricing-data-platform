# Redis Design

## Role

Redis can provide low-latency access to the latest/current pricing state.

Conceptually:

```text
Validated Market Event
        |
        v
      Redis
        |
        v
Current Price Lookup
        |
        v
Downstream Client/Application
```

## Example logical key

```text
price:{instrument_id}
```

Example synthetic value:

```json
{
  "bid": 101.25,
  "ask": 101.30,
  "timestamp": "2026-01-10T10:15:30.125Z"
}
```

The actual production key structure and configuration are intentionally omitted.
