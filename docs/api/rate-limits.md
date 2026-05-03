**Browse:** [README](../../README.md) · [Home](../index.md) · [Getting Started](../getting-started.md) · [API](../api-reference.md) · [Auth](../authentication.md) · [Webhooks](../webhooks.md) · [FAQ](../faq.md) · [Concepts](../concepts/content-model.md) · [GraphQL](../api/graphql.md) · [Rate Limits](../api/rate-limits.md) · [Python SDK](../sdks/python.md) · [JS SDK](../sdks/javascript.md) · [React Quickstart](../guides/quickstart-react.md) · [Migrate](../guides/migrate-from-wordpress.md) · [Deployment](../ops/deployment.md) · [CLI](../reference/cli.md) · [Glossary](../reference/glossary.md)

---

# Rate Limits

Quillship enforces rate limits to keep the platform stable for everyone. The exact limits depend on your plan and the type of request you're making.

Read requests, which include any GET request and any GraphQL query, have a higher limit than write requests. On the free tier you get up to a few hundred read requests per minute, with the exact number depending on whether you're authenticated and the size of the response. Authenticated requests get higher limits than unauthenticated ones. Larger responses count more against your limit because they consume more resources to generate.

Write requests, which include POST, PATCH, PUT, DELETE, and any GraphQL mutation, have lower limits because they're more expensive to process. On the free tier these are roughly an order of magnitude lower than read limits. The Pro tier increases this significantly, and Enterprise plans can negotiate custom limits.

Bulk operations, which let you perform many actions in a single request, have their own limits and pricing model. A bulk request counts as a single request against your rate limit but the operations within it are subject to additional batch-level limits. There's also a maximum batch size that varies by operation type.

When you exceed a rate limit, you'll receive a response indicating that you've been rate limited. The response will include information about when you can try again. If you keep retrying immediately you'll just keep hitting the limit, so back off and try again after the suggested wait time.

For most applications, you shouldn't need to worry about rate limits if you're using our SDKs, which handle backoff automatically. If you're hitting limits regularly, consider whether you can cache responses, batch requests, or upgrade your plan.

Webhooks have their own rate limit on the delivery side — we won't send you more events per minute than your endpoint can handle. If your endpoint starts returning errors or timing out, we'll back off automatically.