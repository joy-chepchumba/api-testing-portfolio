# Read (GET) Requests Testing

## Overview

The **GET** HTTP method is used to retrieve data from a server without modifying existing resources.

GET requests should be **safe** (they do not change data) and **idempotent** (making the same request multiple times should return the same result if the data has not changed).

---

# Common GET Request Flow

```
Client
   │
   │ GET /users/101
   ▼
API Server
   │
Authenticate Request
   │
Validate Parameters
   │
Retrieve Resource
   │
Return Response
   ▼
Client
```

---

# Expected Success Response

| Status Code | Meaning |
|-------------|---------|
| 200 OK | Resource retrieved successfully |
| 204 No Content | Request successful but no data returned |

---

# Types of GET Requests

### Retrieve a Single Resource

```http
GET /api/users/101
```

### Retrieve Multiple Resources

```http
GET /api/users
```

### Retrieve Using Query Parameters

```http
GET /api/users?country=KE
```

### Pagination

```http
GET /api/users?page=1&limit=20
```

---

# Positive Test Scenarios

- Retrieve an existing resource.
- Retrieve a list of resources.
- Retrieve resources using valid query parameters.
- Retrieve paginated results.
- Verify response structure.
- Verify returned data matches stored data.
- Verify response time is acceptable.

---

# Negative Test Scenarios

- Request a non-existent resource.
- Invalid resource ID.
- Invalid query parameters.
- Missing authentication token.
- Invalid authentication token.
- Unauthorized user access.
- Unsupported request parameters.

---

# Edge Case Scenarios

- Empty dataset.
- Extremely large datasets.
- Maximum page number.
- Zero results returned.
- Special characters in query parameters.
- Invalid pagination values.
- Simultaneous GET requests.
- Cached versus non-cached responses.

---

# Validation Checklist

Verify that:

- Correct HTTP status code is returned.
- Response body is valid JSON.
- Returned fields are correct.
- Sensitive information is not exposed.
- Pagination metadata is correct.
- Filtering returns expected records.
- Sorting works correctly.
- Authentication is enforced.
- Authorization is enforced.

---

# Example Request

```http
GET /api/users/101
Authorization: Bearer <token>
```

---

# Example Success Response

```http
HTTP/1.1 200 OK
```

```json
{
    "id": 101,
    "firstName": "Joy",
    "lastName": "Chepchumba",
    "email": "joy@example.com"
}
```

---

# Example Not Found Response

```http
HTTP/1.1 404 Not Found
```

```json
{
    "message": "User not found"
}
```

---

# Common Defects

Examples of issues commonly found while testing GET APIs:

- Incorrect HTTP status code.
- Missing response fields.
- Incorrect data returned.
- Sensitive information exposed.
- Pagination not working correctly.
- Sorting or filtering issues.
- Slow response times.
- Unauthorized data exposure.
- Incorrect error messages.

---

# Best Practices

- Validate response status codes.
- Verify response schema.
- Test filtering and sorting.
- Test pagination thoroughly.
- Verify response time.
- Validate authentication and authorization.
- Confirm only expected data is returned.
- Repeat requests to verify idempotency.
