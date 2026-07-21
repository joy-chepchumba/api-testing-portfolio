# CRUD Operations Testing

CRUD stands for **Create, Read, Update, and Delete**. These are the four fundamental operations performed on data in most REST APIs.

Testing CRUD operations ensures that an API correctly creates new resources, retrieves existing data, updates information accurately, and safely removes records while maintaining data integrity and expected business behavior.

---

# CRUD Operations

| Operation | HTTP Method | Purpose |
|------------|------------|---------|
| Create | POST | Create a new resource |
| Read | GET | Retrieve one or more resources |
| Update | PUT / PATCH | Modify an existing resource |
| Delete | DELETE | Remove a resource |

---

# Why CRUD Testing Matters

CRUD testing helps verify that:

- Resources are created successfully.
- Data can be retrieved accurately.
- Updates are saved correctly.
- Deleted resources are no longer accessible.
- API responses follow expected HTTP status codes.
- Data validation rules are enforced.
- Authentication and authorization are respected.
- Business rules are maintained throughout the resource lifecycle.

---

# Testing Areas Covered

This section includes documentation for:

- POST (Create) Testing
- GET (Read) Testing
- PUT & PATCH (Update) Testing
- DELETE Testing
- CRUD Test Cases
- CRUD Best Practices

---

# Common HTTP Status Codes

| Status Code | Meaning |
|-------------|---------|
| 200 OK | Request completed successfully |
| 201 Created | Resource created successfully |
| 204 No Content | Request successful with no response body |
| 400 Bad Request | Invalid request data |
| 401 Unauthorized | Authentication required or invalid |
| 403 Forbidden | User lacks permission |
| 404 Not Found | Resource does not exist |
| 409 Conflict | Duplicate or conflicting resource |
| 422 Unprocessable Entity | Validation failed |
| 500 Internal Server Error | Unexpected server error |

---

# General CRUD Test Scenarios

Typical CRUD testing includes:

### Positive Testing

- Create a resource with valid data.
- Retrieve existing resources.
- Update a resource successfully.
- Delete a resource successfully.

### Negative Testing

- Missing required fields.
- Invalid data types.
- Duplicate resource creation.
- Unauthorized access.
- Invalid resource IDs.
- Updating non-existent resources.
- Deleting non-existent resources.

### Edge Case Testing

- Maximum field lengths.
- Empty values.
- Special characters.
- Unicode characters.
- Large payloads.
- Concurrent updates.
- Repeated DELETE requests.
- Rate limiting behavior.

---

# Best Practices

When testing CRUD APIs, always verify:

- Correct HTTP status codes.
- Response body structure.
- Response time.
- Database consistency (where applicable).
- Authentication and authorization.
- Error messages.
- Data persistence after updates.
- Resource deletion behavior.
- Idempotency of PUT and DELETE operations.

---

# Repository Structure

```
CRUD-Operations-Testing/
│
├── README.md
├── Create-POST-Requests.md
├── Read-GET-Requests.md
├── Update-PUT-PATCH-Requests.md
├── Delete-DELETE-Requests.md
├── CRUD-Test-Cases.md
└── CRUD-Best-Practices.md
```

---

# Learning Outcome

After completing this section, readers should understand how to design, execute, and document comprehensive CRUD API tests while applying REST API testing best practices used in real-world Quality Assurance projects.
