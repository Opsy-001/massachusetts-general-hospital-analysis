# 🏥 Massachusetts General Hospital — Patient Analytics Dashboard


> A comprehensive Power BI dashboard analyzing patient records from Massachusetts General Hospital covering **2011–2022**, exploring treatment costs, patient demographics, length of stay, insurance coverage, and inpatient readmission across 28,000+ encounters.

---

## Table of Contents
- [Introduction](#introduction)
- [Business Objectives](#business-objectives)
- [Key Contents of the Dataset](#key-contents-of-the-dataset)
- [Tools Used](#tools-used)
- [Methodology](#methodology)
- [Data Visualization](#data-visualization)
- [Key Insights](#key-insights)
- [Recommendations](#recommendations)
- [Expected Business Impact](#expected-business-impact)
- [Conclusion](#conclusion)
- [About the Author](#about-the-author)

---

## Introduction

This project presents an end-to-end data analytics solution for Massachusetts General Hospital (MGH), one of the leading healthcare institutions in the United States. Using a dataset covering patient records from 2011 to 2022, this dashboard was built to help hospital administrators, clinical teams, and finance departments make data-driven decisions around patient care, cost management, and resource planning.

The dashboard was developed using **Power BI Desktop** and covers five key analytical areas: cost and insurance, patient demographics, length of stay behavior, and inpatient readmission analysis.

---

## Business Objectives

The following business questions guided the analysis:

- What factors influence patient length of stay in the hospital?
- What is the rate of patient readmission within 30 days, and what patterns exist?
- How does insurance coverage affect the cost of patient care?
- Which procedures or treatments contribute most to hospital costs?
- Are healthcare costs increasing over time?
- Are certain patient demographics (age, gender, race) associated with longer stays or higher costs?

---

## Key Contents of the Dataset

| Field | Description |
|---|---|
| Patient ID | Unique identifier for each patient |
| Admission Date | Date and time patient was admitted |
| Discharge Date | Date and time patient was discharged |
| Encounter Class | Type of visit (Ambulatory, Inpatient, Emergency, etc.) |
| Medical Condition | Primary diagnosis or condition |
| Medical Procedure | Treatment or procedure performed |
| Gender | Patient gender |
| Age Group | Patient age bracket (26+) |
| Race | Patient race/ethnicity |
| Total Claim Cost | Total cost billed for the encounter |
| Payer Coverage | Amount covered by insurance |
| Insurance Provider | Name of the insurance payer |

> **Dataset period:** 2011–2022 | **Total encounters:** 28,000+ | **Total patients:** 974 | **Total inpatients:** 1,135

---

## Tools Used

| Tool | Purpose |
|---|---|
| **Power BI Desktop** | Dashboard development and data visualization |
| **Power Query** | Data cleaning, transformation, and column creation |
| **DAX** | Custom measures and calculated columns |
| **Microsoft Excel** | Data exploration, validation, and inpatient readmission column creation |
| **GitHub** | Portfolio documentation and project hosting |

---

## Methodology

1. **Data Collection** — Obtained raw hospital patient records dataset covering 2011–2022
2. **Data Cleaning** — Handled missing values, standardized date formats (converted ISO 8601 format), and removed duplicates in Power Query
3. **Feature Engineering** — Created a calculated **Length of Stay** column by subtracting Admission Date from Discharge Date using:
   ```
   Duration.TotalMinutes(DateTime.From([Discharge Date]) - DateTime.From([Admission Date]))
   ```
4. **LOS Grouping** — Created length of stay buckets (0–1 hr, 2–8 hrs, 8–12 hrs, 12+ hrs) using a custom DAX column
5. **Readmission Analysis** — Created an **Inpatient Readmission** column in Excel to identify patients with more than one inpatient encounter within 30 days, then created a **Readmission Flag** calculated column in Power BI to classify each encounter accordingly
6. **Data Modeling** — Built relationships between tables and created DAX measures for all KPIs including readmission rate, total readmissions, and readmission rate by gender and age group
7. **Visualization** — Designed 4 interactive dashboard pages with filters, drill-throughs, and insight annotations
8. **Validation** — Cross-checked Power BI results against Excel calculations to ensure accuracy

---

## Data Visualization

The dashboard consists of **4 interactive pages:**

### 1. Cost & Insurance
![Cost and Insurance Dashboard](Screenshot_cost_insurance.png)

- Total Treatment Cost: **$101.51M** | Average Cost: **$3.64K** | Total Encounters: **28K**
- Average treatment cost by medical procedure — top 5 procedures
- Average treatment cost by year (2011–2022)
- Total cost by insurance provider
- Total treatment cost vs insurance coverage by payer

### 2. Patient Demographics
![Patient Demographics Dashboard](Screenshot_demographics.png)

- Total Patients: **974** | Total Male: **494** | Total Female: **480**
- Average treatment cost by age group (26+)
- Average treatment cost by gender
- Ethnicity distribution (Hispanic vs Non-Hispanic)
- Patient distribution by race

### 3. Length of Stay Behavior
![Length of Stay Dashboard](Screenshot_los.png)

- Average Length of Stay: **7 hours** | Total Inpatient: **1,135** | Total Encounters: **28K**
- Distribution of length of stay across time buckets
- Relationship between length of stay and treatment cost
- Top 5 medical conditions driving hospital visits
- Average length of stay by encounter class

### 4. Readmission
![Readmission Dashboard](Screenshot_readmission.png)

- Readmission Rate: **33.04%** | Total Readmissions: **375** | Total Inpatients: **1,135**
- Readmission rate by year (2011–2022)
- Readmission rate by gender
- Top 5 conditions driving readmission
- Readmission rate by age group

---

## Key Insights

### 💰 Cost & Financial Insights

* 📈 Average treatment costs peaked at **$4.3K in 2012**, with no consistent upward trend over time
* 💊 **Myocardial infarction ($66K)** is the costliest procedure, indicating heart-related conditions drive the highest expenses
* 🚨 **Uninsured patients generate $49M in claims with zero coverage**, representing the largest financial risk
* 💸 Treatment costs increase with length of stay, peaking at **$8.2K for stays over 12 hours**

---

### 🏥 Patient Behavior & Hospital Utilization

* 💊 **Ambulatory encounters dominate (44.95%)**, confirming most visits are non-critical
* ⏱ **Most patients (24K) stay under 1 hour**, reflecting high outpatient volume
* 🔀 Patient stays cluster at **under 1 hour or over 2 hours**, indicating a split between quick visits and extended care
* 🛏 **Inpatient stays average 37 hours**, significantly longer than other encounter types

---

### 👥 Demographics Insights

* 👥 Patients aged **26–40 incur the highest average treatment cost ($6.9K)**
* ⚧ Male patients have higher average costs (**$4.1K vs $3.3K**), possibly due to higher-acuity cases
* 🏥 **83.4% of patients are Non-Hispanic**, showing uneven demographic representation
* 🧑🏻 **White patients account for 19.5K visits**, the highest among all racial groups

---

### 🫀 Medical Conditions Insights

* 🫀 **Chronic congestive heart failure (1,738 visits)** is the most common condition driving hospital visits
* 🏥 A small number of conditions contribute disproportionately to overall hospital utilization

---

### 🔁 Readmission Insights

* 🔁 **Readmission rate is 33.04%**, significantly higher than common benchmarks (~15%), indicating potential care quality concerns
* 👨 Male patients have a higher readmission rate (**58.82%**) compared to females (**17.61%**)
* 👴 Patients aged **61–80 have the highest readmission rate (37.57%)**, showing increased risk among older patients
* 📉 Readmission rates declined from **60% (2011) to 12% (2020)** before rising again to **27% (2022)**
* 🏨 **"Encounter for problem"** is the leading cause of readmissions (303 cases)

---



| #  | Insight                                                    | Recommendation                                                                                                                                                          | Stakeholder                             |
| -- | ---------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------- |
| 1  | No consistent cost upward trend                            | Establish continuous cost monitoring dashboards and investigate cost spikes (e.g., 2012) to identify underlying drivers such as procedure mix or patient volume changes | Finance Department                      |
| 2  | Ambulatory encounters dominate (44.95%)                    | Expand and optimize outpatient and ambulatory care services to improve efficiency, reduce congestion, and lower operational costs                                       | Operations & Resource Planning Teams    |
| 3  | Myocardial infarction is the highest-cost procedure ($66K) | Implement targeted cardiac care programs, including preventive screening and early intervention strategies, to reduce high-cost emergency cases                         | Clinical & Preventive Care Teams        |
| 4  | Uninsured patients account for $49M in uncovered costs     | Introduce structured financial assistance programs and strengthen insurance enrollment initiatives to reduce uncompensated care                                         | Finance & Patient Services              |
| 5  | Patients aged 26–40 incur the highest costs                | Conduct deeper analysis to identify cost drivers (e.g., lifestyle-related conditions or emergency visits) and design targeted preventive health programs                | Clinical & Analytics Teams              |
| 6  | Male patients have higher treatment costs                  | Analyze clinical and behavioral factors contributing to higher male patient costs and develop targeted awareness and early intervention programs                        | Clinical & Public Health Teams          |
| 7  | Inpatient stays average 37 hours                           | Review inpatient workflows and discharge processes to identify inefficiencies and reduce unnecessary extended stays                                                     | Hospital Operations Team                |
| 8  | Chronic heart failure is the most frequent condition       | Prioritize chronic disease management programs (e.g., monitoring, follow-ups) to reduce repeat visits and long-term treatment costs                                     | Clinical Management Team                |
| 9  | Readmission rate is 33.04% (above expected benchmarks)     | Implement structured post-discharge follow-up programs, including patient education, remote monitoring, and scheduled check-ins to reduce preventable readmissions      | Clinical Team & Hospital Administration |
| 10 | Male patients have the highest readmission rate (58.82%)   | Develop targeted discharge planning and follow-up care strategies specifically for high-risk male patients                                                              | Clinical & Patient Support Teams        |
| 11 | Patients aged 61–80 have the highest readmission risk      | Strengthen geriatric care programs, including medication reviews, home care support, and regular follow-ups to reduce readmissions                                      | Geriatric Care Team                     |
| 12 | Readmissions driven by "Encounter for problem" cases       | Improve diagnosis accuracy and treatment resolution during initial visits to minimize unresolved conditions leading to repeat admissions                                | Clinical Quality & Assurance Team       |


---

## Expected Business Impact

- **Cost Reduction** — Targeted cardiac and chronic disease interventions could significantly reduce the hospital's highest-cost procedure volumes
- **Revenue Protection** — Addressing the $49M uninsured coverage gap through financial assistance and enrollment programs reduces financial risk
- **Operational Efficiency** — Better resource allocation for ambulatory services (44.95% of volume) improves patient throughput and reduces wait times
- **Reduced Readmissions** — Implementing post-discharge follow-up programs could bring the 33.04% readmission rate closer to the 15% national benchmark, improving both patient outcomes and hospital resource utilization
- **Improved Patient Outcomes** — Early intervention for high-risk demographics (male patients, 61–80 age group) reduces late-stage, high-cost presentations and preventable readmissions
- **Data Quality** — Standardizing data collection for medical conditions will enable deeper clinical insights in future analyses

---

## Conclusion

This dashboard provides Massachusetts General Hospital stakeholders with a clear, data-driven view of patient activity, cost drivers, demographic patterns, and readmission trends across 11 years of records. The analysis reveals that while most encounters are non-critical and short in duration, a small number of high-acuity procedures, uninsured patients, and preventable readmissions account for a disproportionate share of hospital costs and resources.

The inpatient readmission rate of **33.04% — more than double the national benchmark of 15%** — is the most urgent finding and requires immediate attention through structured discharge planning and post-care follow-up programs.

The recommendations focus on five key priorities: **cardiac care cost reduction, uninsured patient financial risk management, resource planning for high-volume encounters, demographic-targeted outreach, and readmission reduction** — all aimed at improving operational efficiency and patient outcomes.

---

## About the Author

**Abigail Abiodun**

🔗 **LinkedIn:** www.linkedin.com/in/abigail-abiodun-0205903a7

---

*Last Updated: May 2026 | Dataset: Massachusetts General Hospital Patient Records 2011–2022*

