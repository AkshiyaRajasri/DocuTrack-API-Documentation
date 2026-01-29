# Approval Workflow

This document describes the approval process for documents in DocuTrack.

## Overview

Documents must go through an approval workflow before they are finalized and published.

## Roles Involved

- Document Owner
- Reviewer
- Approver
- Administrator (optional override)

## High-Level Flow

UPLOADED  
→ IN_REVIEW  
→ APPROVED or REJECTED  
→ (If rejected) RETURNED_FOR_CHANGES  
→ Resubmission  
→ Final Approval  

## Workflow Steps

### 1. Submit for Review

- Document owner submits uploaded document for review
- Document status changes to `IN_REVIEW`
- Reviewer is notified

### 2. Review Phase

Reviewer can:

- Approve document
- Reject document with comments

### 3. Approval

If approved:

- Document status changes to `APPROVED`
- Document becomes finalized
- Audit trail is updated

### 4. Rejection

If rejected:

- Document status changes to `REJECTED`
- Rejection reason is stored
- Document is returned to owner

### 5. Resubmission

- Document owner updates document
- Resubmits for review
- Workflow restarts from review stage

## Audit Trail

All workflow actions are logged:

- Who performed the action
- Timestamp
- Action taken
- Comments or reasons

