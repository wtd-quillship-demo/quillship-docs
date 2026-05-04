**Browse:** [README](../../README.md) · [Home](../index.md) · [Getting Started](../getting-started.md) · [API](../api-reference.md) · [Auth](../authentication.md) · [Webhooks](../webhooks.md) · [FAQ](../faq.md) · [Concepts](../concepts/content-model.md) · [GraphQL](../api/graphql.md) · [Rate Limits](../api/rate-limits.md) · [Python SDK](../sdks/python.md) · [JS SDK](../sdks/javascript.md) · [React Quickstart](../guides/quickstart-react.md) · [Migrate](../guides/migrate-from-wordpress.md) · [Deployment](../ops/deployment.md) · [CLI](../reference/cli.md) · [Glossary](../reference/glossary.md)

---

# Glossary

A list of terms used throughout the Quillship docs.

## Content concepts

### Content

Any piece of data stored in Quillship — articles, images, products, or custom types. Content belongs to a [workspace](#workspace) and is structured by its [content type](#content-type). See [Content model](../concepts/content-model.md).

### Content type

A schema that defines the structure of your content — what fields it has, their types, and validation rules. For example, a "Blog Post" content type might have fields for title, body, and publish date.

### Field

A single property within a [content type](#content-type). Fields have a name, type (text, number, date, etc.), and optional validation rules.

### Workspace

A container for your content, settings, and team members. Each workspace has its own [environments](#environment), [tokens](#token), and content. See [Getting Started](../getting-started.md).

### Environment

A version of your workspace used for staging changes before going live. Common environments include `development`, `staging`, and `production`. See [Deployment](../ops/deployment.md).

## Technical terms

### API

**Application Programming Interface.** A set of endpoints for programmatically interacting with Quillship — creating, reading, updating, and deleting content. Quillship supports both [REST](#rest) and [GraphQL](#graphql) APIs. See [API Reference](../api-reference.md).

### SDK

**Software Development Kit.** Pre-built libraries that make it easier to interact with the Quillship API in your language. See [Python SDK](../sdks/python.md) and [JavaScript SDK](../sdks/javascript.md).

### REST

**Representational State Transfer.** An architectural style for APIs that uses standard HTTP methods (GET, POST, PUT, DELETE) and URLs to interact with resources. Quillship's REST API returns JSON responses. See [API Reference](../api-reference.md).

### GraphQL

A query language for APIs that lets you request exactly the data you need in a single request. Unlike [REST](#rest), GraphQL uses a single endpoint and lets the client specify the response shape. See [GraphQL API](../api/graphql.md).

### CDN

**Content Delivery Network.** A network of distributed servers that cache static assets close to users for faster delivery. Quillship recommends fronting your frontend with a CDN for performance. See [Deployment](../ops/deployment.md).

### SSR

**Server-Side Rendering.** Rendering pages on the server and sending fully-formed HTML to the browser. Useful for SEO and fast initial page loads. See [React Quickstart](../guides/quickstart-react.md).

### ISR

**Incremental Static Regeneration.** A hybrid approach where static pages are regenerated in the background after a specified time. Combines the performance of static sites with the freshness of dynamic content.

### SSE

**Server-Sent Events.** A one-way streaming protocol where the server pushes updates to the client over a persistent HTTP connection. Quillship uses SSE for real-time notifications in the [webhooks](#webhook) system.

### HMAC

**Hash-based Message Authentication Code.** A cryptographic method used to verify the authenticity and integrity of messages. Quillship uses HMAC signatures to verify [webhook](#webhook) payloads. See [Authentication](../authentication.md).

### RT

**Real-Time streaming.** In Quillship's context, RT refers to the real-time content update streaming pattern via [SSE](#sse), where content changes are pushed to connected clients immediately. See [Webhooks](../webhooks.md).

### Webhook

An HTTP callback that Quillship sends to your server when specific events occur (e.g., content created, updated, or deleted). Webhooks use [HMAC](#hmac) signatures for verification. See [Webhooks](../webhooks.md).

### Token

A credential used to authenticate API requests. Tokens are associated with a specific [workspace](#workspace) and permission scope. Include tokens in the `Authorization` header as `Bearer <token>`. See [Authentication](../authentication.md).

### CMS

**Content Management System.** Software for creating, managing, and publishing digital content. Quillship is a headless CMS, meaning it provides content via [APIs](#api) without a built-in frontend.

### Rate limit

The maximum number of API requests allowed within a time window. Varies by plan — see [Rate Limits](../api/rate-limits.md).

### Bearer token

A type of access token included in the `Authorization` HTTP header as `Bearer <token>`. Quillship uses bearer tokens for API authentication. See [Authentication](../authentication.md).

### Mutation

In [GraphQL](#graphql), a mutation is an operation that modifies data (create, update, or delete). Contrasted with queries, which only read data. See [GraphQL API](../api/graphql.md).
