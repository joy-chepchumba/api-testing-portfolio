# Update (PUT & PATCH) Requests Testing

## Overview

The **PUT** and **PATCH** HTTP methods are used to update existing resources in a REST API.

Although both perform updates, they serve different purposes:

- **PUT** replaces the entire resource.
- **PATCH** updates only the specified fields.

Understanding the difference is essential for designing accurate API test cases.

---

# PUT vs PATCH

| Method | Purpose | Request Body | Idempotent |
|---------|---------|--------------|------------|
| PUT | Replace an entire resource | Complete object | Yes |
| PATCH | Update specific fields | Partial object | Usually Yes |

---

# PUT Request Flow

```
Client
   │
PUT /api/users/101
   │
Validate Request
   │
Replace Resource
   │
Save Changes
   ▼
Return Updated Resource
```

---

# PATCH Request Flow

```
Client
   │
PATCH /api/users/101
   │
Validate Fields
   │
Update Specified Values
   │
Save Changes
   ▼
Return Updated Resource
```

---

# Example PUT Request

```http
PUT /api/users/101
Authorization: Bearer <token>
```

```json
{
    "firstName": "Joy",
    "lastName": "Chepchumba",
    "email": "joy@example.com"
}
```

---

# Example PATCH Request

```http
PATCH /api/users/101
Authorization: Bearer <token>
```

```json
{
    "email": "newemail@example.com"
}
```

---

# Expected Success Responses

| Status Code | Meaning |
|-------------|---------|
| 200 OK | Resource updated successfully |
| 204 No Content | Update successful without response body |

---

# Positive Test Scenarios

- Update an existing resource using PUT.
- Update a single field using PATCH.
- Update multiple fields.
- Verify updated values are persisted.
- Verify unchanged fields remain unchanged after PATCH.
- Verify response structure.

---

# Negative Test Scenarios

- Update a non-existent resource.
- Missing required fields (PUT).
- Invalid field values.
- Invalid authentication token.
- Missing authentication.
- Unauthorized update attempt.
- Invalid resource ID.
- Unsupported field updates.

---

# Edge Case Scenarios

- Update with maximum field lengths.
- Update with empty values.
- Update with Unicode characters.
- Update with special characters.
- Simultaneous updates.
- Multiple PATCH requests on the same resource.
- Updating immutable fields.

---

# Validation Checklist

Verify that:

- Correct HTTP status code is returned.
- Updated values are stored correctly.
- Unchanged values remain unchanged (PATCH).
- Response body reflects updated data.
- Validation rules are enforced.
- Authentication and authorization are respected.
- Database consistency is maintained.
- Audit fields (if applicable) are updated correctly.

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
    "email": "newemail@example.com"
}
```

---

# Common Defects

Examples of issues commonly found while testing PUT and PATCH APIs:

- Incorrect fields updated.
- Entire object overwritten during PATCH.
- Required fields not validated.
- Data loss after PUT request.
- Unauthorized updates allowed.
- Incorrect status codes returned.
- Validation rules bypassed.
- Audit information not updated.

---

# Best Practices

- Verify idempotency of PUT requests.
- Ensure PATCH updates only specified fields.
- Validate response schema.
- Confirm data persistence.
- Test authorization thoroughly.
- Verify immutable fields cannot be modified.
- Check audit trail updates where applicable.
- Test concurrent update scenarios.
