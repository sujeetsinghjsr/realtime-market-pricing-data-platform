# Real-Time Market Data Quality Rules

## Mandatory checks

| Rule | Example failure |
|---|---|
| Required field | instrument_id is missing |
| Exchange validity | Unknown exchange |
| Timestamp validity | Event timestamp is missing |
| Price validity | Negative price |
| Bid/ask relationship | Bid greater than ask |
| Freshness | Price is stale beyond configured threshold |
| Duplicate event | Same event received more than once |
| Instrument validity | Unknown security identifier |

## Validation outcome

```text
VALID
  -> eligible for downstream publication

INVALID / SUSPICIOUS
  -> do not blindly publish
  -> capture reason
  -> alert / investigate according to severity
```

## Severity

Not every quality issue needs to stop the entire feed.

A production design can classify issues, for example:

- CRITICAL: stop/quarantine affected flow
- HIGH: block affected instrument/source
- MEDIUM: publish with monitoring according to business rules
- LOW: log and monitor
