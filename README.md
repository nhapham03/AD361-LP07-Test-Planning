# Learning Practice 07: Test Planning - North Vacation Booking Application

## Step 1: Define the Test Context

| Section      | Description                                                                                                                                                  |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Objective 1  | Confirm that users can create a valid booking by selecting a rental, entering check-in and checkout dates, and entering the number of guests.                |
| Objective 2  | Validate inputs such as a checkout date has to be after the check-in date, or a guest count below 1, is rejected with a message and no booking is created.   |
| In scope     | Rental selection, check-in and checkout date fields, guest count field, increase/decrease/reset controls, booking creation, and the "View my bookings" list. |
| Out of scope | Payment processing, account creation and user login, email confirmations, host/admin features and performance or load testing.                               |
| Test basis   | Booking requirements, user stories, UI designs/wireframes, and the application source code.                                                                  |
| Assumption   | Requirements and user stories are final and will not change during the test period.                                                                          |
| Constraint   | All testing must be completed within one week before the release date.                                                                                       |

---

## Step 2: Roles and Responsibilities

| Role                | Responsibilities                                                                                                                             | When Involved                                                                       | Communication                                                                                                   |
| ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| Test Leader/Manager | Writes and maintains the test plan, assigns roles, tracks progress, decides if exit criteria are met, and writes the test completion report. | From start to finish - planning, execution and test completion                      | Reports progress and risks to the product owner, coordinates with testers and developers                        |
| Tester              | Writes test cases, prepares test data, executes manual and automated tests, logs defects, and retests fixes.                                 | Test design and test execution                                                      | Reports defects to developers, reports daily progress to the test leader/manager                                |
| Developer           | Writes unit/component tests, fixes defects, provides testable builds, and supports the test environment.                                     | Before testing (unit tests, builds) and during execution (defect fixes)             | Receives defects from tester, lets the the tester know when a fix is ready for retest                           |
| Product Owner       | Clarifies requirements and acceptance criteria, and gives project approval.                                                                  | Planning (answer team's questions), requirements review and approval/final decision | Answers questions from testers and developers, receives the test completion report from the test leader/manager |
---



## Step 3: Test Approach

| Test Area         | Test Level or Type       | Technique                | Manual or Automated | Deliverable                    |
| ----------------- | ------------------------ | ------------------------ | ------------------- | ------------------------------ |
| Booking form      | Component / Functional   | Boundary value analysis  | Automated           | Jest test file                 |
| Booking dates     | Component / Functional   | Equivalence partitioning | Automated           | Jest test file                 |
| Full booking flow | System / Usability       | Exploratory testing      | Manual              | Test results, defect reports   |
| Whole app         | System / Regression      | Re-run test suite        | Automated           | Test completion report         |

---

## Step 4: Test Requirements

- **Test environment:** Setup a backend database with fake data that can reset
- **Browsers or devices:** Web browsers like Chrome, Brave, Edge, etc and one mobile screen size
- **Testing tools:** Jest and GitHub
- **Test data:** Sample rentals, valid and invalid dates, guest counts from 0 to the maximum
- **Access:** Staging URL and GitHub repository access
- **People and training:** Tester, developer, and product owner

---

## Step 5: Risk Register

| Risk                                            | Type         | Likelihood | Impact | Mitigation                              |
| ----------------------------------------------- | ------------ | ---------- | ------ | --------------------------------------- |
| A user can book with checkout before check-in   | Product risk | Medium     | High   | Test date validation first              |
| The guest count can go below 1                  | Product risk | Medium     | Medium | Test counter limits with automated tests |
| The test environment is unavailable             | Project risk | Low        | High   |

---

## Step 6 + 7: Entry and Exit Criteria

| Type  | Criterion                                             |
| ----- | ----------------------------------------------------- |
| Entry | The application opens in the test environment         |
| Entry | All planned test cases have been written and reviewed |
| Entry | Test data is loaded in the test environment           |
| Exit  | 100% of high-priority tests have been executed        |
| Exit  | No critical or high-severity defects remain open      |
| Exit  | Final regression tests pass 100%                      |

---

## Step 8: Test Schedule

| Activity                | Responsible Role         | Time    | Dependency                      |
| ----------------------- | ------------------------ | ------- | ------------------------------- |
| Review requirements     | Tester and product owner | Day 1   | Requirements are available      |
| Design test cases       | Tester                   | Day 2   | Requirements have been reviewed |
| Run tests               | Tester                   | Day 3–4 | Entry criteria are met          |
| Fix and retest defects  | Developer and tester     | Day 4   | Defects have been reported      |
| Write completion report | Tester                   | Day 5   | Exit criteria are met           |

---

## Step 9: Communication Plan

| Information       | Audience      | Method         | Frequency              |
| ----------------- | ------------- | -------------- | ---------------------- |
| Test progress     | Project team  | Daily stand up | Daily                  |
| Defect report     | Developer     | GitHub issue   | When a defect is found |
| Completion report | Product owner | Email          | End of testing         |
