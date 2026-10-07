# Python Transformation Layer

## Role

Python was used for transformation and normalization logic.

Conceptually:

```text
Kafka Event
    |
    v
Source-specific fields
    |
    v
Mapping / Transformation
    |
    v
Canonical Market Event
    |
    v
Data Quality Validation
```

Typical transformations can include:

- Field-name mapping
- Data-type conversion
- Price normalization
- Timestamp normalization
- Source-specific mapping
- Instrument identifier mapping
- Derived attributes

The repository contains documentation and synthetic examples only, not proprietary production code.
