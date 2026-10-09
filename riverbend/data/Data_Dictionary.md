# Riverbend Community Services — Data Dictionary
### Integrated 622 shared course dataset · Fall 2026

**This dataset is simulated.** Riverbend Community Services is a fictional organization, and no row describes a real person. The data was built from a stated model of how an organization like this works, which is the kind of honest simulation this course teaches. We use the same data in all three modules.

---

## The organization

Riverbend Community Services is a regional nonprofit providing **home health visits, case management, and client transportation** from **8 service sites**. It employs about 400 staff. Funding comes from a county contract, foundation grants, and fee-for-service billing.

The data covers **8 quarters, January 2024 through December 2025**.

In **2025, three sites (S1, S4, S7) began using SmartShift**, a new scheduling system intended to reduce overtime and turnover. The other five sites did not. Leadership wants to know whether SmartShift worked and should be rolled out everywhere.

Also in early 2025, Riverbend **moved to a new HR information system**.

---

## Two tables

| | `staff_quarters.csv` | `site_weeks.csv` |
|---|---|---|
| **One row is** | one employee in one quarter | one site in one week |
| **Rows** | 3,215 | 832 (8 sites × 104 weeks) |
| **Comes from** | HR information system, payroll, quarterly engagement survey | Case management system, scheduling, client surveys |

**How they connect:** both tables have `site_id` and `quarter`. A quarter contains about 13 weeks. Before you combine the tables, decide what a row of the combined table should be.

---

## `staff_quarters.csv`

| Column | Description |
|---|---|
| `employee_id` | Employee identifier from the HR system |
| `quarter` | Calendar quarter, `2024Q1` through `2025Q4` |
| `site_id` | Site where the employee worked that quarter (S1–S8) |
| `manager_id` | The employee's manager that quarter |
| `role` | Home Health Aide, Nurse, Case Manager, Intake Coordinator, Driver, Admin, or Supervisor |
| `job_level` | Job level, 1 (entry) to 4 (senior) |
| `employment_type` | Full-time or Part-time |
| `hire_date` | Date of hire, as recorded in the HR system |
| `tenure_years` | Years since hire, at the start of the quarter (0 for employees hired during the quarter) |
| `age_band` | Under 30, 30–39, 40–49, 50+ |
| `pay_hourly` | Hourly pay rate in dollars |
| `commute_miles` | One-way distance from home to site, in miles |
| `caseload` | Clients assigned during the quarter (0 for roles without a caseload) |
| `overtime_hours` | Overtime hours worked during the quarter, from payroll |
| `training_completed` | 1 if the employee completed the quarter's professional development training, 0 if not |
| `engagement` | Response to the engagement survey question "I would recommend Riverbend as a place to work," from 1 (strongly disagree) to 5 (strongly agree). Blank if the employee did not respond. |
| `left_org` | 1 if the HR system recorded the employee as leaving Riverbend during the quarter, 0 if not |
| `exit_reason` | Reason given in the exit interview, if one was held. Blank otherwise. |

## `site_weeks.csv`

| Column | Description |
|---|---|
| `site_id` | Site (S1–S8) |
| `week_start` | Monday the week begins |
| `quarter` | Calendar quarter the week starts in |
| `site_type` | Urban, Suburban, or Rural |
| `smartshift_live` | 1 if the site was using SmartShift that week, 0 if not |
| `staff_on_roster` | Staff employed at the site that quarter |
| `open_positions` | Budgeted positions unfilled that quarter |
| `cases_opened` | New client referrals opened that week |
| `cases_closed` | Client cases recorded as closed that week |
| `median_intake_wait_days` | Median days from referral to first visit, for clients first seen that week |
| `missed_visits` | Scheduled visits that did not happen that week |
| `documentation_errors` | Visit records flagged by quality review that week |
| `satisfaction_responses` | Number of client satisfaction surveys returned that week |
| `client_satisfaction` | Average client rating that week, on a 1–5 scale |

---

## Things worth knowing

- Data from real organizations is never perfectly clean, and neither is this. Part of your work is finding where it might mislead you.
- Ask your AI analyst what a row is, what kind of variable each column is, and what looks odd. Then check its answers.

I eagerly await your puzzles.
