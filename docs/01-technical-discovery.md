# Technical Discovery Questionnaire

This document defines the questions I would answer before building or connecting an enterprise integration.

## 1. Business Workflow

- What customer outcome are we trying to automate?
- What triggers the workflow today?
- Which teams own the current process?
- What does the current human workflow look like?
- Where are the biggest delays or manual steps?
- What does successful resolution mean?
- Which part of the workflow is highest value for the initial POC?

## 2. Systems of Record

- Which system owns customer identity?
- Which system owns customer profile data?
- Which system owns movie and showtime inventory?
- Which system owns seat inventory?
- Which system processes ticket purchases?
- Which system owns loyalty and membership?
- Which system owns payment tokens or references?
- Which system is authoritative if two systems disagree?

## 3. API Availability

- Is a REST API available?
- Is there API documentation?
- Is sandbox access available?
- Which endpoints are required?
- Are both read and write operations supported?
- Are webhooks available?
- What request and response formats are supported?
- Are there pagination requirements?
- Are there documented rate limits?

## 4. Authentication

- API key?
- Basic authentication?
- OAuth 2.0?
- Client credentials?
- Authorization code flow?
- Bearer token?
- User-delegated OAuth?
- mTLS?
- How long do tokens live?
- Are refresh tokens supported?
- What scopes are required?

## 5. Data

- What customer identifier should Maven use?
- What fields are required for the use case?
- Which fields contain PII?
- What data should be retrieved at runtime?
- What data can safely be stored in Maven?
- What values need transformation or normalization?
- Are there required custom fields?
- Are there schema constraints?

## 6. Security

- What permissions does the integration account require?
- Can access be limited using least privilege?
- How are credentials stored?
- How are credentials rotated?
- What audit logging is required?
- What are the customer's data retention requirements?
- Are there data residency requirements?
- Are there compliance requirements that affect the workflow?

## 7. Reliability

- What is the upstream API SLA?
- What latency is expected?
- What timeout should the integration use?
- Which errors should be retried?
- What retry guidance does the API provide?
- Is idempotency supported for write operations?
- What happens if an upstream system is unavailable?

## 8. POC Requirements

- Which 1–2 workflows should be validated first?
- What must be live in the initial POC?
- What can be mocked?
- Are sandbox credentials available?
- What test users and test data exist?
- What are the agreed success criteria?
- Who validates the results?
- What must be proven before production integration begins?
