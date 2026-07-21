# Delete (DELETE) Requests Testing

## Overview

The **DELETE** HTTP method is used to remove an existing resource from a REST API.

DELETE requests permanently remove a resource (unless soft delete is implemented). A successful DELETE should ensure the resource is no longer accessible.

Unlike POST, DELETE is generally **idempotent**, meaning repeating the same request should not create additional side effects.

---

# DELETE Request Flow

```
Client
   │
DELETE /api/users/101
   │
Validate Authentication
   │
Validate Authorization
   │
Locate Resource
   │
Delete Resource
   ▼
Return Success Response
```

---

# Example DELETE Request

```http
DELETE /api/users/101
Authorization: Bearer <token>
```

---

# Expected Success Responses

| Status Code | Meaning |
|-------------|---------|
| 200 OK | Resource deleted successfully |
| 202 Accepted | Delete request accepted for processing |
| 204 No Content | Resource deleted successfully with no response body |

---

# Positive Test Scenarios

- Delete an existing resource.
- Delete a resource using valid authentication.
- Verify the resource no longer exists.
- Verify subsequent GET returns **404 Not Found**.
- Verify database record is removed (where applicable).

---

# Negative Test Scenarios

- Delete a non-existent resource.
- Missing authentication token.
- Invalid authentication token.
- Unauthorized user.
- Invalid resource ID.
- Malformed request.

---

# Edge Case Scenarios

- Delete the same resource multiple times.
- Delete resources with dependencies.
- Concurrent DELETE requests.
- Delete locked or protected resources.
- Delete already archived resources.

---

# Validation Checklist

Verify that:

- Correct HTTP status code is returned.
- Resource is actually deleted.
- Deleted resource cannot be retrieved.
- Database reflects the deletion.
- Authorization rules are enforced.
- Appropriate error messages are returned.
- Audit logs are generated if applicable.

---

# Example Success Response

```http
HTTP/1.1 204 No Content
```

or

```json
{
    "message": "Resource deleted successfully."
}
```

---

# Common Defects

Examples of issues commonly found while testing DELETE APIs:

- Resource remains accessible after deletion.
- Incorrect HTTP status codes.
- Unauthorized users can delete resources.
- Multiple DELETE requests return inconsistent responses.
- Related records are not handled correctly.
- Soft delete not functioning as expected.

---

# DELETE Characteristics

| Property | Value |
|----------|-------|
| Purpose | Remove a resource |
| Idempotent | Yes |
| Safe | No |
| Request Body | Usually not required |

---

# Best Practices

- Verify successful deletion.
- Confirm resource is inaccessible after deletion.
- Validate authorization.
- Test repeated DELETE requests.
- Verify database consistency.
- Check related resource handling.
- Verify audit logging where applicable.

---

# Learning Outcome

After completing this section, readers should understand how to validate DELETE endpoints by verifying resource removal, authorization, response handling, idempotency, and overall data integrity.
