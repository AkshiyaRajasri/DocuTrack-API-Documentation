# JWT Authentication Flow

This document describes the JWT-based authentication flow used by DocuTrack APIs.

## Authentication Steps

1. Client sends credentials to `/auth/login`
2. Backend validates username and password
3. On success, backend generates a JWT access token
4. JWT token is returned to the client
5. Client includes JWT in `Authorization` header for all secured APIs

## Authorization Header Format

Authorization: Bearer <JWT_TOKEN>
## Token Validation

For every secured request:

- JWT signature is verified
- Token expiration is checked
- User identity is extracted from token claims
- Request is authorized based on user roles and permissions

## Common Authentication Failures

- Invalid credentials
- Expired JWT token
- Malformed Authorization header
- Missing Bearer token

