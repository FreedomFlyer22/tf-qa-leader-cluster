---
WEBFLOW CMS FIELDS
---
Title: How to Run a Full QA Project in TestFiesta (From Milestone to Defect)
Slug: qa-project-management
Meta Title: Test Plan Management: Run a Full QA Project in TestFiesta
Meta Description: Most QA teams manage projects across three tools. TestFiesta consolidates test cases, runs, defects, and reporting in one place. Here's the complete project lifecycle.
Category: QA Leadership
Author: TestFiesta Team
Published Date: 2026-05-19
Featured Image Alt: QA project management from milestone to defect in TestFiesta
---
ARTICLE BODY
---

# How to Run a Full QA Project in TestFiesta (From Milestone to Defect)

Most QA teams run their projects across three tools. A test management tool for test cases and runs. A bug tracker for defects. A spreadsheet for milestones, release tracking, and the status reports that go to product and engineering leadership.

The friction between these tools is constant. Defects logged in Jira need to be cross-referenced with the test cases that found them. Milestone progress tracked in a spreadsheet needs to be manually updated every time a test run completes. Status reports require pulling data from all three sources and reconciling it into a format that makes sense to someone who does not live in any of them.

TestFiesta consolidates the full QA project lifecycle into one tool. Test cases, test runs, defects, milestones, and reporting all live in the same system. This article walks through a complete QA project from start to finish — from creating the first milestone to closing the last defect.

## Projects — The Organizational Container

In TestFiesta, a project is the top-level container for all QA work related to a product or application. A project contains test cases, test runs, milestones, and defects. Most teams create one project per product — a web application, a mobile app, and an API might each have their own project.

**Creating a project:**

1. Navigate to the TestFiesta dashboard and click **New Project**
2. Enter the project name and description
3. Select the test case template to apply (or create a new template)
4. Configure the project settings — default configurations, Jira integration, team access

The project settings define the structural foundation for everything that follows. Take 15 minutes to configure them correctly before writing the first test case.

**Project settings that matter most:**

- **Test case template:** Defines the fields every test case in the project uses. Set this before writing test cases — changing the template after test cases exist requires updating existing test cases.
- **Jira integration:** If the team uses Jira for defect tracking, connect the Jira project here. Defects logged in TestFiesta will sync to Jira automatically.
- **Default configurations:** The environments the project tests against. Set these up front so test runs can use them immediately.

## Milestones — Planning Release Cycles

Milestones represent release targets or significant testing checkpoints. A milestone has a name, a target date, and a set of test runs associated with it.

**Creating a milestone:**

1. In the project, navigate to **Milestones** → **New Milestone**
2. Enter the milestone name (e.g., "v2.4 Release" or "Sprint 14 Regression")
3. Set the target date
4. Add a description with the release scope and testing objectives

**What milestones track:**

- Overall test execution progress across all runs associated with the milestone
- Blocking defects — defects that must be resolved before the milestone can be released
- Test coverage — percentage of test cases in scope that have been executed
- Release readiness — configurable threshold (e.g., 95% pass rate on critical path tests, zero P1 defects open)

The milestone view gives QA leads and product managers a single answer to the question "are we ready to release?" — without requiring anyone to manually aggregate data from multiple runs.

## Test Plans — Organizing Runs by Milestone

A test plan is a collection of test runs organized around a milestone or a testing objective. Where a milestone tracks the release target, a test plan defines the testing strategy for reaching it.

**Creating a test plan:**

1. In the milestone, click **New Test Plan**
2. Name the plan (e.g., "v2.4 Full Regression" or "Sprint 14 Smoke Tests")
3. Add the test runs that belong to this plan
4. Set the execution order if runs have dependencies

**Test plan structure for a typical release cycle:**

| Run | Scope | Timing |
|---|---|---|
| Smoke tests | Critical path — 20–30 test cases | Day 1 of testing cycle |
| Feature regression | New features in this release | Days 2–4 |
| Full regression | Complete test suite | Days 3–7 |
| Exploratory testing | Unscripted, risk-based | Days 5–7 |
| Sign-off run | Critical path re-run | Day 7 (release day) |

The test plan makes the testing strategy explicit and trackable. Stakeholders can see not just how many tests have passed, but which phase of the testing cycle the team is in.

## Test Runs — Executing Against a Plan

A test run is a specific execution of a set of test cases against a defined configuration. It is the operational unit of QA work — the thing testers actually do.

**Creating a test run:**

1. In the test plan, click **New Run**
2. Name the run (e.g., "Sprint 14 Regression — Chrome/macOS")
3. Select the test cases to include — from the full project library, filtered by tags, or from a saved filter
4. Select the configurations to run against
5. Assign testers to the run (optionally assign specific test cases to specific testers)
6. Set the target completion date

**Assigning testers:**

TestFiesta supports two assignment models:

- **Run-level assignment:** All testers assigned to the run can execute any test case in it. Good for small teams where testers work through the run collaboratively.
- **Test case-level assignment:** Specific test cases are assigned to specific testers. Good for larger teams where testers specialize by feature area or where accountability tracking is important.

**Tracking progress in real time:**

Once a run is active, the run dashboard shows execution progress in real time — test cases executed versus remaining, pass/fail/blocked breakdown, tester progress, and estimated completion time based on current velocity.

The shareable dashboard link lets product managers and developers check progress without asking the QA lead for a status update. See [how to build QA dashboards your whole team will actually use](/blog/qa-dashboards) for the full dashboard setup guide.

## The Personal Workspace Tab — Each Tester's View

When a tester is assigned to one or more test runs, their personal Workspace tab becomes their primary working view. The Workspace tab is a personal to-do list scoped to their assigned test cases across all active runs.

**What the Workspace tab shows:**

- All test cases assigned to the tester across all active runs, in priority order
- Execution status for each assigned test case — not started, in progress, completed
- The run and project each test case belongs to
- Quick access to execute the next assigned test case

**Why the Workspace tab matters:**

In a team running multiple test runs simultaneously, individual testers can lose track of what they are supposed to be working on. The Workspace tab eliminates that confusion — it is always current, always scoped to the individual tester's work, and always shows the most important test cases first.

The Workspace tab is not a separate product or account type. It is a tab within the organizational workspace, available to every tester in the organization at no additional cost. It is distinct from the team-level dashboard — the team dashboard shows aggregate progress for QA leads and stakeholders, while the Workspace tab shows individual progress for the tester doing the work.

## Test Cases — The Building Blocks

Test cases in TestFiesta follow the template defined at the project level. Each test case has:

- **Title:** A specific, action-oriented description of what is being tested
- **Preconditions:** The state the system must be in before the test begins
- **Steps:** The sequence of actions the tester takes
- **Expected results:** What the system should do at each step
- **Custom fields:** Any additional data the team tracks (risk level, automation status, Jira ticket reference)

**Writing effective test cases:**

The most common test case quality problem is vague expected results. "The system should work correctly" is not an expected result. "The user is redirected to the dashboard and a success notification appears in the top right corner" is an expected result.

Specific expected results make test execution faster (testers know exactly what to look for), make defect logging more accurate (testers can describe exactly what happened versus what was expected), and make test case maintenance easier (when the expected behavior changes, the expected result is easy to update).

For AI-assisted test case generation that produces specific, context-aware test cases, see [AI test case generation that actually understands your context](/blog/ai-test-case-generation).

## Defects — Built-In Defect Tracking

TestFiesta includes built-in defect tracking. Defects can be logged directly from a failed test step — no context switching to a separate bug tracker required.

**Logging a defect from a test step:**

1. During test execution, mark a step as Failed
2. Click **Log Defect** on the failed step
3. The defect form pre-populates with the test case name, the failed step, and the expected result
4. Add the actual result, severity, and any attachments (screenshots, log files)
5. Submit — the defect is created and linked to the test case and test run

**Defect fields in TestFiesta:**

- Title (pre-populated from the test case)
- Description (actual result versus expected result)
- Severity (P1 Critical, P2 High, P3 Medium, P4 Low)
- Status (Open, In Progress, Fixed, Verified, Closed)
- Assignee
- Attachments
- Tags
- Linked test case and test run

**Jira sync:**

For teams that use Jira as their primary defect tracker, TestFiesta's Jira integration syncs defects bidirectionally. A defect logged in TestFiesta creates a corresponding Jira issue. Status updates in Jira sync back to TestFiesta. The QA team works in TestFiesta; the engineering team works in Jira; both see the same defect data.

**Defect workflow:**

1. Tester logs defect from failed test step in TestFiesta
2. Defect syncs to Jira automatically (if Jira integration is enabled)
3. Developer fixes the defect and updates status in Jira to "Fixed"
4. Status syncs back to TestFiesta — defect shows as "Fixed"
5. QA tester re-executes the failed test case to verify the fix
6. If the fix is verified, tester marks the defect as "Verified" and the test case as "Pass"
7. Defect closes when the release ships

## Reporting Across the Full Project

TestFiesta's reporting covers the full project lifecycle — from test case coverage through execution progress to defect resolution.

**Key reports:**

- **Coverage report:** What percentage of the application's features have test cases? What percentage have been executed in the current cycle?
- **Execution report:** Pass/fail/blocked breakdown by run, by tester, by feature area, by risk level
- **Defect report:** Open defects by severity, defect trend over time, mean time to resolution
- **Release readiness report:** Configurable thresholds — pass rate, blocking defect count, coverage percentage — with a clear go/no-go indicator

All reports are available as live dashboards (shareable without a TestFiesta account) and as exports (CSV, PDF) for teams that need to include QA data in external reports.

## The Full Lifecycle in One Tool

Here is the complete QA project lifecycle in TestFiesta, from first milestone to final sign-off:

1. **Create project** — set template, configure Jira integration, define configurations
2. **Create milestone** — set release target date, define release scope
3. **Write test cases** — using template, shared steps, and AI generation for efficiency
4. **Create test plan** — organize runs by testing phase (smoke, regression, exploratory)
5. **Create test runs** — select test cases, assign configurations, assign testers
6. **Execute tests** — testers work from their personal Workspace tab
7. **Log defects** — directly from failed test steps, synced to Jira
8. **Track progress** — QA lead monitors run dashboard; stakeholders check shared dashboard link
9. **Verify fixes** — re-execute failed test cases after developer fixes
10. **Release sign-off** — milestone release readiness report shows go/no-go

No spreadsheets. No manual status reports. No context switching between three tools. The full QA project lifecycle in one place.

## Frequently Asked Questions

### What is test plan management?

Test plan management is the practice of organizing test runs into structured plans that map to release milestones or testing objectives. A test plan defines which test cases will be executed, in what order, against which configurations, and by which testers — providing a structured approach to achieving test coverage goals.

### Does TestFiesta replace Jira for defect tracking?

TestFiesta's built-in defect tracking handles most QA team needs without Jira. For teams that use Jira as their single source of truth for all engineering work, TestFiesta's Jira integration syncs defects bidirectionally — QA teams work in TestFiesta, engineering teams work in Jira, and both see the same data.

### How does the personal Workspace tab differ from a test run?

A test run is a team-level execution of a set of test cases. The personal Workspace tab is an individual tester's view of their assigned test cases across all active runs. The Workspace tab aggregates assignments from multiple runs into a single personal to-do list — the tester does not need to navigate between runs to find their work.

### Can multiple testers work on the same test run simultaneously?

Yes. Multiple testers can execute test cases in the same run simultaneously. TestFiesta handles concurrent execution without conflicts — each tester's results are recorded independently, and the run dashboard updates in real time as results come in.

### How does TestFiesta handle test case re-execution after a defect fix?

When a defect is marked as Fixed, TestFiesta flags the associated test case for re-execution. The tester who originally logged the defect is notified. Re-execution results are tracked separately from the original execution — the run history shows both the original failure and the subsequent verification.

### Can I track test coverage by feature area?

Yes. Using TestFiesta's tag system, test cases tagged by feature area can be filtered and reported on independently. A coverage report filtered to the "checkout" tag shows exactly how many checkout test cases exist, how many have been executed, and what the pass rate is — without manual data aggregation.

### What happens to defects when a release ships?

Defects that are Verified (fix confirmed by QA) are typically closed when the release ships. Defects that are still Open or In Progress at release time are carried forward to the next milestone. TestFiesta's milestone view shows the defect status at the time of release — providing a historical record of what shipped with known issues.

---

QA projects that span three tools are QA projects that generate friction. Every context switch, every manual data reconciliation, every status report assembled from multiple sources is time that could be spent testing. TestFiesta consolidates the full project lifecycle — test cases, runs, defects, milestones, and reporting — so the QA team can focus on the work that actually improves product quality.

**[Start Free Account → app.testfiesta.com/signup](https://app.testfiesta.com/signup)**
