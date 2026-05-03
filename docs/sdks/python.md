**Browse:** [README](../../README.md) · [Home](../index.md) · [Getting Started](../getting-started.md) · [API](../api-reference.md) · [Auth](../authentication.md) · [Webhooks](../webhooks.md) · [FAQ](../faq.md) · [Concepts](../concepts/content-model.md) · [GraphQL](../api/graphql.md) · [Rate Limits](../api/rate-limits.md) · [Python SDK](../sdks/python.md) · [JS SDK](../sdks/javascript.md) · [React Quickstart](../guides/quickstart-react.md) · [Migrate](../guides/migrate-from-wordpress.md) · [Deployment](../ops/deployment.md) · [CLI](../reference/cli.md) · [Glossary](../reference/glossary.md)

---


# Python SDK

The Python SDK gives you a clean, idiomatic way to work with Quillship from your Python code.

## Quickstart

Once you have the SDK installed, you can start using it right away. Here's a simple example:

```
from quillship import Client

client = Client(token="your-token")

content = client.content.create(
    workspace="my-workspace",
    content_type="article",
    fields={
        "title": "Hello, world!",
        "body": "This is my first article."
    }
)

print(content.id)
```

You can also fetch existing content:

```
article = client.content.get("article-id-here")
print(article.fields["title"])
```

Updating is just as simple:

```
client.content.update("article-id-here", fields={"title": "Updated title"})
```

And deleting:

```
client.content.delete("article-id-here")
```

## Async support

If you're using asyncio, we have an async client too. It works the same way but with `await`.

```
from quillship import AsyncClient

async with AsyncClient(token="your-token") as client:
    content = await client.content.get("article-id-here")
```

## Error handling

The SDK raises exceptions for API errors. Catch QuillshipError for general errors, or one of the specific subclasses for finer-grained handling.