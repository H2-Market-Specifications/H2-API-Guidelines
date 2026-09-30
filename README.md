# H2 API Guidelines v0.9

API guidelines and technical specifications for hydrogen market communication, intended for market participants, software providers and developers.

## Documents

| Document | Subject | Download |
|---|---|---|
| API Guideline | Cross-interface requirements for API communication. | [API Guideline v0.9](docs/api-guideline/v0.9/API_Guideline_v0.9.pdf) |
| JWS Content Security | Content security for API web services using JSON Web Signature (JWS). | [JWS specification v0.9](docs/jws/v0.9/JWS-Inhaltsdatensicherung_für_API-Webdienste_v0.9.pdf) |
| WebSocket Interface | WebSocket communication with the directory service. | [WebSocket specification v0.9](docs/websocket/v0.9/WebSocket_Verzeichnisdienst_Schnittstellenbeschreibung_v0.9.pdf) |

## Machine-Readable Specifications

The WebSocket message schemas are **JSON Schema Draft 2020-12 expressed in YAML**.

| Schema | Direction | File |
|---|---|---|
| Client messages | Client → directory service | [ws-client-message.schema.yaml](specifications/websocket/v0.9/ws-client-message.schema.yaml) |
| Server messages | Directory service → client | [ws-server-message.schema.yaml](specifications/websocket/v0.9/ws-server-message.schema.yaml) |

See the [WebSocket schema documentation](specifications/websocket/v0.9/) for supported message types and validation dependencies.

## Using the Documentation

Start with the API Guideline for the overall communication requirements. Read the JWS specification for content security and the WebSocket specification for communication with the directory service.

Use the WebSocket YAML schemas alongside the WebSocket document when implementing or validating messages. Schema validation checks message structure; cryptographic signature verification must be performed separately according to the JWS requirements.

The publication version is **0.9**. Schema identifiers are defined within the YAML files and must be used as declared.

## Repository Structure

| Directory | Contents |
|---|---|
| `docs/api-guideline/v0.9/` | API Guideline PDF. |
| `docs/jws/v0.9/` | JWS specification PDF. |
| `docs/websocket/v0.9/` | WebSocket specification PDF. |
| `specifications/websocket/v0.9/` | Client and server message schemas. |

The API Guideline and JWS documentation are provided as PDFs; their specification directories currently contain navigation READMEs only. No shared YAML components are currently published under `specifications/_shared/v0.9/`.

## Related Specifications

| Repository | Subject |
|---|---|
| [h2-market-message-specifications](https://github.com/H2-Market-Specifications/h2-market-message-specifications) | Market message schemas. |
| [h2-market-openapi-specifications](https://github.com/H2-Market-Specifications/h2-market-openapi-specifications) | Message-specific OpenAPI definitions. |
| [h2-directoryservice-specifications](https://github.com/H2-Market-Specifications/h2-directoryservice-specifications) | Directory service specifications and the companion DirectoryRecord schema. |

Companion repositories may require separate access. The publication repository for directory service specifications currently contains no files; the external DirectoryRecord dependency is not included in this guidelines publication.

## Questions and Feedback

For questions or inconsistencies, open a [repository issue](https://github.com/H2-Market-Specifications/h2-api-guidelines/issues) and include the affected document or schema, its version and the relevant section.
