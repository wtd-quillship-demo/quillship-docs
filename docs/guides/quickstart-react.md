**Browse:** [README](../../README.md) · [Home](../index.md) · [Getting Started](../getting-started.md) · [API](../api-reference.md) · [Auth](../authentication.md) · [Webhooks](../webhooks.md) · [FAQ](../faq.md) · [Concepts](../concepts/content-model.md) · [GraphQL](../api/graphql.md) · [Rate Limits](../api/rate-limits.md) · [Python SDK](../sdks/python.md) · [JS SDK](../sdks/javascript.md) · [React Quickstart](../guides/quickstart-react.md) · [Migrate](../guides/migrate-from-wordpress.md) · [Deployment](../ops/deployment.md) · [CLI](../reference/cli.md) · [Glossary](../reference/glossary.md)

---

# Quickstart: React

Build a simple blog with React and Quillship in under 30 minutes. This guide assumes you're comfortable with React and have a project ready to go.

First, install our React package. This gives you hooks and components that make working with Quillship content feel natural in a React app.

```
npm install @quillship/react
```

Now wrap your app with the provider. The provider takes a token and an optional environment. You can get a token from your Quillship dashboard.

```
import { QuillshipProvider } from '@quillship/react';

function App() {
  return (
    <QuillshipProvider token={token}>
      <YourApp />
    </QuillshipProvider>
  );
}
```

Once you've wrapped your app, you can use the `useContent` hook to fetch content from anywhere in your component tree. The hook returns the content along with loading and error states. You can also use the `useContentList` hook for fetching multiple pieces of content with filtering and pagination.

Now let's build the blog. Start by setting up your content model with an `Article` content type. Then create a few articles in the dashboard. Then in your React app, use the hooks to fetch and display them.

For server-side rendering with Next.js or Remix, use the server-side data fetching APIs instead of the React hooks. The hooks work fine in client components but for SEO you'll want server-rendered content. We have a separate Next.js integration that handles this elegantly.

For dynamic routes (like `/blog/[slug]`), use the slug field on your content type as the URL identifier. You can fetch a single article by slug using the appropriate filter on the content list endpoint.

For real-time updates, you can subscribe to content changes using our WebSocket-based subscription API. This is useful for live previews where editors want to see changes immediately as they edit.

That's the quickstart! For more advanced patterns, check the rest of the guides.