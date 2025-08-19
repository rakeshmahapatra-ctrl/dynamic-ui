Got it 👍. I see your sequence diagram from the image. Let’s create a technical design document (TDD) for the CSM Integration with AWS and Pega based on the flow shown.

⸻

Technical Design Document (TDD)

Project: CSM Integration
Component: AWS ↔ Pega ↔ CSM Token Exchange
Version: 1.0
Date: 19-Aug-2025
Prepared By: [Your Name]

⸻

1. Introduction

This document outlines the technical design for integrating Pega with CSM using AWS STS (Security Token Service). The purpose is to enable secure communication and token exchange between AWS, Pega, and CSM systems.

⸻

2. Architecture Overview

The integration involves three main systems:
	1.	AWS – Provides temporary session tokens using IAM and AWS STS.
	2.	Pega – Acts as the client application requesting tokens from CSM using AWS-signed requests.
	3.	CSM – Issues client and TIAA tokens based on authenticated requests from Pega.

⸻

3. Sequence Flow

Step 1: AWS Session Token Request
	•	Action:
Pega sends an AWS Signer Request to the AWS STS service.
	•	Response:
AWS STS returns a session token (IAM request body and headers).

⸻

Step 2: Request Client Token from CSM
	•	Action:
Pega makes a POST request to CSM with IAM details obtained from AWS STS.
	•	Response:
CSM returns a client token to Pega.

⸻

Step 3: Retrieve TIAA Token from CSM
	•	Action:
Pega makes a GET request to CSM, passing the client token in the request header as X-Vault-Token.
	•	Response:
CSM returns the TIAA token to Pega.

⸻

4. Sequence Diagram

AWS                  Pega                    CSM
 |                    |                      |
 |-- POST STS Req --> |                      |
 |<- Session Token ---|                      |
 |                    |-- POST client token ->|
 |                    |<- Client token -------|
 |                    |-- GET (X-Vault-Token)→|
 |                    |<- TIAA token ---------|


⸻

5. API Specifications

5.1 AWS STS Request
	•	Method: POST
	•	Endpoint: https://sts.amazonaws.com/
	•	Headers: AWS Signature V4 signed headers
	•	Response: Temporary session token (AccessKeyId, SecretAccessKey, SessionToken)

5.2 CSM Client Token Request
	•	Method: POST
	•	Endpoint: https://<csm-domain>/v1/auth/iam/login
	•	Headers:
	•	Content-Type: application/json
	•	Body: IAM credentials from AWS STS response
	•	Response: Client token

5.3 CSM TIAA Token Request
	•	Method: GET
	•	Endpoint: https://<csm-domain>/v1/tiaa/token
	•	Headers:
	•	X-Vault-Token: <client-token>
	•	Response: TIAA token

⸻

6. Security Considerations
	•	All communication is over HTTPS (TLS 1.2/1.3).
	•	IAM credentials from AWS STS have a short TTL for security.
	•	Tokens are stored in Pega secure storage (Vault / DSS) with expiration handling.

⸻

7. Error Handling
	•	401 Unauthorized – Invalid or expired token, retry with fresh AWS STS request.
	•	403 Forbidden – IAM role not authorized for the operation.
	•	500 Internal Server Error – Escalate to CSM team.
	•	Retries with exponential backoff for transient errors.

⸻

8. Assumptions
	•	AWS IAM role for Pega has correct trust policies.
	•	CSM Vault integration is enabled and accessible from Pega runtime environment.
	•	Token expiration and refresh mechanisms are implemented in Pega.

⸻

9. Open Items / Dependencies
	•	Confirmation of CSM API endpoints.
	•	IAM role ARN details from AWS security team.
	•	Deployment strategy for Pega environment (Dev, QA, Prod).

⸻

👉 Do you want me to also prepare this in a Word/Docx format with the sequence diagram embedded, so you can directly use it for documentation/sharing?
