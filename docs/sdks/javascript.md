**Browse:** [README](../../README.md) · [Home](../index.md) · [Getting Started](../getting-started.md) · [API](../api-reference.md) · [Auth](../authentication.md) · [Webhooks](../webhooks.md) · [FAQ](../faq.md) · [Concepts](../concepts/content-model.md) · [GraphQL](../api/graphql.md) · [Rate Limits](../api/rate-limits.md) · [Python SDK](../sdks/python.md) · [JS SDK](../sdks/javascript.md) · [React Quickstart](../guides/quickstart-react.md) · [Migrate](../guides/migrate-from-wordpress.md) · [Deployment](../ops/deployment.md) · [CLI](../reference/cli.md) · [Glossary](../reference/glossary.md)

---

# JavaScript SDK

The Quillship JavaScript SDK is the recommended way to interact with our API from JavaScript and TypeScript applications, whether you're running in Node, Deno, Bun, or the browser.

## Installation

Install via your favorite package manager:

```
npm install @quillship/client
```

## Basic usage

```
import { quillship } from '@quillship/client';

const client = quillship({ token: 'your-token' });

const result = client.content.list({ contentType: 'article' });
```

You can configure the client with various options including timeout, retry behavior, and a custom fetch implementation.

## Working with content

```
const article = client.content.create({
  contentType: 'article',
  fields: {
    title: 'Hello',
    body: 'World'
  }
});

const fetched = client.content.get(article.id);
const updated = client.content.update(article.id, { fields: { title: 'Updated' } });
client.content.delete(article.id);
```

## TypeScript

The SDK ships with TypeScript types out of the box. If you're using TypeScript, you'll get autocomplete and type checking for all SDK methods. For typed content (where each content type has known fields), you can pass a generic type parameter.

## Browser usage

For browser usage, make sure your token has the appropriate scope. Don't ship admin tokens to the browser — use a public read-only token instead. The SDK automatically detects browser environments and applies appropriate defaults.

## Error handling

The SDK throws on errors. Catch QuillshipError or one of its subclasses for fine-grained handling.