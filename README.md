# HR Analytics: Visualizing Employee Attrition Drivers

Presented By: Sibangi Subhadarsani  
Date: December 6, 2025  

---

## 📌 Project Overview

Employee attrition poses a significant operational and financial challenge to organizations. This project analyzes an HR dataset to uncover key drivers of turnover, leveraging data visualization techniques in Tableau to transform raw data into actionable retention strategies.

Over iterative design cycles incorporating feedback from the Tableau Community and AI-driven critiques, the analysis evolved from simple exploratory visualization into a targeted, narrative-driven investigation.


```

```
             +-----------------------------------+
             |      The Big Picture (Overview)   |
             +-----------------------------------+
                               |
                               v
             +-----------------------------------+
             |    Who Is Leaving? (Profile)      |
             +-----------------------------------+
                               |
                               v
             +-----------------------------------+
             |    Why Are They Leaving? (Causes) |
             +-----------------------------------+
                               |
                               v
             +-----------------------------------+
             |   When Do They Leave? (Journey)   |
             +-----------------------------------+

```
```
## 🔍 Key Questions & Findings

**Theme 1: Overview & High-Level Drivers**
* **Overall Attrition:** What is the company's overall baseline turnover?
  * *Finding:* The company has an overall attrition rate of **16.12%**.
* **Workload Impact:** Does overtime correlate with higher turnover?
  * *Finding:* Employees working overtime exhibit a **30.53%** attrition rate compared to **10.44%** for non-overtime workers.
* **Role Volatility:** Which roles face the highest risk?
  * *Finding:* Sales Representatives (**39.76%**), Laboratory Technicians (**23.94%**), and HR (**23.08%**) show elevated turnover.

**Theme 2: Demographic & Job Profiles**
* **Gender & Department Disparities:** Are attrition rates uniform across demographics within departments?
  * *Finding:* Female attrition in HR reaches **30.0%**, more than double the male rate of **13.95%**.
* **Commute & Travel Friction:** Do external travel factors influence exit rates?
  * *Finding:* Frequent travelers leave at a **24.91%** rate, and attrition spikes significantly as commute distances enter "Very Long" ranges (**23.74%**).
* **High-Risk Cohort:** Which demographic combination represents the highest risk?
  * *Finding:* Entry-level (Job Level 1) employees who are **Single** and **under 25 years old**.

**Theme 3: Financial & Compensation Drivers**
* **Income Distribution:** How does base compensation differ between retained and attrited staff?
  * *Finding:* Attrition is heavily concentrated in lower monthly income bands ($1K–$4K).
* **Salary Hikes:** Do raises guarantee retention?
  * *Finding:* Low hikes (10%) correlate with high turnover (19.52%), but high hikes (22%) also exhibit high attrition (21.43%), suggesting large raises are often reactive retention attempts.
* **Stock Options:** Do equity incentives reduce turnover?
  * *Finding:* Employees with no stock options (Level 0) have the highest attrition (24.41%), whereas Level 1 and 2 drop below 10%.

**Theme 4 & 5: Career Path & Journey Timeline**
* **Tenure Vulnerability:** When in their lifecycle are employees most likely to leave?
  * *Finding:* First-year employees show the highest rate of turnover (up to 36%), which steadily declines after Year 2.
* **Promotion Stagnation:** How does career advancement lag affect retention?
  * *Finding:* Turnover peaks between **4 and 7 years** following an employee's last promotion.
* **Prior Mobility:** Does past job-hopping predict future attrition?
  * *Finding:* Employees who have worked at **5 or more** previous companies show significantly higher attrition rates.

---

## 🛠 Data Pipeline & Cleaning Operations

* **Dataset:** IBM HR Analytics Employee Attrition & Performance dataset (1,470 records, 35 fields).
* **Data Transformations:**
  * **Quantification:** Created `[Attrition Numeric]` (`IF [Attrition] = 'Yes' THEN 1 ELSE 0 END`).
  * **Binnings:** Applied binning across continuous variables including Age, Tenure, Commute Distance, and Monthly Income.
  * **Composite Metrics:** Engineered `[Overall Satisfaction]` by aggregating Job, Environment, and Relationship satisfaction metrics.
  * **Level of Detail (LOD) Calculations:** Implemented LOD expressions to generate accurate weighted averages and distinct counts (`COUNTD([Employee Number])`).

---

## 🎨 Design Principles Applied

* **Data-Ink Ratio & Truthful Encoding (Tufte):** Removed misleading dynamic benchmarks, corrected ID summation aggregation errors, and reduced label clutter on long-tenure charts to focus on critical data points.
* **Preattentive Attributes (Knaflic):** Employed monochromatic and diverging color palettes (e.g., Orange for Attrited, Blue for Retained) to direct focus to critical risk thresholds.
* **Clarity & Structural Grouping (Gestalt / Munzner / Few):** Grouped semantic categories (Demographics, Financials, Tenure) into dedicated dashboard zones to optimize cognitive load and analytical flow.

---

## 📄 License & Attribution

* **Author:** Sibangi Subhadarsani
* **Dataset Credit:** Rishikesh Konapure (Kaggle)
