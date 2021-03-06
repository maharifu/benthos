---
title: avro
type: processor
---

<!--
     THIS FILE IS AUTOGENERATED!

     To make changes please edit the contents of:
     lib/processor/avro.go
-->


Performs Avro based operations on messages based on a schema.


import Tabs from '@theme/Tabs';

<Tabs defaultValue="common" values={[
  { label: 'Common', value: 'common', },
  { label: 'Advanced', value: 'advanced', },
]}>

import TabItem from '@theme/TabItem';

<TabItem value="common">

```yaml
avro:
  operator: to_json
  encoding: textual
  schema: ""
```

</TabItem>
<TabItem value="advanced">

```yaml
avro:
  operator: to_json
  encoding: textual
  schema: ""
  parts: []
```

</TabItem>
</Tabs>

EXPERIMENTAL: This processor is considered experimental and is therefore subject
to change outside of major version releases.

## Operators

### `to_json`

Converts Avro documents into a JSON structure. This makes it easier to
manipulate the contents of the document within Benthos. The encoding field
specifies how the source documents are encoded.

### `from_json`

Attempts to convert JSON documents into Avro documents according to the
specified encoding.

## Fields

### `operator`

`string` The [operator](#operators) to execute

Options are: `to_json`, `from_json`.

### `encoding`

`string` An Avro encoding format to use for conversions to and from a schema.

Options are: `textual`, `binary`, `single`.

### `schema`

`string` A full Avro schema to use.

### `parts`

`array` An optional array of message indexes of a batch that the processor should apply to.
If left empty all messages are processed. This field is only applicable when
batching messages [at the input level](/docs/configuration/batching).

Indexes can be negative, and if so the part will be selected from the end
counting backwards starting from -1.


