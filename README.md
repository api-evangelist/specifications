# API Specifications (specifications)

Meta-index of the specification languages used to describe APIs, events, schemas, and service interfaces across the modern API landscape. This repo is the **META** layer above the topical repos that profile each individual specification — it catalogs every major HTTP, event-driven, schema, and service interface specification along with its current version, governing body, license, and tooling ecosystem.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/specifications/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

- API Specifications, Specification Languages, API Design, Contracts, Schemas, Interface Definitions, Standards

## Timestamps

- **Created:** 2026-05-22
- **Modified:** 2026-05-22

## The Specification Landscape

API specifications are not one thing. They fall into a handful of recurring categories, each addressing a different shape of API contract. This index draws the lines between them and points to the topical repo for each.

### HTTP request/response specifications

Languages for describing synchronous request/response APIs over HTTP. **OpenAPI 3.0/3.1** is the dominant standard, with **RAML** persisting in Mulesoft/Anypoint estates and **API Blueprint** documented here as historical context. Older XML-based interface description still lives in **WSDL/SOAP** for legacy enterprise and government systems.

### Event-driven specifications

Languages for describing message-driven and event-driven APIs across Kafka, AMQP, MQTT, WebSocket, NATS, and SNS/SQS. **AsyncAPI 3.0** is the canonical specification, frequently used alongside protocol-native schemas (Avro, Protobuf, JSON Schema) for the message payload itself.

### Service interface definition languages (IDLs)

Protocol-agnostic languages that define service contracts and emit clients, servers, and other specs. **gRPC/Protobuf** is the high-performance binary IDL backbone; **GraphQL SDL** defines type systems and queryable graphs; **Smithy** (AWS) and **TypeSpec** (Microsoft) are higher-level IDLs that compile down to OpenAPI, JSON Schema, and Protobuf; **WSDL** is the historical baseline.

### Schema languages

Languages for describing data shapes independent of transport. **JSON Schema** (Draft 2020-12) is the embedded schema language inside OpenAPI 3.1, AsyncAPI 3, and most modern API contracts. **JSON Structure** is an emerging spec that extends JSON Schema's type system for cleaner code generation.

### RPC protocols

Specifications for remote procedure call protocols. **JSON-RPC 2.0** is the lightweight, JSON-encoded RPC powering blockchain APIs (Ethereum, Bitcoin) and IDE language servers (LSP). **gRPC** is the binary HTTP/2-based RPC framework using Protobuf as its IDL.

### Vendor-defined specifications

Vendor-owned specification formats that govern modern API products. **Tinybird's API spec** is profiled here as a representative — a higher-level domain model that often emits OpenAPI as a derived artifact.

### How they relate

- OpenAPI 3.1 embeds **JSON Schema 2020-12** as its schema dialect; OpenAPI 3.0 uses a closely-related Schema Object.
- AsyncAPI embeds JSON Schema for payloads but routinely points to Avro/Protobuf schemas via `schemaFormat`.
- Smithy and TypeSpec sit *above* OpenAPI and Protobuf as authoring sources of truth that emit them.
- gRPC uses Protobuf as its IDL; Protobuf can also be used standalone as a serialization spec.
- RAML and API Blueprint cover the same problem space as OpenAPI but have lost mindshare; their tooling ecosystems are now in maintenance mode.
- WSDL/SOAP describes the same surface as OpenAPI but for XML/SOAP transports; modern migrations replace WSDL with OpenAPI- or gRPC-described services.

## APIs

### OpenAPI Specification (OAS)

The OpenAPI Specification (formerly Swagger) is the dominant industry standard for describing HTTP-based RESTful APIs. Active versions: **3.0.x** and **3.1.0** (fully aligned with JSON Schema 2020-12). Governed by the **OpenAPI Initiative**, a Linux Foundation project, under the **Apache 2.0** license.

**Human URL:** [https://www.openapis.org/](https://www.openapis.org/)

**Tooling:** [OpenAPI Tools Directory](https://tools.openapis.org/)

#### Properties

- [Documentation](https://learn.openapis.org/)
- [Specification (latest)](https://spec.openapis.org/oas/latest.html)
- [OpenAPI 3.1.0](https://spec.openapis.org/oas/v3.1.0)
- [OpenAPI 3.0.3](https://spec.openapis.org/oas/v3.0.3)
- [GitHub Repository](https://github.com/OAI/OpenAPI-Specification)
- [Specification Record Example](examples/openapi-example.json)

### AsyncAPI Specification

The open standard for describing event-driven and message-driven APIs across Kafka, AMQP, MQTT, WebSocket, NATS, and SNS/SQS. **AsyncAPI 3.0** (December 2023) decoupled operations from channels for clearer pub/sub, request/reply, and streaming modelling. Governed by the **AsyncAPI Initiative** under the **Linux Foundation**, **Apache 2.0** licensed.

**Human URL:** [https://www.asyncapi.com/](https://www.asyncapi.com/)

**Tooling:** [AsyncAPI Tools](https://www.asyncapi.com/tools)

#### Properties

- [Documentation](https://www.asyncapi.com/docs)
- [Specification (latest)](https://www.asyncapi.com/docs/reference/specification/latest)
- [AsyncAPI 3.0.0](https://www.asyncapi.com/docs/reference/specification/v3.0.0)
- [GitHub Organization](https://github.com/asyncapi)
- [Specification Record Example](examples/asyncapi-example.json)

### JSON Schema

A declarative language for annotating and validating JSON documents — the foundational schema language embedded in OpenAPI 3.1, AsyncAPI 3, and most modern API specifications. Current dialect: **Draft 2020-12**. Reference tooling is **BSD-3-Clause / MIT**.

**Human URL:** [https://json-schema.org/](https://json-schema.org/)

**Tooling:** [JSON Schema Tooling Ecosystem](https://json-schema.org/tools)

#### Properties

- [Documentation](https://json-schema.org/learn/getting-started-step-by-step)
- [Draft 2020-12 Release Notes](https://json-schema.org/draft/2020-12/release-notes)
- [JSON Schema Core (2020-12)](https://json-schema.org/draft/2020-12/json-schema-core)
- [GitHub Organization](https://github.com/json-schema-org)
- [Specification Record Example](examples/json-schema-example.json)

### JSON Structure

An emerging open specification that extends and complements JSON Schema with a clearer, code-generation-friendly type system designed for data contracts and cross-language model generation. Apache 2.0 licensed.

**Human URL:** [https://json-structure.org/](https://json-structure.org/)

#### Properties

- [Documentation](https://json-structure.org/)
- [Core Meta-Schema v0](https://json-structure.org/meta/core/v0/)
- [GitHub Repository](https://github.com/json-structure/specification)
- [Specification Record Example](examples/json-structure-example.json)

### GraphQL SDL

A query language and runtime for APIs, defined by the GraphQL Specification. The **Schema Definition Language (SDL)** is the declarative format for types, queries, mutations, and subscriptions. Governed by the **GraphQL Foundation**, a Linux Foundation project, under **OWFa 1.0**. Current edition: October 2021 with continued Working Drafts.

**Human URL:** [https://graphql.org/](https://graphql.org/)

#### Properties

- [Documentation](https://graphql.org/learn/)
- [Specification (October 2021)](https://spec.graphql.org/October2021/)
- [Working Draft](https://spec.graphql.org/draft/)
- [GitHub Repository](https://github.com/graphql/graphql-spec)
- [Specification Record Example](examples/graphql-example.json)

### gRPC and Protocol Buffers

High-performance RPC framework using HTTP/2 and **Protocol Buffers** as its IDL and wire format. **gRPC** is a CNCF graduated project; **Protocol Buffers** (proto3) is maintained by Google. Apache 2.0 / BSD-3-Clause licensed.

**Human URL:** [https://grpc.io/](https://grpc.io/) — [https://protobuf.dev/](https://protobuf.dev/)

#### Properties

- [gRPC Documentation](https://grpc.io/docs/)
- [Protobuf Language Guide (proto3)](https://protobuf.dev/programming-guides/proto3/)
- [proto3 Specification](https://protobuf.dev/reference/protobuf/proto3-spec/)
- [gRPC GitHub Organization](https://github.com/grpc)
- [Protocol Buffers GitHub Organization](https://github.com/protocolbuffers)
- [Specification Record Example](examples/grpc-protobuf-example.json)

### Smithy

An open-source IDL and code-generation framework created and maintained by AWS. Protocol-agnostic (HTTP REST, AWS JSON, MQTT, RPC), traits-based modelling. Used to generate AWS service SDKs, OpenAPI, and JSON Schema. **Apache 2.0** licensed.

**Human URL:** [https://smithy.io/](https://smithy.io/)

#### Properties

- [Documentation](https://smithy.io/2.0/quickstart.html)
- [Smithy 2.0 Specification](https://smithy.io/2.0/spec/index.html)
- [GitHub Repository](https://github.com/smithy-lang/smithy)
- [Specification Record Example](examples/smithy-example.json)

### TypeSpec

A language for describing API shapes developed by **Microsoft** (formerly Cadl). TypeSpec definitions emit OpenAPI 3.x, JSON Schema, Protobuf, and other artifacts, and serve as the upstream source for Azure SDK generation. **MIT** licensed.

**Human URL:** [https://typespec.io/](https://typespec.io/)

#### Properties

- [Documentation](https://typespec.io/docs)
- [Language Reference](https://typespec.io/docs/language-basics/overview)
- [GitHub Repository](https://github.com/microsoft/typespec)
- [Specification Record Example](examples/typespec-example.json)

### RAML (RESTful API Modeling Language)

A YAML-based modelling language for RESTful APIs, originally created by Mulesoft. **RAML 1.0** (2016) is the current spec. Steward: Mulesoft/Salesforce. Industry mindshare has shifted to OpenAPI; RAML remains in Anypoint estates. **Apache 2.0**.

**Human URL:** [https://raml.org/](https://raml.org/)

#### Properties

- [Documentation](https://raml.org/developers/raml-100-tutorial)
- [RAML 1.0 Specification](https://github.com/raml-org/raml-spec/blob/master/versions/raml-10/raml-10.md)
- [GitHub Organization](https://github.com/raml-org)
- [Specification Record Example](examples/raml-example.json)

### API Blueprint

A Markdown-based specification language for web APIs, originally created by **Apiary** (acquired by Oracle). The spec is **MIT** licensed but development effectively stalled after acquisition. Documented here as historical context for the API specification landscape.

**Human URL:** [https://apiblueprint.org/](https://apiblueprint.org/)

#### Properties

- [Documentation](https://apiblueprint.org/documentation/tutorial.html)
- [Specification](https://github.com/apiaryio/api-blueprint/blob/master/API%20Blueprint%20Specification.md)
- [GitHub Repository](https://github.com/apiaryio/api-blueprint)
- [Specification Record Example](examples/api-blueprint-example.json)

### WSDL / SOAP

The historical XML-based interface definition for SOAP web services. **WSDL 1.1** (2001) is the most widely deployed; **WSDL 2.0** is a W3C Recommendation (2007). Governed by the **W3C**, remains critical in legacy enterprise and government integrations.

**Human URL:** [https://www.w3.org/TR/wsdl/](https://www.w3.org/TR/wsdl/)

#### Properties

- [Documentation (WSDL 2.0 Primer)](https://www.w3.org/TR/wsdl20-primer/)
- [WSDL 1.1 Note](https://www.w3.org/TR/wsdl/)
- [WSDL 2.0 Recommendation](https://www.w3.org/TR/wsdl20/)
- [SOAP 1.2 Recommendation](https://www.w3.org/TR/soap12-part1/)
- [Specification Record Example](examples/wsdl-soap-example.json)

### JSON-RPC 2.0

A stateless, light-weight remote procedure call protocol encoded in JSON. Widely used in blockchain/Web3 APIs (Ethereum, Bitcoin), IDE language servers (LSP), and developer tooling. **2.0** (2010) is the stable revision. Released into the public domain.

**Human URL:** [https://www.jsonrpc.org/](https://www.jsonrpc.org/)

#### Properties

- [Documentation](https://www.jsonrpc.org/)
- [JSON-RPC 2.0 Specification](https://www.jsonrpc.org/specification)
- [Specification Record Example](examples/json-rpc-example.json)

### Tinybird API Spec

The Tinybird API specification is a vendor-defined, declarative format for describing analytics endpoints (pipes), data sources, and parameters backed by ClickHouse. Documented here as a representative example of vendor-specific specification formats that govern modern data API products outside of the OpenAPI/AsyncAPI mainline. **MIT** licensed (SDKs/CLI).

**Human URL:** [https://www.tinybird.co/docs](https://www.tinybird.co/docs)

#### Properties

- [Documentation](https://www.tinybird.co/docs)
- [API Reference](https://www.tinybird.co/docs/api-reference)
- [GitHub Organization](https://github.com/tinybirdco)
- [Specification Record Example](examples/tinybird-example.json)

## Common Properties

- [Repository](https://github.com/api-evangelist/specifications)
- [Specification Record JSON Schema](json-schema/specification-record-schema.json)
- [Specification Record JSON Structure](json-structure/specification-record-structure.json)
- [API Specifications JSON-LD Context](json-ld/specifications-context.jsonld)
- [API Specifications Vocabulary](vocabulary/specifications-vocabulary.yml)

## Features

| Name | Description |
|------|-------------|
| HTTP Request/Response Specifications | OpenAPI, RAML, API Blueprint, and historically WSDL — describing synchronous HTTP APIs. |
| Event-Driven Specifications | AsyncAPI for channels, operations, and messages across brokers; combined with Avro/Protobuf for payloads. |
| Service Interface Definition Languages (IDLs) | gRPC/Protobuf, Smithy, TypeSpec, GraphQL SDL, and WSDL — protocol-agnostic service contracts that emit clients and other specs. |
| Schema Languages | JSON Schema (de facto, embedded in OpenAPI/AsyncAPI) and JSON Structure (emerging) — describing data shapes. |
| RPC Protocol Specifications | JSON-RPC 2.0 and gRPC — describing RPC method calls and their payloads. |
| Vendor-Defined Specifications | Vendor-specific formats (e.g. Tinybird) that govern modern API products, often emitting OpenAPI as a derived artifact. |

## Use Cases

| Name | Description |
|------|-------------|
| Specification Discovery and Cataloging | Maintain an enterprise inventory of specifications used across internal and partner APIs, mapped to governing bodies and tooling. |
| Multi-Format Code Generation | Author in TypeSpec or Smithy and emit OpenAPI, JSON Schema, and Protobuf to generate SDKs across protocols. |
| Event-Driven Architecture Contracts | Use AsyncAPI alongside Avro/Protobuf to define event schemas, channels, and operations for streaming systems. |
| Governance and Linting Across Specs | Apply Spectral or similar linters against OpenAPI, AsyncAPI, and JSON Schema artifacts as part of an API governance program. |
| Legacy SOAP/WSDL Modernization | Migrate legacy WSDL/SOAP interfaces to OpenAPI-described REST or gRPC services as part of modernization initiatives. |

## Integrations

| Name | Description |
|------|-------------|
| Spectral | Open-source linting engine (Stoplight) for OpenAPI, AsyncAPI, and JSON Schema — the de facto governance engine. |
| Redocly CLI | CLI for linting, bundling, and rendering OpenAPI specs; enforces style guides and integrates with CI. |
| AsyncAPI Generator | Template-driven code and documentation generator for AsyncAPI specs across languages and brokers. |
| Protoc / Buf | The canonical Protobuf compiler and Buf's modern toolchain for linting, breaking-change detection, and codegen. |
| Smithy CLI | AWS-maintained CLI for compiling Smithy models and generating OpenAPI, JSON Schema, and SDK artifacts. |
| TypeSpec Compiler | Microsoft-maintained compiler that emits OpenAPI 3, JSON Schema, Protobuf, and other artifacts from TypeSpec sources. |

## Artifacts

Machine-readable artifacts organized by format.

### JSON Schema

- [Specification Record Schema](json-schema/specification-record-schema.json) — Normalized schema for describing any API specification language (name, version, governing body, license, format, tooling).

### JSON Structure

- [Specification Record Structure](json-structure/specification-record-structure.json) — JSON Structure counterpart aligned with the v0 core meta-schema.

### JSON-LD

- [API Specifications Context](json-ld/specifications-context.jsonld) — Maps the specification record terms to schema.org `SoftwareSourceCode`, `Organization`, and `CreativeWork` plus the local `spec:` namespace.

### Examples

- [OpenAPI](examples/openapi-example.json)
- [AsyncAPI](examples/asyncapi-example.json)
- [JSON Schema](examples/json-schema-example.json)
- [JSON Structure](examples/json-structure-example.json)
- [GraphQL SDL](examples/graphql-example.json)
- [gRPC / Protobuf](examples/grpc-protobuf-example.json)
- [Smithy](examples/smithy-example.json)
- [TypeSpec](examples/typespec-example.json)
- [RAML](examples/raml-example.json)
- [API Blueprint](examples/api-blueprint-example.json)
- [WSDL / SOAP](examples/wsdl-soap-example.json)
- [JSON-RPC 2.0](examples/json-rpc-example.json)
- [Tinybird](examples/tinybird-example.json)

## Vocabulary

- [API Specifications Vocabulary](vocabulary/specifications-vocabulary.yml) — Unified taxonomy mapping 13 specifications, 9 resources, 7 actions, 6 workflows, and 5 personas across the API specification landscape.

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
