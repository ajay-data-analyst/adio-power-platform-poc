# ADIO Power Platform Accelerator — Project Management Dashboard

**Client:** Abu Dhabi Investment Office (ADIO) — delivered as a freelance engagement via Truelancer
**Role:** Independent Power BI Developer & Power Platform Consultant
**Stack:** Power BI Desktop & Service · DAX · Power Query (M) · Power Automate · Dataverse · Data Modeling (Star Schema)

---

## Overview

This project was a Power Platform proof-of-concept delivered for ADIO's PMO (Project Management Office) function — a working accelerator combining a Power BI reporting layer with Power Automate workflow automation, built to demonstrate how project and task visibility across departments could move from manual status updates to a single, structured, branded system.

> **Note on data:** all screenshots and sample data in this repo use placeholder/sample values structured to match the real project's shape. Actual client data is confidential and is not included here.

---

## Business Problem

ADIO needed a fast, working proof-of-concept showing how Microsoft's Power Platform could modernize internal project and portfolio tracking — replacing scattered status updates and manual reporting with a single system covering:
- Project workload across departments
- Task-level distribution and status
- Cross-departmental visibility for strategic initiatives (Technology & Innovation, Finance & Investment, Strategy & Planning, Risk & Compliance)

## Solution

I designed and delivered an end-to-end accelerator with two connected components:

### 1. Power BI Project Management Dashboard
- **Overview page:** total projects, total tasks, workload by project, task distribution by department
- **Detailed task-monitoring page:** project name, program/department, task-level status, drill-down beyond the summary view
- **Data model:** structured around a star schema linking Projects → Tasks → Departments/Programs, built for clean filtering and fast performance
- **Branding:** ADIO's official navy & gold visual identity applied across every report page

### 2. Power Automate Workflow Layer
- Automated task escalation flows to reduce manual follow-up between teams
- Status-update triggers tied to task state changes

## My Role & Responsibilities

- Owned the project end-to-end as an independent consultant — from data structuring through final delivery
- Translated ADIO's project-tracking requirements into a working data model and report layout suited to executive/PMO-level review
- Debugged and corrected automation logic in the Power Automate flows to ensure reliable task escalation behavior
- Applied brand guidelines precisely across every visual element for a presentation-ready final deliverable
- Iterated through a full remediation pass after initial delivery — correcting DAX aggregation logic, fixing broken flows, and resolving solution dependencies before final handoff

## Technical Details

**Data Model**
- Star schema: fact table (Tasks) related to dimension tables (Projects, Departments/Programs, Dates)
- Relationships built for one-directional filtering to keep report performance fast as task volume grows

**DAX Measures (representative examples — logic shown, values are illustrative)**
```dax
Total Projects = DISTINCTCOUNT(Projects[ProjectID])

Total Tasks = COUNTROWS(Tasks)

Tasks by Department =
CALCULATE(
    COUNTROWS(Tasks),
    ALLEXCEPT(Tasks, Tasks[Department])
)
```

**Power Automate**
- Trigger: task status change in Dataverse
- Action: conditional escalation notification based on task age/priority
- Rebuilt during remediation to resolve a broken trigger condition from the initial delivery

## Business Impact

The completed accelerator gave ADIO a working demonstration of how Power BI and Power Automate can unify project visibility across departments — moving from scattered manual updates toward a single, structured, branded reporting system, and showing that a lean Power Platform build can meet the standards expected by a government-level stakeholder group.

## Client Feedback

> "Excellent work, thank you"
> — 5-star rating, ADIO client, via Truelancer

![Client review](screenshots/truelancer-review.png)

## Screenshots

/screenshots/dashboard-overview.png
/screenshots/department(program view).png
/screenshots/project list.png
/screenshots/task-monitoring-detail.png

## Tools & Technologies

`Power BI Desktop` · `Power BI Service` · `DAX` · `Power Query (M)` · `Power Automate` · `Dataverse` · `Data Modeling` · `Star Schema Design`

---

## About Me

I'm Ajay Kumar, a freelance Power BI Developer & BI Consultant specializing in turning messy data into automated, decision-ready dashboards.

📧 ajthakur7273@gmail.com
💼 [LinkedIn](https://linkedin.com/in/ajay6469)
🗂️ [More projects](https://github.com/ajay-data-analyst)
