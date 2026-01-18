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
- [Raw Data (PDF or KAGGLE THING)] (LINK)

---
## Approach

### Step 1: Data Cleaning & Preparation
Raw MotoGP race and results data required standardization before analysis. In this step, I:
- Cleaned and standardized rider, team, and circuit names for consistency
- Parsed race and qualifying results into structured, numeric formats
- Removed incomplete or invalid records (e.g., missing finishes)
- Flagged DNFs and crashes to ensure they could be analyzed separately from classified finishes
- Applied minimum race participation thresholds to prevent small sample sizes from distorting results

**Output:** a clean, analysis-ready dataset with consistent identifiers and reliable race outcomes.

### Step 2: Metric Definition & KPI Calculation
Before analyzing performance, I defined metrics aligned with the business questions rather than relying on raw totals. Key KPIs included:
- Championship points
- Average and median finishing position
- Podium rate and win rate
- Qualifying position vs. race finish delta
- DNF / crash rate
- Track performance index

These metrics were calculated using aggregation logic in Excel (Power Query and PivotTables) to ensure consistency and repeatability.

**Output:** a structured KPI dataset designed to support fair rider and team comparisons.

### Step 3: Analytics & Business Question Analysis
Using the calculated KPIs, I analyzed rider and team performance with a focus on consistency and sustained success:
- Evaluated rider consistency using **average finishing position** rather than total wins or points
- Compared classified finishes across the season to identify riders who perform strongly race-to-race
- Analyzed team dominance using **total championship points combined with race participation**
- Examined performance variation across different circuits to identify track-specific strengths

This approach avoids overvaluing isolated wins and highlights consistent, repeatable performance.

### Step 4: Interpretation & Insights
Results were interpreted through a business lens:
- Riders with lower average finishing positions and high classification rates demonstrated the strongest consistency
- Teams with consistently high point totals across multiple races showed sustained dominance
- Teams with high participation but lower point totals indicated potential reliability or execution issues, supported by DNF analysis

Insights were documented alongside metric definitions and assumptions to ensure transparency.

### Step 5: Reporting & Scalability
Findings were summarized using pivot tables and structured outputs designed to scale into SQL and visualization tools such as Tableau. Emphasis was placed on:
- Choosing metrics that directly answer the business questions
- Documenting data limitations and assumptions
- Designing the dataset to support future expansion and deeper analysis

**Output:** clear, business-relevant insights backed by documented metrics and scalable data design.

--- 
## Results
- Identified riders with the strongest consistency based on average finishing position
- Observed clear separation between consistently competitive riders and mid-pack performers
- Results are visualized in the dashboard below to support comparison and interpretation
  
<img width="1094" height="692" alt="Screenshot 2026-01-17 at 11 57 43 PM" src="https://github.com/user-attachments/assets/a8db0d54-9753-422a-bb8e-b8ea61e054ec" />

---
## Tools

- **Excel / Power Query** – cleaned and standardized raw race data, handled missing values, and prepared analysis-ready datasets  
- **Pivot Tables** – calculated KPIs including average finish, podium rate, win rate, and DNF rate  
- **Dashboarding** – built an interactive dashboard to visualize rider consistency and performance trends  
- **Data Analysis & Metrics Design** – defined KPIs aligned to business questions rather than raw totals  
- **Documentation** – documented assumptions, metric definitions, and data limitations for transparency and reuse




