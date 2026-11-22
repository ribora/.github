# ribora

Composable Go packages and code generators for building services. The wiring, the
input binding and the SQL mapping are decided at generation time and checked by the
compiler, so what would usually be reflection and runtime surprises becomes ordinary
Go you can read, step through and refactor.

Every module stands on its own. Take one, take a few, or take `waffle`, which is the
path through all of them.

## Generators

| | |
|---|---|
| [diogen](https://github.com/ribora/diogen) | Dependency injection. The wiring is Go — `di.Wire`, `di.Define` — and the generator reads it and writes a plain container. Nothing from diogen is imported at run time. |
| [whisk](https://github.com/ribora/whisk) | Input binding and validation from struct tags, generated rather than reflected. |
| [convert](https://github.com/ribora/convert) | DTO ↔ domain conversion over goverter, with proto enums and wrappers handled. |

## Core

| | |
|---|---|
| [failure](https://github.com/ribora/failure) | Typed errors with a stable type code, a payload and a stack, which survive a JSON or gRPC boundary with their identity intact. |
| [pry](https://github.com/ribora/pry) | Logging, with a recorder a test can assert against. |
| [session](https://github.com/ribora/session) | The request's identity and trace, carried through the context. |
| [hilton](https://github.com/ribora/hilton) | One facade over OpenTelemetry traces and metrics, and a no-op for when you want neither. |
| [env](https://github.com/ribora/env) | Configuration from the environment, with what is missing reported at start-up. |
| [criteria](https://github.com/ribora/criteria) | Query expressions, parsed and composed. |

## Transports

| | |
|---|---|
| [http](https://github.com/ribora/http) | Server and client, OpenAPI, protobuf-JSON. |
| [grpc](https://github.com/ribora/grpc) | Server and client, with the interceptor chain already in the right order. |
| [amqp](https://github.com/ribora/amqp) | RabbitMQ publishing and consuming. |

## Storage

| | |
|---|---|
| [sql](https://github.com/ribora/sql) | Query building, repositories generated from your models, and a test harness that brings up a real database in a container. |
| [redis](https://github.com/ribora/redis) | Redis, with the same kind of harness. |
| [elastic](https://github.com/ribora/elastic) | Elasticsearch, likewise. |

## The whole path

| | |
|---|---|
| [waffle](https://github.com/ribora/waffle) | A meta-framework that connects the packages above into one shape: a CLI that scaffolds a service, its domains and its transports, an application lifecycle, and the component-test harness that boots the real container over real infrastructure. |

---

These packages were developed at `gitlab.com/gorib` and moved here in November 2026.
The old repositories are frozen and stay readable for services that have not moved yet.
