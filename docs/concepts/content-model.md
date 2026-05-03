**Browse:** [README](../../README.md) · [Home](../index.md) · [Getting Started](../getting-started.md) · [API](../api-reference.md) · [Auth](../authentication.md) · [Webhooks](../webhooks.md) · [FAQ](../faq.md) · [Concepts](../concepts/content-model.md) · [GraphQL](../api/graphql.md) · [Rate Limits](../api/rate-limits.md) · [Python SDK](../sdks/python.md) · [JS SDK](../sdks/javascript.md) · [React Quickstart](../guides/quickstart-react.md) · [Migrate](../guides/migrate-from-wordpress.md) · [Deployment](../ops/deployment.md) · [CLI](../reference/cli.md) · [Glossary](../reference/glossary.md)

---

# Content Model

Your content model is the foundation of everything you do in Quillship. It defines the shape of your content, how pieces relate to each other, and what your editors see when they create new entries. A well-designed content model makes your team faster and your developers happier. A poorly-designed one creates friction at every step.

The content model is composed of content types, fields, and relationships. Content types are like templates — they define what fields exist for a particular kind of content. An article content type might have fields for title, body, author, and publication date. A product content type might have fields for name, price, description, and images. You define content types in the schema, which can be edited through the dashboard or programmatically through the schema API.

Fields are the building blocks of content types. Quillship supports many different field types: text, rich text, number, boolean, date, media, reference, and more. Each field has options that control its behavior — required vs optional, validation rules, default values, and so on. Reference fields are particularly powerful because they let you connect content types to each other, creating relationships that mirror the structure of your business.

When designing your content model, think about reuse. The same field can be used across multiple content types, and the same content type can be referenced from multiple places. Don't duplicate — reference. This makes your content easier to maintain and your editorial team happier because they can update something in one place and see the change everywhere.

There are also some common patterns to be aware of. The page builder pattern lets editors compose pages from reusable blocks. The localization pattern lets you serve content in multiple languages. The variant pattern lets you have different versions of the same content for different audiences. We support all of these, though some require careful schema design. Talk to our solutions team if you're tackling something complex.