# Healthcare-Analysis-and-Insights
## 1. Problem Statement
- The healthcare industry generates vast amounts of data daily, providing valuable insights for healthcare providers and policymakers to improve patient care, allocate resources effectively, and manage healthcare costs. This project aims to analyze a comprehensive healthcare dataset comprising medical examinations, hospitalization details, and customer profiles to extract insights into patient health profiles, medical histories, and healthcare costs. By exploring relationships between various health metrics, identifying trends, and visualizing key patterns, we aim to deliver actionable insights to healthcare stakeholders for informed decision-making through rigorous data cleaning, transformation, exploration, and analysis.
## 2. Data Set Description
## 📁 Dataset
- Customers: 2335 | Hospitalisation: 2343

## 📄 Sheets
- Customer Names, Medical Examinations, Hospitalisation Details, HEALTH CARE

## 🧹 Cleaning
- Removed `?`, kept 6 `Unknown` IDs
- Split Name to Title / First / Last Name
- Combined DOB using TEXTJOIN

## 🔄 Transformation
- Weight Status from BMI, Diabetes Status from HbA1C
- Age using YEARFRAC, Final table using VLOOKUP

## 📊 Key Counts
- Mr 1165, Ms 1028, Mrs 142
- Obesity 1221, Over Weight 501, Normal 437, Under 176
- Diabetes 784, Pre Diabetes 456, Normal 1095
## 3. Data Preprocessing
### 3.1 Data Cleaning
- Removed `?` values from Hospitalisation Details.
- Kept 6 `Unknown` Customer IDs as it is.
- Split **Name** into **Title, First Name, Last Name**.
- Combined **Year, Month, Date** into **Date Of Birth** using `TEXTJOIN`.
- Removed duplicate Customer IDs.
- Checked and removed blank cells and `#N/A` errors.
- Standardized Title values to Mr / Ms / Mrs.

### 3.2 Data Transformation
- **Weight Status** created from BMI using `IF`:
    - BMI < 18.5 = Under Weight
    - BMI 18.5 - 24.9 = Normal Weight
    - BMI 25 - 29.9 = Over Weight
    - BMI >= 30 = Obesity
- **Diabetes Status** created from HbA1C using `IF`:
    - HbA1C < 5.7 = Normal
    - HbA1C 5.7 - 6.4 = Pre Diabetes
    - HbA1C >= 6.5 = Diabetes
- **Age** calculated using `YEARFRAC` as on 08-Jun-2023.
- **Charges** formatted as `$` currency.
- **HEALTH CARE** final master table created using `VLOOKUP`.

### 3.3 Final Output
- Cleaned data with 2335 customers in final HEALTH CARE table.
- No blanks, no `?` values, no errors.
- Ready for Exploratory Data Analysis.
## 4. Exploratory Data Analysis
### Demographics
- Total Customers: 2335
- Title: Mr 1165, Ms 1028, Mrs 142
- BMI Range: 15.01 - 55.05

### Health Analysis
- Weight: Obesity 1221, Over Weight 501, Normal 437, Under Weight 176
- Diabetes: Normal 1095, Diabetes 784, Pre Diabetes 456
- Majority customers are in Obesity category.

### Charges Analysis
- Charges Range: $563.84 - $63,770.43
- Charges vary by Hospital Tier, City Tier and Age.

### Key Finding
- Obesity and Diabetes are high in this dataset.
- Higher BMI customers show higher health risk.
