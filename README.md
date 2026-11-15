# IncidentIQ
### IT Incident Triage Console

## 1. Project Overview

IncidentIQ is a Java 25 command-line application that helps an IT support team register incidents, calculate their priority, and identify major incidents based on impact, urgency, and the number of affected users.

After all incidents are registered, the program displays an operational summary.

## 2. Problem Statement

In an IT environment, many incidents can be reported at the same time. The support team needs a simple way to decide which incidents need attention first.

IncidentIQ collects the incident details, validates them, calculates a priority score, decides the response target, and checks whether the incident is a major incident.

## 3. Application Features

- Register multiple incidents in one run.
- Generate sequential incident IDs (INC-001, INC-002, INC-003, ...).
- Collect title, affected service, description, affected users, impact, and urgency.
- Validate every input and ask again when the input is invalid.
- Clean text input by removing extra spaces.
- Accept the service name in any letter case (for example `nEtWoRk`) and store it in a standard form (`Network`).
- Automatically calculate the priority score, priority level, and response target.
- Detect major incidents using two escalation conditions and show the reason for the alert.
- Display an incident report after each incident.
- Display an operational summary at the end.
- **Optional enhancement (Option D, Keyword Analysis):** show a warning when the description contains keywords such as `unavailable`, `crash`, `disconnected`, `inaccessible`, or `failed`.

## 4. Priority Calculation Formula

**Priority Score = (Impact × 2) + (Urgency × 2)**

| Score | Priority | Response Target |
|---|---|---|
| 13–16 | P1 - Critical | 1 hour |
| 9–12 | P2 - High | 4 hours |
| 5–8 | P3 - Medium | 8 hours |
| 4 | P4 - Low | 24 hours |

These response targets are illustrative rules for this assignment, not official industry SLA standards.

## 5. Major Incident Escalation Rules

An incident is a major incident if either condition is true:

**Condition A**
- Impact = 4
- Affected users ≥ 50

**OR**

**Condition B**
- Impact ≥ 3
- Urgency = 4
- Affected users ≥ 25

If Condition A is true, the reason shown is "Critical impact affecting at least 50 users." Otherwise, if Condition B is true, the reason shown is "High impact with immediate urgency affecting at least 25 users."

## 6. Java Concepts Used

- Java 25 compact source file with `void main()`
- `IO.print()` and `IO.println()`
- Variables and data types (`int`, `double`, `String`, `boolean`)
- Scanner for user input
- Type conversion (`(double)` casting for the average)
- Arithmetic operators (`+`, `*`, `/`, `++`)
- Relational operators (`>=`, `<=`, `==`)
- Logical operators (`&&`, `||`, `!`)
- `if`, `else if`, `else`, and nested conditions
- `while` loops with boolean flags for input validation
- `switch` statements to convert levels into labels
- String methods (listed in Section 7)
- Counters and accumulators for the summary

## 7. Methods Implemented

The whole application is written inside `main()`. No user-defined methods are used. The program uses only the predefined String and Scanner methods below.

**String methods**

| Method | Where it is used and why |
|---|---|
| `strip()` | Removes extra spaces from the title, service, description, and yes/no answers. |
| `isBlank()` | Rejects a blank or whitespace-only title or description. |
| `equalsIgnoreCase()` | Checks the service category and the yes/no answers without caring about letter case. |
| `substring()` | Splits the service name into its first letter and the rest. |
| `toUpperCase()` | Capitalizes the first letter of the service name. |
| `toLowerCase()` | Lowercases the rest of the service name, and lowercases the description before keyword search. |
| `contains()` | Searches the description for warning keywords (Option D). |
| `isEmpty()` | Checks whether a keyword was found. |

**Scanner methods**

| Method | Purpose |
|---|---|
| `nextLine()` | Reads text inputs and yes/no answers. Also clears the leftover newline after `nextInt()`. |
| `nextInt()` | Reads affected users, impact, and urgency. |

**Main program sections (inside `main()`)**

| Section | Responsibility |
|---|---|
| Incident title loop | Reads the title until it is not blank. |
| Service loop | Reads the service until it matches a permitted category, then standardizes it. |
| Description loop | Reads the description until it is not blank. |
| Affected users loop | Reads the number until it is at least 1. |
| Impact and urgency loops | Read the values until they are between 1 and 4. |
| ID generation | Builds IDs like INC-001 using the incident counter. |
| Priority calculation | Calculates the score, priority, and response target. |
| Major incident check | Evaluates Condition A and Condition B. |
| Incident report | Displays the incident details and results. |
| Keyword analysis | Warns if the description contains a keyword. |
| Summary section | Displays the totals, average, and P1/P2 percentage. |

## 8. Instructions to Run the Application

1. Install Java 25 (or later).
2. Download or clone the repository.
3. Open a terminal in the project folder.
4. Run the program:

   `java Main.java`

   (Or open `Main.java` in IntelliJ IDEA and run it.)
5. Enter the incident details when asked.
6. Type `yes` to register another incident or `no` to finish.
7. Read the operational summary.

## 9. Sample Output

The actual output generated by the program is in `sample-output.txt`.

## 10. Screenshots

Screenshots of the running application are in the `screenshots` folder.

## 11. Current Limitations

- If a letter or symbol is typed where a number is expected (affected users, impact, urgency), the program crashes. Preventing this needs concepts not covered yet, such as `hasNextInt()` or `try-catch`.
- Incident records are not stored. Only counters are kept for the summary, and all data is lost when the program ends.
- Decimal numbers are not accepted for numerical inputs.
- The keyword analysis is basic text matching. It is not an intelligent diagnosis.
- The program runs only in the console and has no graphical interface.
- All logic is inside `main()`, so the code is long and harder to reuse.

## 12. Possible Future Improvements

- Divide the code into user-defined methods (validation, priority calculation, report display) to make it shorter and easier to maintain.
- Handle non-numeric input without crashing.
- Store incident records in a file or database.
- Allow searching for an incident by its ID.
- Add options to update or close an incident.
- Add more optional features, such as a Repeat Incident Indicator or Service Reliability Watch.
- Add a graphical user interface.
