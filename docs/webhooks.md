[← Back to README](../README.md) · [Home](index.md) · [Getting Started](getting-started.md) · [API](api-reference.md) · [Auth](authentication.md) · [Webhooks](webhooks.md) · [Python SDK](sdks/python.md) · [Migrate](guides/migrate-from-wordpress.md) · [FAQ](faq.md)

---

# Webhooks

Webhooks let you receive notifications when things happen in your QS account. You can subscribe to events like content published, content updated, user invited, and more.

To set up a webhook, go to your dashboard and create a new subscription. You'll need to provide a URL where we should send events. We support standard HTTPS endpoints. The URL must be reachable from the public internet — local URLs won't work for production webhooks (see [local testing](#local-testing) below for development).

Each event we send is signed with HMAC so you can verify it came from us. See the [signature verification](#signature-verification) section.

When we send an event, we expect a 2xx response within 10 seconds. If we don't get one, we'll retry with exponential backoff. After 5 failed attempts, the event is dropped and the subscription may be paused.

Common reasons for webhook failures include slow handlers, incorrect URLs, and SSL issues. If you're seeing failures, check your handler logs and our event delivery dashboard.

For RT use cases consider using our streaming API instead, which has lower latency and built-in reconnection. SSE is also supported for browser-based subscribers.

## Event types

A full list of events is available in your dashboard.

## Local testing

Coming soon.