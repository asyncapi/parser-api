---
title: "Migrating to v3"
---

To provide as smooth a transition as possible, this document shows the breaking changes between AsyncAPI Parser API v2.0.0 and v3.0.0 in an interactive manner.

The changes from v2 to v3 are reflected in `Message` and `MessageTrait` objects.


## Replaced `messageId` with `id`

Since `id()` already represents that the message has an ID, `messageId()` is redundent in terms of the purpose.

```md
# AsyncAPI Parser API v2.0.0
...
## Message
- id(): `string`
- hasMessageId(): `boolean`
- messageId(): `string` | `undefined`
...
## MessageTrait
- id(): `string`
- hasMessageId(): `boolean`
- messageId(): `string` | `undefined`
```

```md
# AsyncAPI Parser API v3.0.0
...
## Message
- id(): `string`
- hasMessageId(): `boolean`
...
## MessageTrait
- id(): `string`
- hasMessageId(): `boolean`
```


------------------------------



## Changed Return Types for  `schemaFormat`

In v2, the return type of `schemaFormat()` in `Message` and `MessageTrait` objects is only defined as `string`. 



```md
# AsyncAPI Parser API v2.0.0
...
## Message
- id(): `string`
- hasSchemaFormat(): `boolean`
- schemaFormat(): `string`
...
## MessageTrait
- id(): `string`
- hasSchemaFormat(): `boolean`
- schemaFormat(): `string`
```

In v3, the return type has been changed to `string | undefined`, emphasizing that the payload of a message is optional, so it can be undefined as well as be defined as a string. 

```md
# AsyncAPI Parser API v3.0.0
...
## Message
- id(): `string`
- hasSchemaFormat(): `boolean`
- schemaFormat(): `string` | `undefined`
...
## MessageTrait
- id(): `string`
- hasSchemaFormat(): `boolean`
- schemaFormat(): `string` | `undefined`
```