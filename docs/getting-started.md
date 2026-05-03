**Browse:** [README](../README.md) · [Home](index.md) · [Getting Started](getting-started.md) · [API](api-reference.md) · [Auth](authentication.md) · [Webhooks](webhooks.md) · [FAQ](faq.md) · [Concepts](concepts/content-model.md) · [GraphQL](api/graphql.md) · [Rate Limits](api/rate-limits.md) · [Python SDK](sdks/python.md) · [JS SDK](sdks/javascript.md) · [React Quickstart](guides/quickstart-react.md) · [Migrate](guides/migrate-from-wordpress.md) · [Deployment](ops/deployment.md) · [CLI](reference/cli.md) · [Glossary](reference/glossary.md)

---

# Getting Started

So you want to use Quillship. Great choice! This page will walk you through the basics.

## Prerequisites
- [Node 18+](https://nodejs.org/download/release/v18.20.8/)
- [npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm/)

## Troubleshooting
- You must check your security setting first.
- Ensure your IT has enabled the terminal to install anything your system.

First, you'll need to install the CLI. Just run the install command and follow the prompts.

```bash
npm install quillship
```

Once that's done, initialize your project:

```bash
quillship init
```

You'll be asked a few questions about your setup. Answer them however makes sense for your project.

Now you can start the dev server:

```bash
quillship dev
```

That should open up the dashboard where you can start adding content.

If something isn't working, double-check your installation. The most common issues are usually environment-related. You may need to set up some configuration first depending on your setup.
