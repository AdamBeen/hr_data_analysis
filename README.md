# hr_data_analysis
End-to-end HR analytics project exploring employee attrition using Excel and Power BI. Data cleaning performed in Excel, followed by KPI modeling, DAX measures, and interactive visualization in Power BI to uncover workforce trends and attrition patterns.

# 🧠 HR Analytics Dashboard

## 📌 Project Overview
This project analyzes employee attrition data to uncover key patterns and insights related to workforce demographics, job satisfaction, and education fields.  
The main goal is to help HR managers **understand turnover causes** and **improve retention strategies** using a data-driven approach.

The dataset was **cleaned in Excel** and modeled in **Power BI** for interactive visual analysis.

---

## 🧾 Dataset
The dataset (`HR Data.xlsx`) contains detailed employee information, including:

| Column | Description |
|---------|-------------|
| Employee ID | Unique identifier per employee |
| Department | HR, R&D, or Sales |
| Job Role | Employee’s specific role |
| Gender | Male / Female |
| Age | Employee age |
| Education Field | Academic discipline |
| Job Satisfaction | Survey rating (1–4) |
| Attrition | “Yes” if the employee left, “No” otherwise |
| Monthly Income, Years at Company, etc. | Additional HR metrics |

---

## 🧹 Data Cleaning (Excel)
All preprocessing was done in **Microsoft Excel** before importing into Power BI.

Steps performed:
1. Created a backup copy of the raw data.  
2. Removed duplicates (`Data → Remove Duplicates`).  
3. Fixed formatting issues (text, numbers, dates).  
4. Applied **spell check** and **case correction** (`PROPER()` function).  
5. Used `TRIM()` to remove unwanted spaces.  
6. Replaced missing or null values with “Unknown” or `0` where appropriate.  
7. Applied **Find & Replace** to standardize categorical values (e.g. “M” → “Male”).  

Cleaned dataset saved as `HR_Cleaned.xlsx`.

---

## ⚙️ Power BI Modeling
Data imported into Power BI Desktop and processed as follows:

- Converted columns to correct data types.  
- Created calculated columns (Age Group).  
- Built DAX measures for KPIs (Employee Count, Attrition Rate, Average Age).  
- Designed multiple pages for various HR perspectives.

### **Key DAX Measures**
```DAX
Employee Count := COUNTROWS(HR_Data)

Attrition Count :=
CALCULATE(COUNTROWS(HR_Data), HR_Data[Attrition] = "Yes")

Attrition Rate :=
DIVIDE([Attrition Count], [Employee Count])

Active Employees :=
CALCULATE(COUNTROWS(HR_Data), HR_Data[Attrition] = "No")

Average Age := AVERAGE(HR_Data[Age])

