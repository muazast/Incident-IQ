# IncidentIQ – Test Cases

## Test Case 1: Register a Valid Incident

**Objective:** Check whether the program accepts valid incident details.

**Input:**
- Title: Internet Not Working
- Service: Network
- Description: Office internet connection is down
- Affected Users: 10
- Impact: 2
- Urgency: 2

**Expected Result:** Incident should be registered successfully with priority P3 - Medium.

**Actual Result:** To be filled after testing.

**Status:** Pending

---

## Test Case 2: Blank Incident Title

**Objective:** Check whether the program rejects an empty title.

**Input:**
- Title: Empty

**Expected Result:** Program should ask the user to enter the title again.

**Actual Result:** To be filled after testing.

**Status:** Pending

---

## Test Case 3: Blank Incident Description

**Objective:** Check whether the program rejects an empty description.

**Input:**
- Description: Only spaces

**Expected Result:** Program should reject the description and ask again.

**Actual Result:** To be filled after testing.

**Status:** Pending

---

## Test Case 4: Invalid Service Category

**Objective:** Check whether the program accepts only the permitted service categories.

**Input:**
- Service: Software

**Expected Result:** Program should reject the service and ask again.

**Actual Result:** To be filled after testing.

**Status:** Pending

---

## Test Case 5: Invalid Affected Users

**Objective:** Check whether the program rejects zero or negative affected users.

**Input:**
- Affected Users: 0

**Expected Result:** Program should ask for a valid number of affected users.

**Actual Result:** To be filled after testing.

**Status:** Pending

---

## Test Case 6: Invalid Urgency

**Objective:** Check whether the program rejects urgency values above 4.

**Input:**
- Urgency: 5

**Expected Result:** Program should reject the value and ask again.

**Actual Result:** To be filled after testing.

**Status:** Pending

---

## Test Case 7: P4 Priority Calculation

**Objective:** Check the lowest priority calculation.

**Input:**
- Impact: 1
- Urgency: 1

**Expected Result:**
- Priority Score: 4
- Priority: P4 - Low
- Response Target: 24 hours

**Actual Result:** To be filled after testing.

**Status:** Pending

---

## Test Case 8: P1 Priority Calculation

**Objective:** Check the highest priority calculation.

**Input:**
- Impact: 4
- Urgency: 4

**Expected Result:**
- Priority Score: 16
- Priority: P1 - Critical
- Response Target: 1 hour

**Actual Result:** To be filled after testing.

**Status:** Pending

---

## Test Case 9: Major Incident Detection

**Objective:** Check whether the program identifies a major incident.

**Input:**
- Impact: 4
- Urgency: 2
- Affected Users: 50

**Expected Result:** Program should display a major incident alert.

**Actual Result:** To be filled after testing.

**Status:** Pending

---

## Test Case 10: Multiple Incident Registration

**Objective:** Check whether the program can register multiple incidents and calculate the final summary.

**Input:**
- Register first incident with impact 4 and urgency 4.
- Register second incident with impact 1 and urgency 2.
- Enter no when asked to register another incident.

**Expected Result:**
- Two incidents should be registered.
- Priority counts should be correct.
- Total affected users should be correct.
- Average affected users should be correct.
- P1/P2 percentage should be correct.

**Actual Result:** To be filled after testing.

**Status:** Pending
