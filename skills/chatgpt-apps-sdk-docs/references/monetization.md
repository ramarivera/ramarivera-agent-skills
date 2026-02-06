# Monetization

## Recommended

- Use external checkout on your own domain for most apps.

## Instant Checkout (Beta)

- Available to select partners.
- Flow:
1. MCP tool returns checkout session data in `structuredContent`.
2. Widget renders cart preview.
3. Widget calls `window.openai.requestCheckout(session)`.
4. Host returns order data or error.
5. MCP `complete_checkout` tool finalizes order.

## Notes

- Use ACP checkout spec for session and order payloads.
- Provide legal links like terms and privacy.
