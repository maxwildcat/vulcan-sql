# vulcan-sql

Exposing analytical data to an application usually means writing an API layer around SQL queries. vulcan-sql turns templated SQL into REST APIs that AI agents and data apps can call, so you can keep query logic in SQL instead of custom request handlers.

## Features

- Build REST endpoints from SQL templates that accept API request parameters.
- Connect APIs to databases, data warehouses, and data lakes through VulcanSQL data-source integrations.
- Describe APIs with OpenAPI documents so clients and AI agents can inspect their interfaces.
- Cache query results with DuckDB to reduce repeated work on source databases.
- Deploy APIs with Docker or run them from the command line.

## Installation

Install Node.js and npm, then install the VulcanSQL CLI:

```sh
npm install --global @vulcan-sql/cli
```

**These commands use the upstream VulcanSQL CLI**, rather than a separate package published under this project's name. For current runtime requirements and data-source setup, see the [upstream installation guide](https://vulcansql.com/docs/get-started/installation).

## Usage

Create a workspace for an analytics API and start the development workflow:

```sh
vulcan init analytics-api
cd analytics-api
vulcan start
```

Follow the initialization prompts. Configure the workspace's data-source credentials and SQL templates for your database before you query your own data.

Each endpoint uses a SQL template. API inputs supply template variables, and VulcanSQL generates the query at request time. Keep credentials out of version control and use database permissions appropriate for the data you intend to expose.

For deployment, build the API and start the server:

```sh
vulcan build
vulcan serve
```

The [upstream examples](https://github.com/Canner/vulcan-sql-examples) provide reference projects for endpoint definitions and data-source configuration.

<!-- seorepo:network:start -->
## More tools from our network

- [**octo-cli**](https://github.com/boostlyapi/octo-cli) — CLI на Go для публикации данных из PostgreSQL, MSSQL и MySQL через бессерверные веб-сервисы в OpenFaaS или Knative. Конфигурация сервиса задаётся в YAML.
- [**tool**](https://github.com/boostlyapi/tool) — CLI на Go для Apache Kafka: чтение и отправка сообщений в JSON, просмотр топиков, управление смещениями consumer groups и базовое администрирование.
- [**docker-ikev2-vpn-server**](https://github.com/Cabral-it/docker-ikev2-vpn-server) — Docker-based IKEv2 VPN server with shared-secret authentication and .mobileconfig generation for iOS and macOS, based on gaomd/docker-ikev2-vpn-server.
- [**akrobateo**](https://github.com/Dyooooou/akrobateo) — A Go Kubernetes operator that exposes LoadBalancer services through node hostPorts using DaemonSets and synchronizes their load balancer addresses.
- [**node-hnsn**](https://github.com/ghb13/node-hnsn) — A TypeScript node for decentralized document timestamping with Bitcoin and IPFS, with an HTTP API for signed work claims and file uploads.
- [**wg-access-server**](https://github.com/EngHirsi/wg-access-server) — A WireGuard VPN server with a web UI for user authentication, one-click device registration, QR-code setup, and configurable network isolation.
<!-- seorepo:network:end -->

## License

Apache-2.0. This project is based on [Canner/vulcan-sql](https://github.com/Canner/vulcan-sql). Retain the upstream copyright and license notices, and include any applicable NOTICE file when redistributing derived code.
