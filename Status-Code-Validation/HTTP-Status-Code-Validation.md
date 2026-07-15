# 🌐 HTTP Status Code Validation

## Document Information

| Item                 | Details                                     |
| -------------------- | ------------------------------------------- |
| **Project**          | ShopEasy (Fictional E-commerce Application) |
| **Module**           | API Status Code Validation                  |
| **Prepared By**      | Joy Chepchumba                              |
| **Document Version** | 1.0                                         |
| **Date**             | 2026-07-16                                  |

---

# 1. Objective

The purpose of this document is to define the HTTP status codes validated during API testing and ensure that the API returns the correct response code for each request scenario.

Correct status code validation helps verify that the API communicates outcomes consistently and according to REST API standards.

---

# 2. What is an HTTP Status Code?

An HTTP status code is a three-digit response returned by a server indicating the result of an API request.

Status codes are grouped into categories based on their purpose.

---

# 3. Status Code Categories

| Category | Description             |
| -------- | ----------------------- |
| **1xx**  | Informational responses |
| **2xx**  | Successful requests     |
| **3xx**  | Redirection responses   |
| **4xx**  | Client-side errors      |
| **5xx**  | Server-side errors      |

---

# 4. Common Status Codes Used During API Testing

| Status Code                    | Meaning                                    | Typical Validation                     |
| ------------------------------ | ------------------------------------------ | -------------------------------------- |
| **200 OK**                     | Request completed successfully             | Verify response body and returned data |
| **201 Created**                | Resource created successfully              | Verify new resource exists             |
| **204 No Content**             | Request successful with no response body   | Verify empty response                  |
| **400 Bad Request**            | Invalid request or missing required fields | Verify validation message              |
| **401 Unauthorized**           | Authentication failed or token missing     | Verify authentication error            |
| **403 Forbidden**              | User authenticated but lacks permission    | Verify authorization rules             |
| **404 Not Found**              | Requested resource does not exist          | Verify appropriate error message       |
| **405 Method Not Allowed**     | Unsupported HTTP method                    | Verify allowed methods                 |
| **409 Conflict**               | Duplicate or conflicting resource          | Verify conflict handling               |
| **415 Unsupported Media Type** | Invalid Content-Type header                | Verify request rejection               |
| **422 Unprocessable Entity**   | Validation rules failed                    | Verify field-level validation errors   |
| **429 Too Many Requests**      | Rate limit exceeded                        | Verify throttling behaviour            |
| **500 Internal Server Error**  | Unexpected server failure                  | Verify generic error response          |
| **503 Service Unavailable**    | Service temporarily unavailable            | Verify maintenance or outage response  |

---

# 5. Validation Checklist

During API testing, verify that:

* Correct HTTP status code is returned.
* Response body matches the expected status.
* Error messages are meaningful and consistent.
* Sensitive system information is not exposed.
* Invalid requests return appropriate client-side errors.
* Server failures return generic responses without exposing implementation details.

---

# 6. Sample Validation Scenarios

| Scenario                    | Expected Status Code       |
| --------------------------- | -------------------------- |
| Successful Login            | 200 OK                     |
| Invalid Credentials         | 401 Unauthorized           |
| Missing Email               | 400 Bad Request            |
| Missing Password            | 400 Bad Request            |
| Invalid Endpoint            | 404 Not Found              |
| Unsupported HTTP Method     | 405 Method Not Allowed     |
| Invalid Content-Type        | 415 Unsupported Media Type |
| Expired Token               | 401 Unauthorized           |
| Duplicate Resource Creation | 409 Conflict               |
| Unexpected Server Failure   | 500 Internal Server Error  |

---

# 7. Best Practices

* Validate both the status code and the response body.
* Do not rely solely on success messages.
* Ensure error responses are user-friendly and consistent.
* Verify API documentation matches actual behaviour.
* Test both positive and negative scenarios.
* Include edge-case validation where applicable.

---

# 8. Tools Used

* Postman
* Swagger / OpenAPI
* REST APIs
* JSON
* HTTP Protocol

---

# 9. Conclusion

Validating HTTP status codes is a fundamental part of API testing. Ensuring that each request returns the correct response code improves API reliability, simplifies troubleshooting, and confirms compliance with REST API standards.

---

# Document History

| Version | Date           | Author             | Description                                                    |
| ------- | -------------- | ------------------ | -------------------------------------------------------------- |
| **1.0** | **2026-07-16** | **Joy Chepchumba** | Initial creation of HTTP Status Code Validation documentation. |
