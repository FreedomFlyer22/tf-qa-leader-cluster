---
WEBFLOW CMS FIELDS
---
Title: How to Build a Flexible Test Case Structure Without Losing Your Mind
Slug: flexible-test-case-structure
Meta Title: Test Case Management: Build a Flexible Structure That Scales
Meta Description: Copy-paste test cases and inconsistent formats make test suites unmaintainable. Here's how to use templates, custom fields, and shared steps to fix it once.
Category: QA Leadership
Author: TestFiesta Team
Published Date: 2026-05-19
Featured Image Alt: Flexible test case structure with templates and shared steps
---
ARTICLE BODY
---

# How to Build a Flexible Test Case Structure Without Losing Your Mind

Most QA teams spend more time maintaining their test suite than running it. Copy-pasted steps that break when a shared flow changes. Inconsistent formats that make it impossible to filter or report across test cases. Custom fields that were added one at a time with no coherent system behind them. A test suite that started clean and became unmaintainable somewhere around sprint 20.

The problem is not the team. It is the structure — or the lack of one. Test case management is not just about writing test cases. It is about building a system where test cases stay accurate, stay organized, and stay useful as the product evolves.

TestFiesta's setup features — templates, custom fields, shared steps, tags, and configurations — are designed to solve this once. Not repeatedly, not sprint by sprint, but as a foundation that scales with the team.

## The Maintenance Problem

The average QA team rewrites or updates 30–40% of their test suite every quarter. Some of that is legitimate — the product changed, the requirements changed, the test cases need to reflect reality. But a significant portion of that maintenance work is structural: fixing inconsistencies, updating copy-pasted steps that should have been shared steps, adding fields that should have been in the template from the start.

Every hour spent on structural maintenance is an hour not spent on testing. The goal of a well-designed test case structure is to make the legitimate maintenance fast and eliminate the structural maintenance entirely.

## Templates — Define the Format Once

TestFiesta test case templates define the structure that every test case in a project follows. Not suggestions — enforced structure. When a template is applied to a project, every new test case uses that template's fields, field order, and required/optional designations.

**What templates control:**

- Which fields appear in the Overview tab versus the Details tab
- Which fields are required before a test case can be saved
- Whether test execution uses status-by-step (each step gets a pass/fail) or single overall status
- Which result statuses are available (Pass, Fail, Blocked, Skipped — or custom statuses)
- Whether a defect must be created when a test step fails

**The practical impact:** A QA team that defines its template before writing the first test case never has to go back and add fields to 400 existing test cases. The template enforces consistency from day one.

**Result templates** are a separate but related concept. Where test case templates define the structure of the test case itself, result templates define what happens when a test is executed. A result template can require a defect to be created when a test fails, require a comment when a test is blocked, or enforce a specific set of result statuses for a particular type of testing.

For teams running compliance testing or regulated workflows, result templates provide the audit trail enforcement that manual processes cannot guarantee.

## Custom Fields — Capture What Matters to Your Team

Default test case fields cover the basics: title, description, preconditions, steps, expected results. They do not cover everything a QA team needs to track.

TestFiesta custom fields let teams add any data point that matters to their workflow — and define exactly how that data is captured.

**Available field types:**

- **Text** — free-form notes, external ticket references, environment details
- **Dropdown** — controlled vocabulary for fields like risk level, test type, or automation status
- **Date** — last reviewed date, scheduled execution date
- **Number** — test case priority score, estimated execution time in minutes
- **Checkbox** — boolean flags like "requires data setup" or "flaky test"
- **URL** — link to the feature spec, the Jira ticket, the design file

**The automation status field** is one of the most valuable custom fields a QA team can add. A dropdown with values like Manual, Automated, In Progress, and Blocked gives the team an instant view of automation coverage across the test suite — filterable, reportable, and always current.

**Mapping to external systems:** Custom fields can be mapped to Jira fields, so data entered in TestFiesta flows automatically to the corresponding Jira field without manual re-entry. For teams running TestFiesta alongside Jira, this eliminates the double-entry problem that makes cross-tool workflows painful.

## Shared Steps — Write Once, Use Everywhere

Shared steps are the single most impactful structural feature in TestFiesta for teams with test suites larger than a few hundred test cases.

The problem they solve: every test case that requires a user to be logged in starts with the same three steps. Log in, navigate to the dashboard, verify the user is authenticated. When the login flow changes — and it will change — every test case that contains those steps needs to be updated. If those steps are copy-pasted across 200 test cases, that is 200 updates. If they are a shared step, it is one.

**How shared steps work in TestFiesta:**

1. Create a shared step with a name and the step sequence it contains
2. Insert the shared step into any test case with a single click
3. When the shared step is updated, every test case that uses it reflects the change automatically

**Nested shared steps** extend this further. A shared step can contain other shared steps — so a "complete checkout flow" shared step can contain a "log in" shared step, an "add item to cart" shared step, and a "enter payment details" shared step. Update any component and the change propagates through every test case that uses it, at any level of nesting.

The organizational discipline required: shared steps need names that make their content obvious. "Login flow" is a good shared step name. "Step 1" is not. Teams that invest 30 minutes in naming conventions for shared steps save hours of confusion later.

For a complete guide to organizing shared steps alongside tags and configurations, see [the QA leader's guide to test organization](/blog/test-case-organization).

## Tags — Multidimensional Organization

Folders organize test cases in one dimension. Tags organize them in as many dimensions as the team needs.

A single test case can have tags for its feature area (checkout), its risk level (high), its sprint (sprint-14), its environment (mobile), and its test type (regression). Filtering by any combination of those tags returns exactly the test cases that match — without restructuring the folder hierarchy.

**Where tags apply in TestFiesta:**

- Test cases — the primary use case
- Test runs — tag a run as regression, smoke, or exploratory
- Users — tag team members by role or specialization for assignment filtering
- Defects — tag defects by severity, component, or root cause

**The sprint tag pattern** is particularly useful for agile teams. Tag every test case added or modified in a sprint with that sprint's tag. At the end of the sprint, filter by the sprint tag to see exactly which test cases were touched — without maintaining a separate spreadsheet.

## Configurations — Build Your Test Matrix

Configurations define the environments, browsers, devices, and operating systems that test cases run against. A configuration is not a test case — it is a dimension that gets applied to a test run.

**The test matrix use case:** A web application that needs to be tested on Chrome, Firefox, Safari, and Edge across Windows and macOS has eight environment combinations. Without configurations, a QA team either runs the same test cases eight times manually (tracking results in a spreadsheet) or skips the matrix testing entirely.

With TestFiesta configurations, a single test run can be executed across all eight configurations simultaneously. Results are tracked per configuration, so the team can see at a glance that the checkout flow passes on Chrome/Windows but fails on Safari/macOS — without any manual result aggregation.

**Setting up configurations:**

1. Define your configuration dimensions (browser, OS, device type)
2. Create the specific configurations you test against (Chrome/Windows, Safari/macOS, etc.)
3. When creating a test run, select which configurations to include
4. Assign testers to specific configurations or let the system distribute automatically

For teams running mobile testing, device configurations work the same way — define the device models and OS versions you test against, and the configuration system tracks results per device automatically.

## How They Work Together

The real power of TestFiesta's structure features comes from using them in combination.

A well-structured TestFiesta project looks like this:

- **Template** defines the fields every test case captures — title, preconditions, steps, expected result, automation status (dropdown), risk level (dropdown), last reviewed date
- **Shared steps** handle every repeated sequence — login flow, navigation to key pages, data setup sequences
- **Tags** provide multidimensional filtering — feature area, sprint, risk level, environment, test type
- **Configurations** define the test matrix — browsers, devices, environments
- **Custom fields** capture team-specific data — Jira ticket reference, estimated execution time, compliance requirement mapping

A QA lead who sets up this structure before the team writes their first test case creates a system that stays maintainable as the test suite grows from 50 test cases to 5,000. The structural maintenance work — the copy-paste updates, the field additions, the reorganizations — largely disappears.

## Getting Started: The Right Order

The most common mistake when setting up a new TestFiesta project is writing test cases before defining the template. Once test cases exist, changing the template requires updating every existing test case. Define the structure first.

**Recommended setup sequence:**

1. Define your test case template — required fields, optional fields, result statuses
2. Create your shared steps library — start with the five most common repeated sequences
3. Set up your tag taxonomy — feature areas, risk levels, test types (keep it simple at first)
4. Define your configurations — the environments you actually test against
5. Write your first test cases using the structure you have defined

The full project lifecycle — from this structure setup through test runs, defect tracking, and reporting — is covered in [how to run a full QA project in TestFiesta](/blog/qa-project-management).

## Frequently Asked Questions

### What is test case management?

Test case management is the practice of creating, organizing, executing, and maintaining test cases in a structured system. A test case management tool provides the infrastructure for this — storing test cases, tracking execution results, managing defects, and reporting on coverage and progress.

### How do TestFiesta templates differ from TestRail templates?

TestFiesta templates control field structure, required fields, result statuses, and defect creation rules — similar to TestRail's case types. The key difference is that TestFiesta templates apply at the project level and enforce consistency across all test cases in that project, while TestRail's case types are applied per test case and can vary within a project.

### Can I have different templates for different types of testing?

Yes. TestFiesta supports multiple templates within a project — so a functional testing template can have different fields and result statuses than a performance testing template or a security testing template. Each test case is assigned to a template when it is created.

### How many shared steps can a project have?

There is no limit on shared steps in TestFiesta. Large test suites typically have 50–200 shared steps covering common flows, navigation sequences, and data setup procedures. The shared step library is searchable, so finding the right shared step in a large library takes seconds.

### Can tags be used for reporting?

Yes. Any tag can be used as a filter in TestFiesta's reporting and dashboard views. A dashboard showing test execution progress filtered by the current sprint tag, broken down by risk level tag, gives QA leads the release-readiness view they need without any manual data aggregation.

### What happens to test cases when a shared step is updated?

All test cases that use the shared step reflect the update immediately. There is no propagation delay and no manual update required. This is the core value of shared steps — one update, universal effect.

### How do configurations work with test assignments?

When a test run includes multiple configurations, testers can be assigned to specific configurations or to all configurations. A tester assigned to the Chrome/Windows configuration only sees and executes test cases for that configuration. Results are tracked per tester per configuration, so the team has full visibility into who tested what and what the results were.

---

A test suite that nobody can maintain is a test suite that does not get used. Templates, custom fields, shared steps, tags, and configurations are the structural primitives that keep a test suite maintainable as it grows. Set them up before writing the first test case and the maintenance problem largely solves itself.

**[Start Free Account → app.testfiesta.com/signup](https://app.testfiesta.com/signup)**
