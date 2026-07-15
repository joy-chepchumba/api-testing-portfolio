# 🔌 API Test Plan – Login API

## Document Information

| Item                 | Details                                                          |
| -------------------- | ---------------------------------------------------------------- |
| **Project**          | ShopEasy (Fictional E-commerce Application)                      |
| **Module**           | User Authentication API                                          |
| **API Name**         | Login API                                                        |
| **Prepared By**      | Joy Chepchumba                                                   |
| **Document Version** | 1.0                                                              |
| **Date**             | 2026-07-16                                                       |
| **Test Type**        | Functional API Testing, Regression Testing & Integration Testing |

---

# 1. Objective

The objective of this API Test Plan is to verify that the Login API functions correctly, securely, and reliably by validating request processing, response accuracy, authentication, error handling, and API behaviour under different input conditions.

The goal is to ensure that valid users are authenticated successfully while invalid requests are handled appropriately according to the API specification.

---

# 2. Scope

The following functionality is included within the scope of testing:

* Successful login using valid credentials
* Login with invalid email address
* Login with invalid password
* Login with missing required fields
* Empty request validation
* Invalid request payload validation
* Response body validation
* HTTP status code validation
* Authentication token validation
* Error message validation
* Response time verification

---

# 3. Out of Scope

The following functionality is excluded from this test plan:

* User Registration API
* Password Reset API
* Multi-Factor Authentication (MFA)
* Social Authentication APIs
* Performance and Load Testing
* Security Penetration Testing

---

# 4. API Information

| Item                        | Details                       |
| --------------------------- | ----------------------------- |
| **Endpoint**                | `/api/v1/login`               |
| **Method**                  | POST                          |
| **Content Type**            | application/json              |
| **Authentication**          | Not Required (Login Endpoint) |
| **Expected Success Status** | HTTP 200 OK                   |

---

# 5. Test Strategy

Testing will include:

* Functional API Testing
* Positive Testing
* Negative Testing
* Boundary Value Testing
* Input Validation Testing
* Response Validation
* HTTP Status Code Validation
* Authentication Validation
* Regression Testing

API requests and responses will be validated using Postman and compared against the API specification.

---

# 6. Test Environment

| Item                 | Details                   |
| -------------------- | ------------------------- |
| **Environment**      | Staging                   |
| **API Client**       | Postman                   |
| **Documentation**    | Swagger / OpenAPI         |
| **Database**         | Test Database             |
| **Operating System** | Windows 11                |
| **Network**          | Internal Test Environment |

---

# 7. Entry Criteria

Testing will commence once:

* API development is complete.
* API has been deployed to the staging environment.
* Swagger documentation is available.
* Test accounts have been created.
* API endpoint is accessible.

---

# 8. Exit Criteria

Testing will be considered complete when:

* All planned API test cases have been executed.
* Critical and High severity defects have been resolved or accepted.
* Regression testing has been completed successfully.
* API Test Summary Report has been prepared.
* Product Owner approves the feature for release.

---

# 9. Test Deliverables

The following deliverables will be produced:

* API Test Plan
* API Test Cases
* API Bug Reports
* Authentication Validation Report
* HTTP Status Code Validation Report
* API Test Summary Report

---

# 10. Risks

Potential risks include:

* API endpoint unavailable
* Authentication service failure
* Invalid or outdated API documentation
* Test environment instability
* Database connectivity issues
* Third-party service outages

---

# 11. Assumptions

This test plan assumes:

* API documentation accurately reflects implementation.
* Test environment mirrors production behaviour.
* Test accounts are available.
* Required backend services are operational.
* Network connectivity is stable throughout testing.

---

# 12. Dependencies

Successful execution of this test plan depends on:

* Availability of the staging environment
* Access to Postman
* Access to Swagger documentation
* Stable backend authentication services
* Availability of valid test accounts

---

# 13. Roles & Responsibilities

| Role                | Responsibility                                                                                                     |
| ------------------- | ------------------------------------------------------------------------------------------------------------------ |
| **QA Analyst**      | Prepare API test cases, execute API tests, validate responses, log defects, verify fixes, and prepare test reports |
| **Developer**       | Resolve reported API defects and support defect verification                                                       |
| **Product Owner**   | Validate business requirements and approve User Acceptance Testing (UAT)                                           |
| **Project Manager** | Coordinate project timelines and release activities                                                                |

---

# 14. Approval

This API Test Plan serves as the testing approach for validating the Login API before deployment to production.

---

# Document History

| Version | Date           | Author             | Description                                  |
| ------- | -------------- | ------------------ | -------------------------------------------- |
| **1.0** | **2026-07-16** | **Joy Chepchumba** | Initial creation of the Login API Test Plan. |
