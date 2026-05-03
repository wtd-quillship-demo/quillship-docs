**Browse:** [README](../../README.md) · [Home](../index.md) · [Getting Started](../getting-started.md) · [API](../api-reference.md) · [Auth](../authentication.md) · [Webhooks](../webhooks.md) · [FAQ](../faq.md) · [Concepts](../concepts/content-model.md) · [GraphQL](../api/graphql.md) · [Rate Limits](../api/rate-limits.md) · [Python SDK](../sdks/python.md) · [JS SDK](../sdks/javascript.md) · [React Quickstart](../guides/quickstart-react.md) · [Migrate](../guides/migrate-from-wordpress.md) · [Deployment](../ops/deployment.md) · [CLI](../reference/cli.md) · [Glossary](../reference/glossary.md)

---

# GraphQL API

Quillship exposes a fully-featured GraphQL API alongside our REST endpoints. Many teams prefer GraphQL because it lets you fetch exactly the fields you need in a single request, which is especially useful for content-heavy frontends.

The GraphQL endpoint is the same as the REST one, just with a different path. You authenticate the same way, with a Bearer token. The schema is generated automatically from your content model — every content type becomes a GraphQL type, and every field becomes a corresponding GraphQL field with appropriate types.

You can query for content using standard GraphQL syntax. Filtering, sorting, and pagination are all supported through arguments on the query fields. The query language is rich and expressive, but if you're new to GraphQL there's a learning curve. We recommend the official GraphQL tutorial as a starting point.

For mutations, the same auth applies, and the mutation names follow predictable patterns. There's a mutation for every standard CRUD operation on every content type. There are also some special mutations for things like publishing, unpublishing, and managing references.

Subscriptions are supported for real-time updates, though you'll need a WebSocket connection. The subscription endpoint is documented in the dashboard.

For exploring the schema, you can use any GraphQL client like Insomnia, Postman, or Apollo Studio. We also have a built-in playground at the appropriate URL where you can run queries interactively.

Performance considerations: GraphQL queries can be expensive if you're not careful. Use field-level pagination, avoid deep nesting where possible, and remember that complex queries count more against your rate limit than simple ones. The query complexity is calculated based on a number of factors.