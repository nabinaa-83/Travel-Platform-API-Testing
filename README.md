# Travel & Trekking Platform - API Testing Portfolio

This repository contains the comprehensive QA test cases and API testing documentation for a specialized travel and trekking application, simulating professional backend validation methodologies.

## 1. Trek Package API Testing (`GET /api/trek-package`)

| Test Case ID | Scenario / Description | Input / Condition | Expected Result | Status |
| :--- | :--- | :--- | :--- | :--- |
| TC_TP_001 | Verify successful retrieval of all available trek packages. | Valid request header | `200 OK`, returns a list of packages matching database data. | Pass |
| TC_TP_002 | Verify API behavior when no trek packages exist in the database. | Database table is empty | `200 OK`, returns an empty array `[]`. | Pass |
| TC_TP_003 | **[Negative Test]** Verify system response to an invalid authorization token. | Expired or incorrect token | `401 Unauthorized`, blocks access with clear error message. | Pass |


## 2. Gallery API Testing (`/api/gallery`)

| Test Case ID | Endpoint & Method | Scenario / Description | Input / Condition | Expected Result |
| :--- | :--- | :--- | :--- | :--- |
| TC_GAL_001 | `GET /api/gallery` | Verify all gallery image links load successfully. | Valid authorization header | `200 OK`, returns array of image URLs and meta tags. |
| TC_GAL_002 | `POST /api/gallery` | Verify a manager can successfully upload a valid image file. | `.jpg` or `.png` file under 5MB | `201 Created`, image uploaded and stored correctly. |
| TC_GAL_003 | `POST /api/gallery` | **[Negative Test]** Verify system blocks unsupported file uploads. | `.exe` or `.txt` file payload | `400 Bad Request`, payload rejected with validation error. |
| TC_GAL_004 | `GET /api/gallery/{id}` | Verify retrieval of a single specific gallery image asset by ID. | Valid target Image ID | `200 OK`, returns exact object details matching the ID. |
| TC_GAL_005 | `GET /api/gallery/{id}` | **[Negative Test]** Verify request response for a non-existent item ID. | Non-existent string ID | `404 Not Found`, returns standard resource error message. |
