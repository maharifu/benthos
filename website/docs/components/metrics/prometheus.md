---
title: prometheus
type: metrics
---

<!--
     THIS FILE IS AUTOGENERATED!

     To make changes please edit the contents of:
     lib/metrics/prometheus.go
-->


Host endpoints (`/metrics` and `/stats`) for Prometheus scraping.


import Tabs from '@theme/Tabs';

<Tabs defaultValue="common" values={[
  { label: 'Common', value: 'common', },
  { label: 'Advanced', value: 'advanced', },
]}>

import TabItem from '@theme/TabItem';

<TabItem value="common">

```yaml
metrics:
  prometheus:
    prefix: benthos
```

</TabItem>
<TabItem value="advanced">

```yaml
metrics:
  prometheus:
    prefix: benthos
    push_url: ""
    push_interval: ""
    push_job_name: benthos_push
```

</TabItem>
</Tabs>

Metrics paths will differ from [the list](/docs/components/metrics/about#paths) in that dot separators will
instead be underscores.

## Fields

### `prefix`

`string` A string prefix to add to all metrics.

### `push_url`

`string` An optional [Push Gateway URL](#push-gateway) to push metrics to.

### `push_interval`

`string` The period of time between each push when sending metrics to a Push Gateway.

### `push_job_name`

`string` An identifier for push jobs.

## Push Gateway

The field `push_url` is optional and when set will trigger a push of
metrics to a [Prometheus Push Gateway](https://prometheus.io/docs/instrumenting/pushing/)
once Benthos shuts down. It is also possible to specify a
`push_interval` which results in periodic pushes.

The Push Gateway is useful for when Benthos instances are short lived. Do not
include the "/metrics/jobs/..." path in the push URL.

