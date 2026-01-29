# Authentication Error Scenarios

This document lists common authentication-related errors and their causes.

## 401 Unauthorized

### Invalid Credentials
- Username or password is incorrect
- Authentication fails at login endpoint

### Expired JWT Token
- Access token expiration time exceeded
- Client must re-authenticate

### Missing Authorization Header
- Authorization header not provided
- Backend rejects request

## 403 Forbidden

### Insufficient Permissions
- User authenticated but lacks required role
- Access denied for protected resource

## Error Response Format

All authentication errors follow a standardized error response:

```json
{
  "timestamp": "2026-01-29T10:15:30Z",
  "status": 401,
  "error": "Unauthorized",
  "message": "Invalid or expired JWT token",
  "path": "/documents/upload"
}

