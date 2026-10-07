# Processing Flow

```text
28 Exchange Feeds
       |
       v
Java Feed Application
       |
       v
Apache Kafka
       |
       v
Python Transformation
       |
       v
Data Quality Validation
       |
   +---+---+
   |       |
 PASS     FAIL
   |       |
   v       v
Redis   Exception /
   |    Investigation
   v
Client Pricing

Oracle supports reference/persistent/operational data.
```

## Critical-path consideration

Real-time pricing requires low latency. High-value validations should be performed before publication without introducing unnecessary processing delay.

More expensive investigation, historical analysis or root-cause workflows can operate outside the critical publication path.
