---
title: stdout
type: metrics
---

<!--
     THIS FILE IS AUTOGENERATED!

     To make changes please edit the contents of:
     lib/metrics/stdout.go
-->


Prints aggregated metrics as JSON objects to stdout.

```yaml
metrics:
  stdout:
    push_interval: ""
    static_fields:
      '@service': benthos
    flush_metrics: false
```

EXPERIMENTAL: This component is considered experimental and is therefore subject
to change outside of major version releases.

When Benthos shuts down all aggregated metrics are printed. If a
`push_interval` is specified then metrics are also printed
periodically.

## Fields

### `push_interval`

`string` An optional period of time to continuously print metrics.

### `static_fields`

`object` A map of static fields to add to each flushed metric object.

### `flush_metrics`

`bool` Whether counters and timing metrics should be reset to 0 each time metrics are printed.


