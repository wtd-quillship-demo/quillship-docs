**Browse:** [README](../../README.md) · [Home](../index.md) · [Getting Started](../getting-started.md) · [API](../api-reference.md) · [Auth](../authentication.md) · [Webhooks](../webhooks.md) · [FAQ](../faq.md) · [Concepts](../concepts/content-model.md) · [GraphQL](../api/graphql.md) · [Rate Limits](../api/rate-limits.md) · [Python SDK](../sdks/python.md) · [JS SDK](../sdks/javascript.md) · [React Quickstart](../guides/quickstart-react.md) · [Migrate](../guides/migrate-from-wordpress.md) · [Deployment](../ops/deployment.md) · [CLI](../reference/cli.md) · [Glossary](../reference/glossary.md)

---

# Rate Limits

Quillship enforces rate limits to keep the platform stable for everyone.

## Limits by plan

| Plan | Read req/min | Write req/min | Bulk batch size |
|------|-------------|---------------|-----------------|
| Free | 200 | 20 | 50 |
| Pro | 1,000 | 100 | 500 |
| Enterprise | Custom | Custom | Custom |

- **Read requests** — GET requests and GraphQL queries. Authenticated requests get higher limits. Larger responses count more against your limit.
- **Write requests** — POST, PATCH, PUT, DELETE, and GraphQL mutations. More expensive to process.
- **Bulk operations** — A bulk request counts as a single request against your rate limit, but operations within it are subject to batch-level limits. See [bulk operations guide](../guides/migrate-from-wordpress.md) for details.

## Response headers

When you make an API request, Quillship returns the following rate limit headers:

```
HTTP/1.1 200 OK
X-RateLimit-Limit: 200
X-RateLimit-Remaining: 195
X-RateLimit-Reset: 1717045200
```

| Header | Description |
|--------|-------------|
| `X-RateLimit-Limit` | Maximum requests allowed per window |
| `X-RateLimit-Remaining` | Requests remaining in current window |
| `X-RateLimit-Reset` | Unix timestamp when the window resets |

## Example 429 response

When you exceed a rate limit, Quillship returns a `429 Too Many Requests` response:

```
HTTP/1.1 429 Too Many Requests
Retry-After: 60
X-RateLimit-Limit: 200
X-RateLimit-Remaining: 0
X-RateLimit-Reset: 1717045200
Content-Type: application/json

{
  "error": "rate_limit_exceeded",
  "message": "Rate limit exceeded. Retry after 60 seconds.",
  "retry_after": 60
}
```

## Best practices

- **Read `Retry-After`** — The `Retry-After` header tells you how many seconds to wait before retrying.
- **Exponential backoff** — If you hit a rate limit, wait the suggested time, then retry with exponential backoff.
- **Cache responses** — Cache API responses locally to reduce unnecessary requests.
- **Use bulk endpoints** — When performing many operations, use bulk endpoints to reduce request count.
- **Monitor headers** — Track `X-RateLimit-Remaining` to proactively slow down before hitting limits.
