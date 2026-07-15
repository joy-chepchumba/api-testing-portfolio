# ✅ Login API Test Cases

## Document Information

| Item                 | Details                                     |
| -------------------- | ------------------------------------------- |
| **Project**          | ShopEasy (Fictional E-commerce Application) |
| **Module**           | User Authentication API                     |
| **API Name**         | Login API                                   |
| **Prepared By**      | Joy Chepchumba                              |
| **Document Version** | 1.0                                         |
| **Date**             | 2026-07-16                                  |

---

# API Information

| Item                        | Value              |
| --------------------------- | ------------------ |
| **Endpoint**                | `/api/v1/login`    |
| **Method**                  | POST               |
| **Content-Type**            | `application/json` |
| **Authentication**          | Not Required       |
| **Expected Success Status** | HTTP 200 OK        |

---

# Test Cases

| TC ID      | Test Scenario                                         | Request                        | Expected Result                                                | Priority | Status |
| ---------- | ----------------------------------------------------- | ------------------------------ | -------------------------------------------------------------- | -------- | ------ |
| API-TC-001 | Login with valid email and password                   | Valid email & valid password   | HTTP 200 returned with authentication token and user details   | High     | Pass   |
| API-TC-002 | Login with invalid email                              | Invalid email & valid password | HTTP 401 Unauthorized with appropriate error message           | High     | Pass   |
| API-TC-003 | Login with invalid password                           | Valid email & invalid password | HTTP 401 Unauthorized with appropriate error message           | High     | Pass   |
| API-TC-004 | Login with both email and password invalid            | Invalid credentials            | HTTP 401 Unauthorized                                          | High     | Pass   |
| API-TC-005 | Login with empty email                                | Password only                  | HTTP 400 Bad Request with validation message                   | High     | Pass   |
| API-TC-006 | Login with empty password                             | Email only                     | HTTP 400 Bad Request with validation message                   | High     | Pass   |
| API-TC-007 | Login with empty request body                         | `{}`                           | HTTP 400 Bad Request                                           | High     | Pass   |
| API-TC-008 | Login with missing required fields                    | Partial request payload        | HTTP 400 Bad Request                                           | High     | Pass   |
| API-TC-009 | Login using malformed JSON payload                    | Invalid JSON syntax            | HTTP 400 Bad Request                                           | Medium   | Pass   |
| API-TC-010 | Verify response body structure after successful login | Valid credentials              | Response contains token, user ID, email and success message    | High     | Pass   |
| API-TC-011 | Verify authentication token is generated              | Valid credentials              | Bearer token returned in response                              | High     | Pass   |
| API-TC-012 | Verify response time                                  | Valid credentials              | API responds within acceptable response time (e.g. <2 seconds) | Medium   | Pass   |

---

# Negative Test Scenarios

| TC ID       | Scenario                                     | Expected Result                                        |
| ----------- | -------------------------------------------- | ------------------------------------------------------ |
| API-NEG-001 | SQL Injection attempt in email field         | Request rejected without exposing database information |
| API-NEG-002 | SQL Injection attempt in password field      | Request rejected securely                              |
| API-NEG-003 | Cross-Site Scripting (XSS) payload submitted | Request rejected or sanitized appropriately            |
| API-NEG-004 | Unsupported HTTP Method (GET)                | HTTP 405 Method Not Allowed                            |
| API-NEG-005 | Unsupported Media Type                       | HTTP 415 Unsupported Media Type                        |
| API-NEG-006 | Invalid Content-Type header                  | HTTP 415 Unsupported Media Type                        |

---

# Edge Test Scenarios

| TC ID        | Scenario                               | Expected Result                                                                                       |
| ------------ | -------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| API-EDGE-001 | Extremely long email address           | Appropriate validation message returned                                                               |
| API-EDGE-002 | Extremely long password                | Request processed according to validation rules                                                       |
| API-EDGE-003 | Email with leading/trailing spaces     | Spaces trimmed or validation applied                                                                  |
| API-EDGE-004 | Password containing special characters | Request processed successfully if supported                                                           |
| API-EDGE-005 | Multiple consecutive login attempts    | API behaves according to security requirements (rate limiting or account protection where applicable) |

---

# Test Data

| Field            | Sample Value               |
| ---------------- | -------------------------- |
| Valid Email      | `joy@example.com`          |
| Valid Password   | `Password@123`             |
| Invalid Email    | `invalid@example.com`      |
| Invalid Password | `WrongPassword123`         |
| Empty Payload    | `{}`                       |
| Malformed JSON   | `{email:"joy@example.com"` |

---

# Execution Summary

| Metric           | Result |
| ---------------- | ------ |
| Total Test Cases | 12     |
| Passed           | 12     |
| Failed           | 0      |
| Blocked          | 0      |
| Overall Status   | ✅ Pass |

---

# Remarks

* All functional API scenarios executed successfully.
* Authentication token generation was validated.
* Request and response payloads matched the API specification.
* HTTP status codes were verified against expected outcomes.
* Additional security and performance testing should be conducted separately.

---

# Document History

| Version | Date           | Author             | Description                               |
| ------- | -------------- | ------------------ | ----------------------------------------- |
| **1.0** | **2026-07-16** | **Joy Chepchumba** | Initial creation of Login API Test Cases. |
