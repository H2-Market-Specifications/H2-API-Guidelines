# JWS Content Security v0.9

The JWS requirements are described in the [JWS specification PDF](../../../docs/jws/v0.9/JWS-Inhaltsdatensicherung_für_API-Webdienste_v0.9.pdf). No separate JWS YAML specification is included in this repository.

The [WebSocket client message schema](../../websocket/v0.9/ws-client-message.schema.yaml) includes the message signature field. Validating that field's structure does not verify the cryptographic signature; consult the JWS specification for verification requirements.

[Repository overview](../../../README.md)
