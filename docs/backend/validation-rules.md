# Validation Rules

This document defines common validation rules enforced by the backend.

## User Input Validation

- Required fields must be present
- String length limits enforced
- Email format validation
- Password complexity rules

## Document Validation

- Document name required
- Supported file types only (PDF, DOCX)
- Maximum file size enforced
- Metadata fields validated

## Workflow Validation

- Status transitions validated
- Invalid state changes rejected
- Required approvals enforced

## Validation Error Handling

Validation failures return structured error responses:

```json
{
  "status": 400,
  "error": "Bad Request",
  "message": "Validation failed for one or more fields",
  "details": [
    {
      "field": "documentName",
      "message": "Document name is required"
    }
  ]
}

