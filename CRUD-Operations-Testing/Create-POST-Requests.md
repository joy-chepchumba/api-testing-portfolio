# Create (POST) Requests Testing

## Overview

The **POST** HTTP method is used to create new resources in a REST API.

POST requests send data to the server, which processes the request and creates a new resource. Unlike PUT, POST is generally **not idempotent**, meaning sending the same request multiple times may create multiple resources.

---

# POST Request Flow

```
Client
   │
POST /api/users
   │
Validate Request
   │
Validate Business Rules
   │
Create Resource
   │
Persist Data
   ▼
Return Created Resource
```

---

# Example POST Request

```http
POST /api/users
Authorization: Bearer <token>
Content-Type: application/json
```

```json
{
    "firstName": "Joy",
    "lastName": "Chepchumba",
    "email": "joy@example.com",
    "phone": "0712345678"
}
```

---

# Expected Success Responses

| Status Code | Meaning |
|-------------|---------|
| 201 Created | Resource created successfully |
| 200 OK | Resource created successfully (some APIs) |
| 202 Accepted | Request accepted for asynchronous processing |

---

# Positive Test Scenarios

- Create a resource using valid data.
- Create a resource with all required fields.
- Create a resource with optional fields.
- Verify the resource is stored successfully.
- Verify response body contains the created resource.
- Verify generated resource ID.
- Verify creation timestamp (if applicable).

---

# Negative Test Scenarios

- Missing required fields.
- Invalid data types.
- Duplicate resource creation.
- Invalid authentication token.
- Missing authentication.
- Unauthorized user.
- Invalid request payload.
- Unsupported media type.
- Invalid JSON format.

---

# Edge Case Scenarios

- Maximum field lengths.
- Minimum field lengths.
- Empty strings.
- Null values.
- Unicode characters.
- Special characters.
- Large payloads.
- High-volume POST requests.
- Rate limiting.
- Simultaneous resource creation.

---

# Validation Checklist

Verify that:

- Correct HTTP status code is returned.
- Resource is created successfully.
- Response body matches the submitted data.
- Generated IDs are unique.
- Required fields are validated.
- Duplicate resources are handled correctly.
- Authentication and authorization are enforced.
- Database records are created correctly.
- Audit fields are populated where applicable.

---

# Example Success Response

```http
HTTP/1.1 201 Created
```

```json
{
    "id": 101,
    "firstName": "Joy",
    "lastName": "Chepchumba",
    "email": "joy@example.com",
    "phone": "0712345678",
    "createdAt": "2026-07-22T08:30:15Z"
}
```

---

# Common Defects

Examples of issues commonly found while testing POST APIs:

- Duplicate records created.
- Missing validation on required fields.
- Incorrect HTTP status codes.
- Invalid response schema.
- Sensitive information exposed.
- Database record not created.
- Duplicate unique identifiers allowed.
- Server returns 500 instead of validation errors.

---

# Best Practices

- Verify successful resource creation.
- Validate all required fields.
- Test duplicate creation scenarios.
- Verify generated identifiers.
- Validate response schema.
- Check database consistency (where applicable).
- Test authorization thoroughly.
- Test invalid payloads and malformed JSON.
- Verify appropriate error messages are returned.

---

# POST vs PUT

| POST | PUT |
|------|-----|
| Creates a new resource | Replaces an existing resource |
| Usually not idempotent | Idempotent |
| Server often generates the resource ID | Client usually specifies the resource ID |
| Returns **201 Created** | Returns **200 OK** or **204 No Content** |

---

# Learning Outcome

After completing this section, readers should understand how to test POST endpoints by validating request payloads, response structures, business rules, authentication, and data persistence while applying REST API testing best practices.
