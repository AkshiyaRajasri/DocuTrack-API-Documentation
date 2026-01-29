# Backend Request Lifecycle

This document describes how a typical backend request is processed in DocuTrack.

## High-Level Flow

Client Request  
→ Controller  
→ Service Layer  
→ Validation  
→ Business Logic  
→ Repository/Data Access  
→ Response Mapping  
→ Client Response  

## Controller Layer

Responsibilities:

- Map HTTP requests to controller methods
- Parse request body and parameters
- Perform basic request validation
- Forward request to service layer

## Service Layer

Responsibilities:

- Execute business logic
- Coordinate multiple operations
- Enforce workflow rules
- Call repository/data access layer

## Validation Layer

Validation occurs at multiple stages:

- Request body validation
- Field-level validation
- Business rule validation

Invalid data results in standardized validation errors.

## Exception Handling

All exceptions are handled by a global exception handler:

- ValidationException → 400 Bad Request
- AuthenticationException → 401 Unauthorized
- AuthorizationException → 403 Forbidden
- ResourceNotFoundException → 404 Not Found
- InternalServerError → 500 Internal Server Error

## Response Standardization

Responses are mapped to consistent response formats before returning to client.
