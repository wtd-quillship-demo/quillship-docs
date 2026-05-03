**Browse:** [README](../../README.md) · [Home](../index.md) · [Getting Started](../getting-started.md) · [API](../api-reference.md) · [Auth](../authentication.md) · [Webhooks](../webhooks.md) · [FAQ](../faq.md) · [Concepts](../concepts/content-model.md) · [GraphQL](../api/graphql.md) · [Rate Limits](../api/rate-limits.md) · [Python SDK](../sdks/python.md) · [JS SDK](../sdks/javascript.md) · [React Quickstart](../guides/quickstart-react.md) · [Migrate](../guides/migrate-from-wordpress.md) · [Deployment](../ops/deployment.md) · [CLI](../reference/cli.md) · [Glossary](../reference/glossary.md)

---

# Rate Limits

Quillship enforces rate limits to keep the platform stable for everyone. The exact limits depend on your plan and the type of request you're making.

## Limits by Plan

| Plan       | Read Requests (per minute) | Write Requests (per minute) | Bulk Operations (per minute) |
|------------|----------------------------|-----------------------------|-----------------------------|
| Free       | 300                        | 30                          | 5                           |
| Pro        | 3,000                      | 300                         | 50                          |
| Enterprise | Custom (contact sales)     | Custom (contact sales)      | Custom (contact sales)      |

**Read requests** include any GET request and any GraphQL query.

**Write requests** include POST, PATCH, PUT, DELETE, and any GraphQL mutation.

**Bulk operations** let you perform many actions in a single request. A bulk request counts as one request against your rate limit, but the operations within it are subject to additional batch-level limits (max 100 operations per batch on Free/Pro plans).

## Response Headers

Every API response includes rate limit headers so you can track your usage:

```http
X-RateLimit-Limit: 300
X-RateLimit-Remaining: 287
X-RateLimit-Reset: 1672531200
```

**`X-RateLimit-Limit`**: Maximum requests allowed in the current time window

**`X-RateLimit-Remaining`**: Number of requests remaining in the current time window

**`X-RateLimit-Reset`**: Unix timestamp when the rate limit resets

## Example 429 Response

When you exceed a rate limit, you'll receive a `429 Too Many Requests` response:

```http
HTTP/1.1 429 Too Many Requests
Content-Type: application/json
X-RateLimit-Limit: 300
X-RateLimit-Remaining: 0
X-RateLimit-Reset: 1672531260
Retry-After: 60

{
  "error": {
    "type": "rate_limit_exceeded",
    "message": "Rate limit exceeded. Please retry after 60 seconds.",
    "retry_after": 60
  }
}
```

The `Retry-After` header tells you how many seconds to wait before retrying.

## Best Practices

- **Check rate limit headers** in your responses to track usage and avoid hitting limits
- **Implement exponential backoff** when you receive a `429` response
- **Respect the `Retry-After` header** - don't retry immediately or you'll keep hitting the limit
- **Cache responses** when possible to reduce API calls
- **Use webhooks** instead of polling for real-time updates
- **Use our SDKs** - they handle backoff and retries automatically

Authenticated requests get higher priority than unauthenticated ones. If you're hitting limits regularly, consider caching, batching, or upgrading your plan.

For webhook delivery limits, see [Webhooks](../webhooks.md).
