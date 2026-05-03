[← Back to README](../README.md) · [Home](index.md) · [Getting Started](getting-started.md) · [API](api-reference.md) · [Auth](authentication.md) · [Webhooks](webhooks.md) · [Python SDK](sdks/python.md) · [Migrate](guides/migrate-from-wordpress.md) · [FAQ](faq.md)

---

# Authentication

All Quillship API requests require authentication. We use API tokens for this.

To authenticate a request, include your token in the request. The token should be sent in the appropriate header. Make sure to keep your token safe — anyone with your token can access your account.

If your request fails authentication, you'll get back a 401 response. Double-check that your token is valid and properly formatted.

Tokens can be revoked at any time from your account settings. If you think your token has been compromised, revoke it immediately and generate a new one.

For server-to-server use cases, we recommend using a dedicated service token rather than a personal token. Service tokens have the same capabilities but are tied to a workspace rather than an individual user.

OAuth is also supported for applications that need to act on behalf of users. See the OAuth guide for more on that.