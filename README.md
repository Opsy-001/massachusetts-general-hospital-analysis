# 📊 Massachusetts General Hospital Analysis

## 📌 Project Overview
This project analyzes hospital patient data to uncover insights on patient demographics, treatment costs, insurance coverage, and hospital visit patterns.

The goal is to transform raw healthcare data into meaningful insights that support better decision-making.

---

## Project Aim
To analyze hospital data in order to identify trends in patient behavior, treatment costs, and healthcare utilization, and provide actionable insights.

---

## 📂 Dataset Information
- **Source:** STC Synthetic Healthcare Dataset  
- **Tables Used:**
  - Patients  
  - Encounters  
  - Payers  
  - Procedures  

### 🔑 Key Columns
- Patient ID  
- Admission & Discharge Date  
- Length of Stay  
- Total Claim Cost  
- Payer Coverage  
- Gender, Age, Ethnicity, Race  
- Encounter Class  
- Procedure Description  

## 🛠 Tools Used
- Microsoft Excel  
- Power BI  

## 📥 Data Import Process
- Dataset was first cleaned in Excel  
- Cleaned data was imported into Power BI  
- Relationships were created between tables  

## 🧹 Data Cleaning & Transformation
- Fixed incorrect text encoding issues in names  
- Merged multiple name columns into **Full Name**  
- Standardized column formats  
- Converted date/time fields  
- Created **Length of Stay (minutes)**  
- Handled missing values  
- Converted cost columns to fixed decimal format  

## 🔗 Data Modeling
- Created relationships between tables  
- Created calculated columns:
  - Age  
  - Age Groups (35–50, 51–65, 66–80, 81+)  
  - Length of Stay Groups  

### 📐 DAX Measures
- Total Cost  
- Average Cost  
- Total Encounters  

## 📊 Dashboard Structure

### Page 1: Overview
- KPI Cards: Total Patients, Total Encounters, Total Cost, Avg Cost, Avg Length of Stay  
- Line Chart: Hospital Visits Over Time  
- Bar Chart: Encounter Class Distribution  

### Page 2: Cost & Insurance
- Bar Chart: Cost by Procedure  
- Bar Chart: Cost by Insurance Provider (Top 5)  
- Column Chart: Insurance Coverage vs Total Cost  

### Page 3: Patient Demographics
- Column Chart: Average Cost by Age Group  
- Bar Chart: Average Cost by Gender  
- Donut Chart: Ethnicity Distribution  
- Bar Chart: Patient Distribution by Race  

### Page 4: Length of Stay & Behavior
- Column Chart: Length of Stay Distribution  
- Column Chart: Length of Stay vs Cost  
- Bar Chart: Top Medical Conditions  

## 📈 Key Insights
- Hospital visits fluctuate over time  
- Most visits are outpatient and non-critical  
- Uninsured patients generate the highest costs  
- Insurance coverage often falls below total treatment cost  
- Heart-related procedures are the most expensive  
- Ages 35–50 incur the highest average cost  
- Male patients have slightly higher treatment costs  
- Most hospital stays are short  
- Costs increase with longer stays  
- A few medical conditions drive most visits  
- Patient distribution is uneven across ethnic and racial groups  

## 💡 Recommendations
- Improve financial strategies for uninsured patients  
- Focus on high-cost procedures for cost control  
- Promote preventive care to reduce frequent visits  
- Allocate resources to high-demand conditions  
- Improve data quality for better analysis  

## ✅ Conclusion
This project demonstrates how healthcare data can be used to uncover patterns in cost, patient behavior, and hospital operations.

The insights can support better decision-making in healthcare management.

---

## 📬 Contact
- **LinkedIn:** www.linkedin.com/in/abigail-abiodun-0205903a7
- **Email:** abigailopeyemi001@gmail.com  

⭐ If you found this project useful, feel free to star the repository!
