📂 IBM HR Analytics Dataset Guide

Due to GitHub's repository best practices, this folder documents the original raw dataset structure, setup instructions, and the clean data dictionary used to drive our Python pipelines and Power BI dashboard.

📥 Source & Dataset Details

Database Source: Kaggle — IBM HR Analytics Employee Attrition & Performance

Dataset Size: ~230 KB (Uncompressed CSV)

Volume: 1,470 rows × 35 columns (Raw)

Format: Comma Separated Values (.csv)

⚙️ How to Set Up the Data

To run the Python Jupyter Notebook and Power BI dashboard successfully, follow these quick setup instructions based on your environment:

Method A: Running on Google Colab (Recommended)

Download the raw WA_Fn-UseC_-HR-Employee-Attrition.csv from the Kaggle link above.

Upload the file to your Google Drive under this exact directory path:

My Drive/HR_Project/WA_Fn-UseC_-HR-Employee-Attrition.csv

Execute the Google Colab notebook. The script will automatically clean the data and export ibm_hr_cleaned_data.csv straight to your Drive!

Method B: Running Locally (Jupyter / VS Code & Power BI Desktop)

Clone this repository to your local machine.

Download the raw CSV from Kaggle.

Place the raw CSV inside your local /data/ folder.

If opening the Power BI .pbix dashboard locally, click Home ➔ Transform Data, select the source step of the query, and point the file path directly to your locally saved ibm_hr_cleaned_data.csv file.

🗺️ Unified Schema Dictionary (Selected Key Features)

Here is a map of the primary attributes we processed and engineered throughout our operational consulting project:

| Attribute Name | Data Type | Description / Range | Handling in our Pipeline |
| Age | Integer | Biological age (18 to 60) | Kept (Used for demographic profiling) |
| Attrition | Categorical | Yes / No flag | Mapped to binary numeric attrition_num (Yes = 1, No = 0) |
| Department | Categorical | Sales, R&D, Human Resources | Kept (Primary grouping variable) |
| MonthlyIncome | Integer | Monthly base salary (₹) | Kept (Primary financial metric) |
| OverTime | Categorical | Yes / No overtime workload flag | Kept (Key operational driver of burnout) |
| WorkLifeBalance | Integer | Rating scale from 1 (Poor) to 4 (Excellent) | Kept (Primary employee satisfaction metric) |
| EmployeeCount | Integer | Constant value of 1 for all rows | Dropped (Zero statistical variance) |
| StandardHours | Integer | Constant value of 80 for all rows | Dropped (Zero statistical variance) |
| Over18 | Categorical | Constant value of 'Y' for all rows | Dropped (Zero statistical variance) |
| EmployeeNumber | Integer | Sequential ID numbers | Dropped (Unique administrative identifier) |
