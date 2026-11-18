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

## License

Apache-2.0. This project is based on [Canner/vulcan-sql](https://github.com/Canner/vulcan-sql). Retain the upstream copyright and license notices, and include any applicable NOTICE file when redistributing derived code.
