# Normalized Market Event

The normalized event provides a common representation independent of the source exchange format.

| Field | Description |
|---|---|
| instrument_id | Internal/security identifier |
| exchange | Source exchange |
| currency | Trading currency |
| bid_price | Current bid price |
| ask_price | Current ask price |
| open_price | Market/session opening price |
| high_price | Session high price |
| low_price | Session low price |
| close_price | Previous/session closing price |
| volume | Traded volume |
| event_timestamp | Source event timestamp |
| ingestion_timestamp | Platform ingestion timestamp |

## Operational attributes

A production implementation may additionally capture:

- source_sequence_number
- feed_name
- processing_timestamp
- validation_status
- validation_reason
- correlation_id

## Reference data

Instrument validation can use authoritative reference data from Oracle where appropriate.
