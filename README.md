# 🏁 MotoGP Performance Analysis

## Objective
The goal of this project was to analyze MotoGP race and rider data to understand performance trends,
consistency across seasons, and key factors influencing race outcomes.

## Table of Contents
- [Data](#data)
- [Approach](#approach)
- [Results](#results)
- [Tools](#tools)

---
## Data
The dataset includes MotoGP race results, lap times, rider information, and season-level statistics
sourced from publicly available MotoGP records.

More information about the dataset can be found in the following links:
- [MotoGP Championship Standings](ogp.com/en/world-standing/2025/motogp/championship-standings)
- [Raw Dataset](https://www.kaggle.com/datasets/sammee/motogp-race-results-2022)

---
## Approach

### Step 1: Data Cleaning & Preparation (Excel)

Raw MotoGP race results required standardization before analysis. Excel was used as the initial environment to understand the structure of the data and validate its quality. During this step, I:

- Standardized rider names to ensure consistent identifiers across all records
- Verified data types for finishing positions, points, and session counts
- Reviewed records for missing or invalid values and removed incomplete results where necessary
- Used PivotTables to validate summary statistics (finishing positions, total sessions) against known season outcomes

This step ensured the dataset was internally consistent and suitable for aggregation.

<img width="781" height="672" alt="Screenshot 2026-01-18 at 9 19 18 PM" src="https://github.com/user-attachments/assets/0b6f1dad-2d05-4ed8-b5be-78fc78af9808" />

**Output:** a clean, analysis-ready dataset with validated rider-level results.

### Step 2: Metric Definition & Aggregation (SQL)

Rather than analyzing individual race results directly, I defined metrics aligned with the core analytical question: rider consistency across the season.

Using SQL, I aggregated the cleaned race data to create rider-level performance metrics, including:

- Average finishing position across all competitive sessions
- Total number of competitive sessions completed per rider (Sprint + Grand Prix)
- Rider-level grouping to prevent individual race results from skewing the analysis

<img width="946" height="538" alt="Screenshot 2026-01-18 at 8 59 39 PM" src="https://github.com/user-attachments/assets/2697f3dd-e67e-4136-abd8-b830e67159f9" />

<img width="946" height="571" alt="Screenshot 2026-01-18 at 9 08 23 PM" src="https://github.com/user-attachments/assets/7d7518df-105c-4731-a8d4-f19f44c357bf" />

SQL was used specifically for its ability to perform repeatable aggregations and produce a compact analytical table optimized for visualization.

**Output:** a structured rider-level dataset containing average finish position and total session counts.

### Step 3: Analytical Framing & Business Logic

The analysis focused on consistency rather than peak performance. Instead of emphasizing wins or podium counts, riders were evaluated based on their average finishing position across the season.

This approach highlights sustained, repeatable performance and avoids overvaluing isolated race results. Including both Sprint and Grand Prix sessions provides a more complete view of competitive workload and season-long reliability.

### Step 4: Visualization & Insight Delivery (Tableau)

Tableau was used to translate the aggregated SQL output into a clear, interpretable visualization. A horizontal bar chart was chosen to rank riders by average finishing position, with lower values indicating greater consistency.

Key design choices included:

- Filtering to the bottom performers by average finish (Top 10 most consistent riders)
- Applying a sequential color scale to reinforce performance differences without overwhelming the viewer
- Custom tooltips displaying average finish position and total competitive sessions for additional context
- Minimal visual clutter to keep the focus on comparative performance

<img width="1094" height="692" alt="Screenshot 2026-01-17 at 11 57 43 PM" src="https://github.com/user-attachments/assets/a8db0d54-9753-422a-bb8e-b8ea61e054ec" />

The final dashboard emphasizes clarity, interpretability, and analytical intent.

### Step 5: Reporting & Scalability

The final outputs were designed to be portable and scalable. Metrics are clearly defined, assumptions are transparent, and the dataset structure allows for future expansion, such as separating Sprint and Grand Prix results or incorporating additional seasons.

<img width="418" height="405" alt="Screenshot 2026-01-18 at 9 34 44 PM" src="https://github.com/user-attachments/assets/01a4a98f-a564-4719-a553-5ccb3d63ec07" />
<img width="1385" height="678" alt="Screenshot 2026-01-18 at 9 35 16 PM" src="https://github.com/user-attachments/assets/a0bf1088-b6e7-4ada-8e2f-326bed690441" />

This workflow supports reproducibility across Excel, SQL, and visualization tools while maintaining a clear analytical narrative.

--- 
## Results
- Identified riders with the strongest consistency based on average finishing position
- Observed clear separation between consistently competitive riders and mid-pack performers
- Results are visualized in the dashboard below to support comparison and interpretation

---
## Tools

- **Excel / Power Query** – cleaned and standardized raw race data, handled missing values, and prepared analysis-ready datasets  
- **Pivot Tables** – calculated KPIs including average finish, podium rate, win rate, and DNF rate  
- **Dashboarding** – built an interactive dashboard to visualize rider consistency and performance trends  
- **Data Analysis & Metrics Design** – defined KPIs aligned to business questions rather than raw totals  
- **Documentation** – documented assumptions, metric definitions, and data limitations for transparency and reuse




