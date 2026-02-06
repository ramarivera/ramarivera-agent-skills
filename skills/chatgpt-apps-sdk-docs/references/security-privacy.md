# Security and Privacy

## Principles

- Use least privilege and explicit consent.
- Validate all inputs and assume prompt injection.
- Keep structuredContent minimal and safe.

## Data Handling

- Do not embed secrets in tool results or widget state.
- Redact PII in logs and limit retention.

## Network and CSP

- Widgets run in a sandbox and must obey CSP.
- Subframes are blocked unless allowed by `frameDomains`.

## Auth

- Use OAuth 2.1 with PKCE and dynamic client registration.
- Verify tokens on every call.
