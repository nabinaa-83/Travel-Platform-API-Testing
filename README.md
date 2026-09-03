# Travel & Trekking Platform - API Testing Portfolio

This repository contains the comprehensive QA test cases and API testing documentation for a specialized travel and trekking application, simulating professional backend validation methodologies.

## 1. Trek Package API Testing (`GET /api/trek-package`)

| Test Case ID | Scenario / Description | Input / Condition | Expected Result | Status |
| :--- | :--- | :--- | :--- | :--- |
| TC_TP_001 | Verify successful retrieval of all available trek packages. | Valid request header | `200 OK`, returns a list of packages matching database data. | Pass |
| TC_TP_002 | Verify API behavior when no trek packages exist in the database. | Database table is empty | `200 OK`, returns an empty array `[]`. | Pass |
| TC_TP_003 | **[Negative Test]** Verify system response to an invalid authorization token. | Expired or incorrect token | `401 Unauthorized`, blocks access with clear error message. | Pass |

