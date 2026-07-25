# API Security Risk Analysis Report

**Internship:** Future Interns – Cyber Security Internship

**Task ID:** FUTURE_CS_03

**Project Title:** API Security Risk Analysis (Modern SaaS Skill)

**API Assessed:** JSONPlaceholder Public REST API

**Assessment Type:** Read-Only API Security Assessment

**Assessment Date:** July 2026

**Prepared By:** <YOUR NAME>

# Executive Summary

This report presents a read-only API Security Risk Analysis conducted on the JSONPlaceholder Public REST API. The assessment was performed using safe and ethical testing techniques without attempting to exploit, modify, or disrupt the service.

The objective of this assessment was to evaluate publicly accessible API endpoints, inspect HTTP requests and responses, review response headers, analyze authentication mechanisms, and identify potential security observations based on industry best practices.

Three public endpoints (`/posts`, `/users`, and `/comments`) were examined using Postman. The assessment identified information useful for understanding API security, including authentication behavior, response headers, technology disclosure, rate limiting, and data exposure. Recommendations are provided to improve API security in production environments while recognizing that the tested API is intentionally designed for learning and testing purposes.

# Objective

The objective of this project is to perform an ethical API Security Risk Analysis on a public demonstration API and document the findings from a security consultant's perspective.

The assessment focuses on:

- Inspecting publicly available API endpoints
- Reviewing HTTP requests and responses
- Evaluating authentication requirements
- Inspecting response headers
- Identifying potential security observations
- Assessing possible business impact
- Recommending security best practices

# Scope

## In Scope

- Read-only API testing
- HTTP GET requests
- Response body inspection
- Response header analysis
- Authentication review
- Security observation and documentation

## Out of Scope

- Exploitation attempts
- Authentication bypass
- Denial-of-Service testing
- Unauthorized access attempts
- Data modification
- Vulnerability exploitation

# Tools Used

| Tool | Purpose |
|------|---------|
| Postman (Lightweight API Client) | API Testing |
| JSONPlaceholder API | Target API |
| Kali Linux | Testing Environment |
| Visual Studio Code | Report Writing |
| Git | Version Control |
| GitHub | Repository Hosting |
# API Overview

**API Name:** JSONPlaceholder


**Base URL:**

```text
https://jsonplaceholder.typicode.com
```


**Purpose:**

JSONPlaceholder is a free online REST API developed for learning, testing, and prototyping applications. It provides sample resources such as posts, users, comments, albums, photos, and todos without exposing real user information.

During this assessment, only publicly documented endpoints were tested using read-only HTTP requests in accordance with ethical security testing practices.

# Testing Methodology

The API Security Risk Analysis was conducted using a structured, read-only assessment methodology. The objective was to inspect publicly accessible API endpoints without modifying data or attempting any unauthorized activity.

The following methodology was followed:

1. Selected the JSONPlaceholder Public REST API as the assessment target.
2. Configured and tested API requests using the Postman Lightweight API Client.
3. Sent HTTP GET requests to publicly documented endpoints.
4. Reviewed HTTP response status codes and response bodies.
5. Inspected response headers for security-related information.
6. Evaluated authentication and authorization requirements.
7. Identified potential security observations based on API security best practices.
8. Documented findings, business impact, and remediation recommendations.

No exploitation, brute-force attempts, authentication bypass, or denial-of-service testing was performed during this assessment.

# API Endpoints Tested

| Endpoint | Method | Purpose | Result |
|----------|--------|---------|--------|
| `/posts` | GET | Retrieve sample posts | Successful (200 OK) |
| `/users` | GET | Retrieve sample user information | Successful (200 OK) |
| `/comments` | GET | Retrieve sample comments | Successful (200 OK) |

# Endpoint Analysis

## Endpoint 1 – GET /posts

**URL**

```text
https://jsonplaceholder.typicode.com/posts
```

### Observations

- Request completed successfully with HTTP Status Code **200 OK**.
- Authentication was **not required** to access the endpoint.
- The response returned sample post data in JSON format.
- No sensitive information, credentials, API keys, or authentication tokens were observed.

### Security Assessment

The endpoint behaves as expected for a public demonstration API. In a production environment, access to sensitive resources should be protected through appropriate authentication mechanisms.

---

## Endpoint 2 – GET /users

**URL**

```text
https://jsonplaceholder.typicode.com/users
```

### Observations

- The endpoint returned user profile information.
- Data included names, usernames, email addresses, phone numbers, addresses, websites, and company information.
- No authentication was required.
- No passwords, tokens, or confidential credentials were exposed.

### Security Assessment

The returned information is intentionally provided for learning purposes. In production environments, user-related information should be protected through authentication, authorization, and the principle of least privilege.

---

## Endpoint 3 – GET /comments

**URL**

```text
https://jsonplaceholder.typicode.com/comments
```

### Observations

- The endpoint returned comment information successfully.
- Data included comment IDs, names, email addresses, and comment content.
- No authentication was required.
- No sensitive credentials or authentication tokens were exposed.

### Security Assessment

The endpoint exposes only demonstration data. For production APIs, publicly exposing user-related information should be carefully evaluated to reduce privacy risks.

# Security Findings

## Finding 1 – Public Endpoint Accessibility

**Severity:** Informational (Expected for Demo API)

**Observation**

The tested API endpoints (`/posts`, `/users`, and `/comments`) were publicly accessible without requiring authentication.

**Business Impact**

Public APIs are expected to provide open access to demonstration data. However, production APIs containing sensitive information should require authentication and authorization before allowing access.

**Recommendation**

Implement authentication mechanisms such as API Keys, OAuth 2.0, or JSON Web Tokens (JWT) to protect sensitive production endpoints.

---

## Finding 2 – Technology Information Disclosure

**Severity:** Low

**Observation**

The response headers exposed the following technology information:

- X-Powered-By: Express
- Server: Cloudflare

**Business Impact**

Technology disclosure may help attackers identify the application's technology stack and perform targeted reconnaissance.

**Recommendation**

Remove or minimize unnecessary response headers that reveal backend technologies in production environments.

---

## Finding 3 – User Information Exposure Assessment

**Severity:** Informational

**Observation**

The `/users` endpoint returned user profile information including names, email addresses, phone numbers, addresses, websites, and company information.

The assessment confirmed that the data belongs to a public demonstration API and does not represent real user information.

**Business Impact**

In production environments, unnecessary exposure of user information could increase privacy risks and support phishing or social engineering attacks.

**Recommendation**

Return only the minimum information required by the client application and protect sensitive user information using proper authentication and authorization controls.

---

## Finding 4 – Rate Limiting Observation

**Severity:** Positive Security Control

**Observation**

The response headers included rate-limiting information, indicating that request limits are configured.

**Business Impact**

Rate limiting helps reduce abuse, automated attacks, and excessive API usage.

**Recommendation**

Continue implementing rate limiting for all production API endpoints and monitor unusual traffic patterns.

# Risk Matrix

| Finding | Severity |
|----------|----------|
| Public Endpoint Accessibility | Informational |
| Technology Information Disclosure | Low |
| User Information Exposure Assessment | Informational |
| Rate Limiting Implemented | Positive Security Control |

# Business Impact

Although the assessed API is intentionally designed for learning and testing, the observations demonstrate how similar implementations in production environments could introduce security risks if not properly secured.

Potential business impacts include:

- Information disclosure
- Increased phishing and social engineering risks
- Technology fingerprinting by attackers
- Privacy concerns
- Increased attack surface due to unnecessary data exposure

Implementing strong authentication, authorization, secure response headers, and least-privilege access controls significantly reduces these risks.

# Recommendations

The following security best practices are recommended for production APIs:

- Implement strong authentication (OAuth 2.0, JWT, or API Keys).
- Enforce proper authorization for protected resources.
- Minimize unnecessary information returned in API responses.
- Remove technology disclosure headers where possible.
- Apply secure HTTP response headers.
- Implement request rate limiting.
- Validate all user inputs.
- Perform regular API security assessments.
- Follow the OWASP API Security Top 10 recommendations.

# Key Learnings

This project provided practical experience in performing an API Security Risk Analysis using a public REST API.

During the assessment, the following concepts were reinforced:

- Understanding REST API architecture and HTTP methods.
- Using Postman to inspect API requests and responses.
- Analyzing HTTP response headers for security-related information.
- Evaluating authentication and authorization requirements.
- Identifying technology disclosure through response headers.
- Assessing information exposure from API responses.
- Understanding the importance of rate limiting.
- Applying API security best practices based on real observations.
- Writing a professional security assessment report.

This assessment also strengthened documentation and reporting skills by presenting technical findings in business-friendly language.

# Conclusion

The API Security Risk Analysis successfully evaluated the JSONPlaceholder Public REST API using safe and ethical testing practices.

Three API endpoints were analyzed to assess authentication behavior, response headers, information exposure, and general API security posture. The assessment confirmed that the API is intentionally designed as a public demonstration platform for learning and testing.

No critical security vulnerabilities were identified during the assessment. However, observations such as technology disclosure and public accessibility were documented to demonstrate how similar implementations should be secured in production environments.

Overall, this project provided valuable hands-on experience in API security assessment, security documentation, and risk analysis while reinforcing industry best practices for protecting modern REST APIs.

# Evidence Collected

The following evidence was collected during the assessment:

| Screenshot | Description |
|------------|-------------|
| 01_project_structure.png | Project folder structure |
| 02_postman_home.png | Postman Lightweight API Client |
| 03_get_posts_response.png | GET /posts response (200 OK) |
| 04_posts_response_headers.png | Response header analysis |
| 05_users_response_body.png | GET /users response body |
| 06_users_response_headers.png | Response headers for /users |
| 07_comments_response.png | GET /comments response |

# References

- JSONPlaceholder Public API
  https://jsonplaceholder.typicode.com

- OWASP API Security Top 10
  https://owasp.org/API-Security/

- Postman API Platform
  https://www.postman.com/