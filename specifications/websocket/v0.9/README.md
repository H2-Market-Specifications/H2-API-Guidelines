# WebSocket Message Schemas v0.9

Machine-readable definitions of the directory service WebSocket messages, provided as **JSON Schema Draft 2020-12 expressed in YAML**. These files are message schemas, not OpenAPI or AsyncAPI interface descriptions.

Use them alongside the [WebSocket specification PDF](../../../docs/websocket/v0.9/WebSocket_Verzeichnisdienst_Schnittstellenbeschreibung_v0.9.pdf).

## Available Schemas

| File | Direction | Corresponding document section |
|---|---|---|
| [ws-client-message.schema.yaml](ws-client-message.schema.yaml) | Client → directory service | 11.3 |
| [ws-server-message.schema.yaml](ws-server-message.schema.yaml) | Directory service → client | 11.4 |

## Client Messages

The client schema covers `subscribe`, `unsubscribe`, `availabilityStart`, `availabilityHeartbeat` and `availabilityStop`.

These messages require `type`, `messageId`, `correlationId`, `timestamp`, `payload` and `signature`. The schema defines message-specific payloads and requires a null client `correlationId`.

## Server Messages

The server schema covers `subscribeAck`, `unsubscribeAck`, `availabilityAck`, `notification` and `error`. It also includes a branch for unknown future server message types.

The base envelope requires `type`, `messageId`, `correlationId`, `timestamp` and `payload`. A `signature` property is prohibited by the server schema.

## Validation and References

Parse the YAML schema and validate message instances with a JSON Schema Draft 2020-12 validator. Enable format checking where supported, in addition to the explicit schema constraints.

The server schema references the external DirectoryRecord definition:

```text
urn:h2:directory:record:v1#/$defs/DirectoryRecord
```

Register the corresponding DirectoryRecord schema with the validator's reference resolver. That schema is not included in this repository. The companion [directory service schema bundle](https://github.com/H2-Market-Specifications/h2-directoryservice-specifications/tree/main/specifications/schemas/v0.9) includes [directory-record.schema.yaml](https://github.com/H2-Market-Specifications/h2-directoryservice-specifications/blob/main/specifications/schemas/v0.9/directory-record.schema.yaml). Validation of messages containing a DirectoryRecord requires that schema. Register the approved schema locally; the URN is an identifier, not a download URL.

The schemas declare these identifiers:

| Schema | `$id` |
|---|---|
| Client messages | `urn:h2:directory:ws:client-message:v1` |
| Server messages | `urn:h2:directory:ws:server-message:v1` |

The publication directory is `v0.9`; the identifiers above are those declared in the supplied schemas.

Structural validation does not perform cryptographic signature verification. See the [JWS specification](../../../docs/jws/v0.9/) for content security requirements.

[Repository overview](../../../README.md)
