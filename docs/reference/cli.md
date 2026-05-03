**Browse:** [README](../../README.md) · [Home](../index.md) · [Getting Started](../getting-started.md) · [API](../api-reference.md) · [Auth](../authentication.md) · [Webhooks](../webhooks.md) · [FAQ](../faq.md) · [Concepts](../concepts/content-model.md) · [GraphQL](../api/graphql.md) · [Rate Limits](../api/rate-limits.md) · [Python SDK](../sdks/python.md) · [JS SDK](../sdks/javascript.md) · [React Quickstart](../guides/quickstart-react.md) · [Migrate](../guides/migrate-from-wordpress.md) · [Deployment](../ops/deployment.md) · [CLI](../reference/cli.md) · [Glossary](../reference/glossary.md)

---

# CLI Reference

The Quillship CLI lets you manage content, schemas, and deployments from your terminal.

## Installation

The CLI is part of the main package, so if you've installed `@quillship/client` you have it.

## Commands

### init

Initializes a new Quillship project in the current directory.

### login

Authenticates you against your Quillship account.

### logout

Logs you out.

### config

Manages local configuration.

### content

Manages content. Has several subcommands.

### schema

Manages your content schema. Has several subcommands.

### export

Exports content from a workspace.

### import

Imports content into a workspace.

### deploy

Deploys schema changes from your local environment to a remote one.

### env

Manages environments.

### whoami

Shows the currently authenticated user.

## Global flags

There are a few flags that work with any command, including verbose output, dry run, and pointing at a different environment.

## Configuration

The CLI reads from a config file in your home directory. You can also set things via environment variables.

## Troubleshooting

If a command isn't working, try running it with verbose output to see what's happening. If you're getting auth errors, try logging out and back in.