# Document Status Transitions

This document defines allowed status transitions for documents.

## Supported Statuses

- DRAFT
- UPLOADED
- IN_REVIEW
- APPROVED
- REJECTED
- ARCHIVED

## Allowed Transitions

| Current Status | Allowed Next Status |
|----------------|---------------------|
| DRAFT          | UPLOADED            |
| UPLOADED       | IN_REVIEW           |
| IN_REVIEW      | APPROVED            |
| IN_REVIEW      | REJECTED            |
| REJECTED       | DRAFT               |
| APPROVED       | ARCHIVED            |

## Invalid Transitions

The following transitions are not allowed:

- DRAFT → APPROVED
- UPLOADED → APPROVED
- ARCHIVED → IN_REVIEW

Invalid transitions return a validation error.

## Business Rules

- Only reviewers can move document to APPROVED
- Only document owner can resubmit after rejection
- Archived documents cannot be modified

## Error Handling

Invalid transitions return:

```json
{
  "status": 400,
  "error": "Invalid Status Transition",
  "message": "Document cannot be moved from DRAFT to APPROVED"
}

