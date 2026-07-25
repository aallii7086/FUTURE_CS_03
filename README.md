# API Security Risk Analysis (Modern SaaS Skill)

## Overview

This project was completed as part of the **Future Interns Cyber Security Internship (FUTURE_CS_03)**.

The objective of this assessment was to perform a read-only API Security Risk Analysis on a public REST API using ethical security testing practices. The assessment focused on identifying potential security observations, evaluating authentication mechanisms, inspecting response headers, and documenting findings from a security consultant's perspective.

---

## Objectives

- Perform ethical API security assessment
- Analyze public REST API endpoints
- Review authentication requirements
- Inspect HTTP response headers
- Identify potential security observations
- Recommend security best practices

---

## API Tested

**JSONPlaceholder Public REST API**

Base URL:

```text
https://jsonplaceholder.typicode.com
```

---

## Tools Used

- Kali Linux
- Postman (Lightweight API Client)
- Visual Studio Code
- Git
- GitHub

---

## Methodology

The assessment followed a structured read-only methodology:

1. Selected a public demonstration API.
2. Sent HTTP GET requests using Postman.
3. Reviewed response bodies.
4. Inspected response headers.
5. Evaluated authentication requirements.
6. Identified security observations.
7. Documented findings and recommendations.

No exploitation or unauthorized testing was performed.

---

## Endpoints Tested

| Endpoint | Method | Status |
|----------|--------|--------|
| /posts | GET | ✅ |
| /users | GET | ✅ |
| /comments | GET | ✅ |

---

## Security Findings

- Public endpoint accessibility (Expected for demo API)
- Technology information disclosure (`X-Powered-By`)
- User information exposure assessment
- Rate limiting observed
- Secure response headers present

---

## Repository Structure

```text
FUTURE_CS_03
│
├── evidence
│   ├── requests
│   └── screenshots
│
├── report
│   ├── FUTURE_CS_03_Report.md
│   └── FUTURE_CS_03_Report.pdf
│
└── README.md
```

---

## Disclaimer

This assessment was performed only against a public demonstration API using ethical, read-only testing techniques. No exploitation, unauthorized access, or modification of data was attempted.

---

## Author

**<YOUR NAME>**

Future Interns – Cyber Security Internship