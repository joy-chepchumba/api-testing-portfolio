# 📊 Login API Test Summary Report

## Document Information

| Item                 | Details                                     |
| -------------------- | ------------------------------------------- |
| **Project**          | ShopEasy (Fictional E-commerce Application) |
| **Module**           | Login API                                   |
| **Prepared By**      | Joy Chepchumba                              |
| **Document Version** | 1.0                                         |
| **Date**             | 2026-07-20                                  |
| **Test Cycle**       | API Functional Testing Cycle 1              |

---

# 1. Objective

The purpose of this test summary report is to provide an overview of the API testing activities completed for the Login API and summarize the overall quality of the feature before release.

---

# 2. Scope of Testing

The following areas were validated:

* Login with valid credentials
* Login with invalid credentials
* Required field validation
* Invalid request payloads
* Bearer Token Authentication
* HTTP Status Code Validation
* Error response validation
* Response body verification
* Response time verification
* Security and authentication behaviour

---

# 3. Test Execution Summary

| Metric               | Result |
| -------------------- | ------ |
| **Total Test Cases** | 12     |
| **Executed**         | 12     |
| **Passed**           | 11     |
| **Failed**           | 1      |
| **Blocked**          | 0      |
| **Not Executed**     | 0      |

---

# 4. Defects Summary

| Bug ID      | Description                                                            | Severity | Status |
| ----------- | ---------------------------------------------------------------------- | -------- | ------ |
| API-BUG-001 | Expired Bearer Token returns HTTP 500 instead of HTTP 401 Unauthorized | Critical | Open   |

---

# 5. Risks Identified

* Authentication failures are not handled correctly for expired tokens.
* Client applications receive an incorrect server error, making troubleshooting more difficult.
* API behaviour does not fully align with REST API best practices.

---

# 6. Overall Quality Assessment

The Login API is functionally stable for the majority of tested scenarios. However, one Critical defect was identified relating to expired Bearer Token handling.

The issue should be resolved and regression testing completed before the API is approved for production deployment.

---

# 7. Recommendation

**Release Status:** ❌ Not Ready for Production

The Login API should not be released until:

* API-BUG-001 has been resolved.
* Authentication error handling returns the correct HTTP status codes.
* Regression testing has been completed successfully.
* No Critical or High severity defects remain open.

---

# 8. Lessons Learned

* Authentication scenarios should include valid, invalid, missing, and expired tokens.
* HTTP status code validation is essential to ensure REST API compliance.
* Negative API testing helps identify issues that are not visible through successful request scenarios.

---

# 9. Approval

| Role              | Status           |
| ----------------- | ---------------- |
| QA Analyst        | ✅ Completed      |
| Backend Developer | Pending Fix      |
| Product Owner     | Pending Approval |

---

# Document History

| Version | Date           | Author             | Description                                        |
| ------- | -------------- | ------------------ | -------------------------------------------------- |
| **1.0** | **2026-07-20** | **Joy Chepchumba** | Initial creation of Login API Test Summary Report. |
