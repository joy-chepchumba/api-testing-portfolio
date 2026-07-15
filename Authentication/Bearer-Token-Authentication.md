# 🔐 Bearer Token Authentication

## Document Information

| Item                 | Details                                     |
| -------------------- | ------------------------------------------- |
| **Project**          | ShopEasy (Fictional E-commerce Application) |
| **Module**           | API Authentication                          |
| **Prepared By**      | Joy Chepchumba                              |
| **Document Version** | 1.0                                         |
| **Date**             | 2026-07-16                                  |

---

# 1. Overview

Bearer Token Authentication is a commonly used authentication mechanism for securing REST APIs.

Once a user successfully authenticates, the API generates an access token that must be included in subsequent requests to access protected resources.

---

# 2. Authentication Flow

The typical authentication process follows these steps:

1. User submits valid login credentials.
2. API validates the credentials.
3. API generates an access token.
4. Client stores the token securely.
5. Client includes the token in every protected API request.
6. Server validates the token before processing the request.

---

# 3. Authorization Header

The access token is sent using the HTTP **Authorization** header.

### Example

```http
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```

---

# 4. Sample Login Request

```http
POST /api/v1/login
Content-Type: application/json

{
  "email": "joy@example.com",
  "password": "Password@123"
}
```

---

# 5. Sample Login Response

```json
{
  "status": "success",
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "user": {
    "id": 101,
    "email": "joy@example.com"
  }
}
```

---

# 6. Using the Token

After authentication, the token should be included in every request to protected endpoints.

### Example Request

```http
GET /api/v1/profile

Authorization: Bearer <access_token>
```

---

# 7. Authentication Test Scenarios

| Scenario               | Expected Result                                    |
| ---------------------- | -------------------------------------------------- |
| Valid Bearer Token     | HTTP 200 OK                                        |
| Missing Token          | HTTP 401 Unauthorized                              |
| Invalid Token          | HTTP 401 Unauthorized                              |
| Expired Token          | HTTP 401 Unauthorized                              |
| Malformed Token        | HTTP 401 Unauthorized                              |
| Token for another user | Access denied according to API authorization rules |

---

# 8. Validation Checklist

During authentication testing, verify:

* Token is generated after successful login.
* Token is returned in the response body or header as specified.
* Protected endpoints reject requests without a token.
* Expired tokens are rejected.
* Invalid tokens are rejected.
* Token format follows the API specification.
* Sensitive information is never exposed in the token or response.

---

# 9. Common HTTP Status Codes

| Status Code                   | Meaning                                 |
| ----------------------------- | --------------------------------------- |
| **200 OK**                    | Authentication successful               |
| **400 Bad Request**           | Invalid request payload                 |
| **401 Unauthorized**          | Authentication failed or token missing  |
| **403 Forbidden**             | User authenticated but lacks permission |
| **500 Internal Server Error** | Unexpected server error                 |

---

# 10. Best Practices

* Always use HTTPS when transmitting tokens.
* Never expose tokens in URLs.
* Store tokens securely.
* Avoid logging authentication tokens.
* Validate token expiration.
* Re-authenticate users when tokens expire.

---

# 11. Tools Used

* Postman
* Swagger / OpenAPI
* REST APIs
* JSON
* HTTP Headers

---

# 12. Conclusion

Bearer Token Authentication is a standard mechanism for securing REST APIs. Proper validation of authentication flows, token handling, and authorization behaviour helps ensure that only authenticated users can access protected resources while maintaining API security.

---

# Document History

| Version | Date           | Author             | Description                                                    |
| ------- | -------------- | ------------------ | -------------------------------------------------------------- |
| **1.0** | **2026-07-16** | **Joy Chepchumba** | Initial creation of Bearer Token Authentication documentation. |
