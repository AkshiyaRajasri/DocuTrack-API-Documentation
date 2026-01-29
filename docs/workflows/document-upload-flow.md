# Document Upload Workflow

This document describes the end-to-end workflow for uploading documents into DocuTrack.

## Overview

The document upload workflow allows users to upload documents, attach metadata, and initiate processing for approval workflows.

## High-Level Flow

Client  
→ Upload Document Request  
→ Backend Validation  
→ File Storage  
→ Metadata Persistence  
→ Workflow Initialization  
→ Upload Response  

## Detailed Steps

### 1. Upload Request

Client sends a multipart/form-data request containing:

- Document file
- Document name
- Document type
- Optional metadata

### 2. Validation

Backend validates:

- File type (PDF, DOCX only)
- File size limits
- Required metadata fields
- User permissions to upload documents

### 3. File Storage

- File is stored in document storage system
- Storage reference ID is generated
- File checksum may be calculated

### 4. Metadata Persistence

Backend stores:

- Document name
- Storage reference ID
- Uploaded by user
- Upload timestamp
- Initial document status

### 5. Workflow Initialization

- Document status is set to `UPLOADED`
- Approval workflow is initialized
- Document is marked ready for review

## Failure Scenarios

- Unsupported file type
- File size exceeded
- Missing required metadata
- Storage service failure

Each failure returns a standardized error response.

