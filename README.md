# IncidentIQ
### IT Incident Triage Console

## 1. Project Overview

IncidentIQ is a simple Java-based IT Incident Triage Console. It allows users to register IT incidents, calculate their priority, and identify major incidents based on their impact, urgency, and affected users.

The program also generates an operational summary after all incidents have been registered.

## 2. Problem Statement

In an IT environment, different incidents can affect users and services. It is important to identify which incidents need immediate attention.

IncidentIQ helps organize incidents and assign priorities so that critical problems can be identified first.

## 3. Application Features

- Register multiple IT incidents.
- Generate a unique incident ID for every incident.
- Accept incident title, service, description, affected users, impact, and urgency.
- Validate user inputs.
- Automatically calculate the priority score.
- Assign priority levels from P1 to P4.
- Identify major incidents.
- Display an incident report.
- Generate a final operational summary.

## 4. Priority Calculation Formula

The program calculates the priority score using:

**Priority Score = (Impact × 2) + (Urgency × 2)**

Priority classification:

| Score | Priority | Response Target |
|---|---|---|
| 13–16 | P1 - Critical | 1 hour |
| 9–12 | P2 - High | 4 hours |
| 5–8 | P3 - Medium | 8 hours |
| 4 | P4 - Low | 24 hours |

## 5. Major Incident Escalation Rules

An incident is considered a major incident if either of these conditions is satisfied:

**Condition A**
- Impact is equal to 4.
- Affected users are 50 or more.

**Condition B**
- Impact is at least 3.
- Urgency is equal to 4.
- Affected users are 25 or more.

If either condition is true, the program displays a major incident alert.

## 6. Java Concepts Used

The following Java concepts were used:

- Variables and data types
- Scanner for user input
- If-else conditions
- While loops
- Boolean variables
- Logical operators
- String methods
- User-defined methods
- Method parameters and return values
- Mathematical calculations

## 7. Methods Implemented

| Method | Responsibility |
|---|---|
| `calculatePriorityScore()` | Calculates the incident priority score. |
| `determinePriority()` | Determines the priority level. |
| `getResponseTarget()` | Returns the response target based on priority. |
| `isMajorIncident()` | Checks whether an incident qualifies as a major incident. |
| `displaySummary()` | Displays the final operational summary. |

## 8. Instructions to Run the Application

1. Install Java 25 or a compatible version.
2. Open the project in IntelliJ IDEA.
3. Open the `Main.java` file.
4. Run the program.
5. Enter the incident details when requested.
6. Register more incidents or enter `no` to finish.
7. View the final operational summary.

## 9. Sample Output

The sample output is available in the `sample-output.txt` file.

## 10. Screenshots

Screenshots of the application execution will be added to the `screenshots` folder.

## 11. Current Limitations

- The program currently accepts integer values for numerical inputs.
- It does not store incident records permanently.
- All incident information is lost when the program ends.
- The application runs through the console and does not have a graphical interface.

## 12. Possible Future Improvements

- Store incident records in a file or database.
- Add a graphical user interface.
- Allow users to search for incidents using their incident IDs.
- Add options to update or
