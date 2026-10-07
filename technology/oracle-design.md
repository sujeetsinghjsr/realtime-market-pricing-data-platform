# Oracle Design

## Role

Oracle supports persistent/reference/operational information used by the platform.

Examples of logical data areas include:

- Instrument/reference data
- Exchange metadata
- Operational configuration
- Historical or audit information where applicable

## Reference-data interaction

A real-time event may use reference data to validate whether an instrument or source is recognized.

```text
Market Event
     |
     v
Instrument ID
     |
     v
Oracle Reference Data
     |
     v
Validation Decision
```

Actual production schemas, table names and connection details are intentionally excluded.
