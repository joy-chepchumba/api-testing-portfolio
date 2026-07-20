# 🐞 API Bug Report

## Document Information

| Item              | Details                                     |
| ----------------- | ------------------------------------------- |
| **Project**       | ShopEasy (Fictional E-commerce Application) |
| **Module**        | Login API                                   |
| **Reported By**   | Joy Chepchumba                              |
| **Bug ID**        | API-BUG-001                                 |
| **Date Reported** | 2026-07-20                                  |
| **Severity**      | Critical                                    |
| **Priority**      | High                                        |
| **Status**        | Open                                        |

---

# Bug Summary

The Login API returns an **HTTP 500 Internal Server Error** when an expired Bearer Token is used instead of returning the expected **401 Unauthorized** response.

---

# Environment

* Environment: QA
* API Version: v1
* Tool Used: Postman
* Authentication: Bearer Token

---

# Preconditions

* Login API is accessible.
* A previously generated Bearer Token has expired.
* User account exists.

---

# Steps to Reproduce

1. Open Postman.
2. Send a **POST** request to the Login API.
3. Include an expired Bearer Token in the Authorization header.
4. Submit the request.

---

# Actual Result

* API returns:

```http
500 Internal Server Error
```

* Generic server error is displayed.

---

# Expected Result

The API should reject the expired token and return:

```http
401 Unauthorized
```

with a meaningful error message indicating that the authentication token has expired or is invalid.

---

# Impact

* Authentication errors are not handled correctly.
* Client applications receive an incorrect server error.
* Makes troubleshooting difficult.
* Does not comply with expected REST API behaviour.

---

# Suggested Fix

Validate the Bearer Token before processing the request and return the correct authentication response when the token is expired or invalid.

---

# Attachments

* Postman Request
* Postman Response
* API Logs (if available)

---

# Root Cause

Pending Developer Investigation.

---

# Recommendation

Update the authentication middleware to correctly identify expired tokens and return **HTTP 401 Unauthorized** instead of **HTTP 500 Internal Server Error**.

---

# Document History

| Version | Date           | Author             | Description                               |
| ------- | -------------- | ------------------ | ----------------------------------------- |
| **1.0** | **2026-07-20** | **Joy Chepchumba** | Initial creation of Login API Bug Report. |
