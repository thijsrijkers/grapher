# Grapher

<p align="center"><img src="assets/grapher.png" width="300"></p>

Create a set of easy‑to‑use Go packages. The implementation will be **low‑level, and library‑oriented**, suitable for both standalone GraphQL servers.

## **High‑Level Architecture**

1. **HTTP Interface**
   - Exposes a `/graphql` endpoint.
   - Accepts POST requests containing GraphQL queries.
   - Returns responses in standard GraphQL JSON format.

2. **Query Parser**
   - Converts incoming GraphQL queries into an internal representation.
   - Handles field selection, arguments, and nested queries (basic or advanced over time).
   - Serves as the core of low-level query processing.

3. **Schema & Resolvers**
   - Defines types, fields, and arguments.
   - Each field maps to a resolver function that produces data.
   - Supports queries, mutations, and eventually entity resolution for subgraphs.

4. **Execution Engine**
   - Matches parsed queries to the schema.
   - Executes resolver functions.
   - Collects results and formats them into a GraphQL-compliant response.

5. **Subgraph Layer (Future)**
   - Implements `_service` endpoint exposing SDL.
   - Implements `_entities` endpoint for federated entity resolution.
   - Adds metadata directives (e.g., `@key`) for integration with Apollo Gateway.
   - Enables the server to participate in a larger federated schema.

## **Future Extensions**

- Support for mutations and subscriptions.
- Nested queries and complex argument handling.
- Authentication and authorization layers.
- Improved error handling and validation.
- Integration with databases or external APIs.
- Full Apollo Federation support as a modular subgraph.

## **Outcome**

By following this architecture, the project will provide:

- A **fully low-level, from-scratch GraphQL server in Go**.
- A **foundation for modular, federated GraphQL services**.
- Flexibility to expand, optimize, and integrate with larger systems.
