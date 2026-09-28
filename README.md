# Day 13 – Excel Data Analyst Challenge:Employee Stress Level Analysis — Power BI Dashboard

A Power BI dashboard built for an organization's wellness program. It analyzes survey and activity data to show what drives employee stress, which employees are at risk, and how stress changes over time, so management can design better workplace policies.

## Files

| File | Description |
|---|---|
| `day-13-data-analysis_challenge.pbix` | Power BI report (data model, DAX measures, dashboard) |
| `stress_analysis_data.csv` | Source data (300 employees, no missing values) |
| `Day13_Coding_Challenge.pdf` | Original challenge brief |

## Dataset

| Column | Description |
|---|---|
| `EmployeeID` | Unique employee identifier |
| `Department` | Employee department (Finance, IT, Marketing, Operations, HR) |
| `Age` | Employee age |
| `Gender` | Male / Female |
| `WorkHours` | Average daily work hours |
| `SleepHours` | Average daily sleep hours |
| `ExerciseHours` | Average weekly exercise hours |
| `CaffeineIntake` | Daily cups of coffee/tea |
| `StressLevel` | Stress rating (1 = Low, 5 = Very High) |
| `DateRecorded` | Survey date (Jan 1 – Apr 1, 2025) |

## DAX measures

| Measure | Purpose |
|---|---|
| `Average Stress level` | Company-wide average stress rating |
| `% of Employees with High Stress` | Share of employees with `StressLevel >= 4` |
| `Avg Sleep vs Work Ratio` | Average sleep hours divided by average work hours |
| `stress level cat` | Category (Low / Medium / High) used by the donut chart |

## Dashboard contents

**KPI cards**
- Average stress level (company-wide)
- % of employees with high stress
- Avg sleep vs work ratio

**Charts**
- **Column chart:** average stress level by department
- **Line chart:** stress level trend over time (date hierarchy)
- **Scatter plot:** work hours vs. stress level, with trend line
- **Donut chart:** distribution of employees across stress categories

**Table with conditional formatting**
- Employee-level table (stress, sleep) with formatting to highlight at-risk employees (StressLevel = 5 and SleepHours < 5)

**Slicers**
- Department
- Gender

## Key insights

Figures below are calculated from the source CSV.

- **Stress is elevated overall.** Average stress is about 2.98 out of 5, and roughly 41% of employees report high stress (rating 4 or 5).
- **Finance and IT are the most stressed departments** (about 3.33 and 3.13 average), while HR is the lowest (about 2.67).
- **Sleep is short relative to work.** Employees average about 5.95 hours of sleep against 8.59 work hours, a ratio of roughly 0.69.
- **Women report slightly higher stress** than men (about 3.12 vs. 2.87).
- **12 employees are in the critical group** (stress = 5 and sleep < 5 hours) and are good candidates for direct wellness outreach.
- **Stress is flat over the period** (about 3.0 each month, January to April), and individual factors such as work hours, sleep, exercise, and caffeine show very weak linear correlation with stress in this dataset. Department and other unmeasured factors likely matter more than any single habit.

## How to use

1. Open `day-13-data-analysis_challenge.pbix` in Power BI Desktop.
2. Use the Department and Gender slicers to filter every visual.
3. Check the employee table for highlighted at-risk employees.
4. Refresh the data (**Home → Refresh**) if `stress_analysis_data.csv` changes.

## Known gaps / next steps

- **Age Group slicer:** the brief requires one, but the report only has Department and Gender slicers. Add an `Age Group` calculated column (e.g., <30, 30–39, 40–49, 50+) and a slicer on it.
- **Custom titles:** visuals use default titles; descriptive titles would improve readability.
- **Insights on the dashboard:** consider adding the insights above as a text box so the .pbix is self-contained.
