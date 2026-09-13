# Consent API – Consent Management REST API

A hosted **Consent Management REST API** for developers to add consent lifecycle management to applications and automated workflows.

Consent API lets applications **create, retrieve, check, and revoke consent** without building the complete consent lifecycle themselves.

## What the API does

The API provides endpoints to:

- Create a consent record
- Retrieve an existing consent
- Check whether consent is ACTIVE, EXPIRED, or REVOKED
- Revoke consent
- Verify the updated consent status

This makes it possible for an application or automated workflow to check consent before performing an action or sharing data.

## Example use cases

Consent API can be integrated into workflows involving:

- Healthcare consent and health-record sharing
- Customer data-sharing consent
- Privacy and data-access workflows
- Third-party data access
- Marketing and communication consent
- Automated workflows and API integrations

## Quickstart

Create a consent:

```http
POST https://consent-api-stage1.onrender.com/consents
X-API-Key: YOUR_API_KEY
Content-Type: application/json

Example request:
{
  "customer_id": "PATIENT-001",
  "application_number": "HOSPITAL-001",
  "scenario_id": "HEALTH-RECORD-ACCESS-001",
  "purpose": "Access patient health records for treatment",
  "expires_at": null,
  "metadata": null
}

A newly created consent starts in the ACTIVE state.
Applications can subsequently retrieve the consent, check its current status, or revoke it.

**Developer resources**
**Consent API Website**
https://consent-api-website.onrender.com

**Developer Documentation**
https://documenter.getpostman.com/view/50524135/2sBYAysovB
The Postman documentation includes a complete consent lifecycle Quickstart and a Run in Postman option.

**Authentication**
Authenticated endpoints use an API key supplied through:
X-API-Key: YOUR_API_KEY

The health-check endpoint does not require authentication.

**Consent lifecycle**
A consent instance can have one of three states:
ACTIVE → EXPIRED
or
ACTIVE → REVOKED
Only one ACTIVE consent can exist for the same customer, application, and scenario.
After a consent becomes REVOKED or EXPIRED, a new consent instance can be created for the same scenario.

**Current stage**
This is an early developer release intended for API integration testing, workflow experimentation, and developer feedback.

