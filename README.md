# Inboxes.Run

Send email from your app.

Inboxes.Run is building transactional email delivery for SaaS applications, with an API, clear sending history, and tools for your own AI agent.

## Project status

Early development. The backend has a private test deployment. Public registration, external email delivery, payments, and an installable customer MCP connection have not yet completed end-to-end acceptance.

This repository is the home for public client integration materials. It currently contains documentation. A production SDK, public API endpoint, and runnable sending quickstart are not released here yet.

## MVP scope

- Connect and verify a sending domain.
- Send application emails with your own sender name, HTML or plain text, and personalization.
- Separate projects and use scoped credentials.
- Inspect message history, usage, domain checks, and actionable errors.
- Connect your own AI agent through a customer MCP integration.
- Understand quotas and charges before sending.

These are the intended MVP capabilities. They are not a statement that the public service is available today.

## Integration guide

Read the [integration guide](docs/integration-guide.md) for the intended client flow, retry handling, and the evidence required before a sending example is published.

Client examples will be added against an accepted customer API contract. Each example should identify its supported version and verification status.

## License

A license has not been selected for this repository.
