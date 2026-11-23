# Client integration guide

Status: planning guide for the early MVP. The public customer API and sending quickstart are not released yet.

## Intended client flow

1. Create an account and verify your email address.
2. Create a project.
3. Add a sending domain and obtain its DNS requirements.
4. Publish the required records through your DNS provider and verify them.
5. Configure a sender and obtain credentials restricted to the project and required operations.
6. Send one transactional email to an address you control.
7. Read the message result, transport events, and usage for the same operation.

API base URLs, authentication details, DNS values, and request examples must come from the accepted version of the customer contract. Do not infer them from the product name or a website mockup.

## Reliable integration

### One application event, one send intent

Persist an application event identifier and use it consistently when the accepted API provides idempotency.

Keep the same payload and idempotency key when retrying the same operation under the documented contract. A changed payload represents a separate decision.

A timeout does not prove that sending failed. Do not generate a new key or automatically switch providers after an uncertain result. First reconcile the original operation through the supported API.

### Distinguish the outcomes

API acceptance, acceptance by a sending MTA, acceptance by the recipient's server, and observation in a mailbox are different events.

Keep the application event identifier and the returned message identifier together. Use documented transport events to explain the result. Do not label an accepted request as an inbox delivery.

### Keep access scoped

Store credentials server-side. Grant only the project and operations the integration needs. Support revocation without sharing administrative server access.

### Let the client control DNS

The intended Inboxes.Run workflow returns DNS requirements and verifies the resulting records. DNS changes remain under the client's provider access.

Review existing records before applying changes. Preserve unrelated mail routing.

## Integration through an AI agent

The intended customer MCP connection exposes the same project permissions and message results as the API.

A customer integration should not require SSH, root access, or an administrative Inboxes.Run connector. A private customer installation must be verified before it is described as available.

## Before a runnable example is released

- The supported customer API version and accessible environment are identified.
- Authentication and domain setup work through the documented client flow.
- A controlled real message is linked to its API result and transport evidence.
- Retries, ambiguous results, credential revocation, and project isolation are checked.
- Quota usage agrees with the accepted accounting contract.
- The example contains placeholders, not credentials or customer data.
- Setup instructions have been reproduced from a clean client environment.

Until those checks pass, documentation and UI examples should clearly show their preview status.
