# Authentication (OAuth 2.1)

## Required Pieces

- Protected resource metadata endpoint on the MCP server.
- OAuth discovery document on the auth server.
- PKCE with S256 supported.
- Dynamic client registration supported.

## Protected Resource Metadata

- Serve `/.well-known/oauth-protected-resource`.
- Include `resource`, `authorization_servers`, and optional `scopes_supported`.
- Return `WWW-Authenticate` header on 401 with `resource_metadata` URL.

## OAuth Discovery

- Provide `authorization_endpoint`, `token_endpoint`, and `registration_endpoint`.
- List `code_challenge_methods_supported` with `S256`.

## Redirect URIs

- Allow `https://chatgpt.com/connector_platform_oauth_redirect`.
- Allow review redirect `https://platform.openai.com/apps-manage/oauth`.

## Tool-Level Auth

- Use `securitySchemes` per tool with `noauth` or `oauth2` scopes.
- Return `_meta["mcp/www_authenticate"]` in error results to trigger linking UI.

## Token Verification

- Verify signature, issuer, audience/resource, expiry, and scopes.
- Reject invalid tokens with 401 and `WWW-Authenticate` header.
