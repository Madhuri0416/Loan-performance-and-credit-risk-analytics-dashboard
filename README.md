# Loan-performance-and-credit-risk-analytics-dashboard
📊 Loan Performance & Credit Risk Analytics Dashboard (Power BI)

📌 Project Overview
This project delivers an executive-ready Power BI dashboard designed to monitor loan portfolio performance and credit risk exposure. The dashboard enables stakeholders to quickly track key KPIs such as total loan amount, default rate (NPL%), and risk segmentation, helping improve risk monitoring and decision-making.

🎯 Business Problem
Loan portfolios often contain thousands of loan-level records. Without centralized reporting, stakeholders struggle to answer:

1.How healthy is the overall loan portfolio?
2.Which borrower segments contribute most to defaults?
3.How does credit score influence default probability?
4.What financial exposure exists from high-risk lending?
5.Manual reporting leads to delayed decision-making and increased credit risk.

✅ Objectives

This dashboard answers:

1.How many loans has the business issued?
2.What is the total loan amount issued?
3.What is the default rate / non-performing loan (NPL) percentage?
4.What is the average loan amount?
5.How is the portfolio distributed across risk categories?
6.Which risk category has the highest default rate?

📂 Dataset

Source: Kaggle – Loan Default Dataset
Table: Loan_default
Key columns:
loan_id (identifier)
LoanAmount (loan value)
CreditScore (borrower score)
Default (0 = non-default, 1 = default)

🛠 Tools & Skills Used
Tools:
Power BI Desktop
Power Query 
Skills:
KPI dashboard design
DAX measures
Risk segmentation (calculated column)
Data storytelling (insights + recommendations)

🧼 Data Preparation (Power Query)

Minimal transformations were required:
Ensured LoanAmount is numeric
Ensured Default is Whole Number (0/1)
Kept loan_id as Text identifier

🧠 Data Modeling

Single-table model (no joins required).
Created Risk Category using credit score thresholds:
Credit Score Range	Risk Category
≥ 750	Low Risk
650–749	Medium Risk
< 650	High Risk

📈 KPIs & Measures (DAX)

Total Loans Issued

Total Loans Issued = COUNTROWS('Loan_default')


Total Loan Amount

Total Loan Amount = SUM('Loan_default'[LoanAmount])


Average Loan Amount

Average Loan Amount = AVERAGE('Loan_default'[LoanAmount])


Default Rate (%)

Default Rate =
DIVIDE(
    SUM('Loan_default'[Default]),
    COUNTROWS('Loan_default'),
    0
)


NPL (%)

NPL (%) = [Default Rate]

📊 Dashboard Features
KPI Cards:

Total Loans Issued

Total Loan Amount

Average Loan Amount

Default Rate (%) / NPL (%)

Visuals:

Loans by Risk Category

Default Rate by Risk Category

Loan Details Table (Loan ID, Loan Amount, Credit Score, Risk Category, Default)

🔍 Key Insights

High Risk segment has the highest default rate, increasing portfolio risk exposure.

Medium Risk segment contributes heavily to total defaults due to high loan volume.

High loan amounts increase financial exposure even with small default changes.

Low Risk segment remains stable and supports portfolio health.

💡 Business Recommendations

Strengthen controls for High Risk approvals: Income verification, employment stability checks, collateral or pricing adjustments

Increase monitoring for Medium Risk loans: monthly risk review, early warning trigger.

Create policy for high-value loan exposure, additional approval layers, tighter DTI requirements

🏁 Conclusion

This dashboard demonstrates how Power BI can convert loan-level data into centralized credit risk reporting, enabling faster insights into portfolio health, risk segmentation, and default exposure.

