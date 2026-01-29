# JWT Token Lifecycle

This document describes the lifecycle of JWT access tokens used by DocuTrack.

## Token Generation

- JWT token is generated after successful authentication
- Token contains:
  - User ID
  - Username
  - Issued time (iat)
  - Expiration time (exp)
  - User roles/authorities

## Token Expiration

- Access tokens have a fixed expiration time
- Example: 1 hour (3600 seconds)
- Expired tokens are rejected by backend filters

## Token Validation Flow

For each secured API request:

1. Extract token from Authorization header
2. Validate token signature
3. Check token expiration
4. Extract user identity and roles
5. Attach user context to request

## Token Revocation Scenarios

Although JWT is stateless, tokens may be invalidated in these cases:

- User account is disabled
- User password is reset
- Admin manually revokes user access

In these cases, backend enforces additional checks to reject existing tokens.

## Common Token Errors

- Token expired
- Invalid signature
- Token malformed
- Token missing required claims

