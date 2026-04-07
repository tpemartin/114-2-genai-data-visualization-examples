# **Dataset Documentation: \[Full Study Title\]**

**Persistent Identifier (DOI/HDL):** \[e.g., https://doi.org/10.xxxx/xxxx\]

**Version:** \[e.g., 1.0.0\]

**Date of Documentation:** \[YYYY-MM-DD\]

## **1\. Administrative Metadata**

### **1.1 Principal Investigators (PI)**

* **Name:** \[Lead Researcher\]  
* **Affiliation:** \[University/Department\]  
* **ORCID:** \[0000-0000-0000-0000\]  
* **Contact Email:** \[email@academic.edu\]

### **1.2 Funding & Support**

* **Funding Agency:** \[e.g., National Science Foundation (NSF)\]  
* **Grant Number:** \[e.g., SES-XXXXXX\]  
* **Acknowlegments:** \[Any additional collaborators or support staff\]

### **1.3 Ethical Oversight**

* **IRB Approval Number:** \[e.g., IRB-FY24-123\]  
* **Reviewing Institution:** \[University Name\]  
* **Consent Type:** \[e.g., Written Informed Consent / Online Click-through\]

## **2\. Study Overview & Methodology**

### **2.1 Abstract/Summary**

\[A brief description of the study's purpose, the central research questions, and the scientific contribution of the dataset.\]

### **2.2 Geographic Coverage**

* **Country/Region:** \[e.g., United States, Midwest Census Region\]  
* **Smallest Unit of Geography:** \[e.g., Census Tract / County\]

### **2.3 Temporal Coverage**

* **Data Collection Start:** \[YYYY-MM-DD\]  
* **Data Collection End:** \[YYYY-MM-DD\]  
* **Time Method:** \[e.g., Cross-sectional / Longitudinal Panel / Trend\]

### **2.4 Universe & Unit of Analysis**

* **Target Population:** \[e.g., Adults 18+ residing in urban centers\]  
* **Unit of Analysis:** \[e.g., Individuals / Households / Organizations\]

## **3\. Sampling & Data Collection**

### **3.1 Sampling Procedure**

\[Detail the sampling frame. Was it a simple random sample, stratified, or a non-probability convenience sample?\]

### **3.2 Mode of Collection**

* **Primary Mode:** \[e.g., Computer-Assisted Web Interview (CAWI) / Face-to-Face\]  
* **Instrument Used:** \[e.g., Qualtrics / SurveyMonkey / Paper Questionnaire\]

### **3.3 Response Rates**

* **Total Sample Size (N):** \[Number\]  
* **Completion Rate:** \[%\]  
* **Weighting:** \[Describe any probability weights, post-stratification, or non-response adjustments applied.\]

## **4\. Data Dictionary (Codebook)**

\[Must contain all variable names of the dataset in the table\]

| Variable Name | Label | Measurement Level | Values/Codes | Missing Values | R Data Type |
| :---- | :---- | :---- | :---- | :---- | :---- |
| case\_id | Unique Record ID | Nominal | Alphanumeric string | N/A | character |
| survey\_date | Date of Interview | Interval | YYYY-MM-DD | 9999-01-01 | Date |
| age\_years | Participant Age | Ratio | 18 to 99 | NA | numeric (double) |
| sibling\_count | Number of Siblings | Ratio | 0, 1, 2, ... | \-1 | integer |
| treatment\_grp | Study Group | Nominal (Factor) | "Control", "Placebo", "Active" | NA | factor |
| income\_rank | Income Bracket | Ordinal (Factor) | 1: Low, 2: Med, 3: High | \-9: Refused | ordered factor |
| is\_employed | Employment Status | Nominal (Binary) | TRUE (Yes), FALSE (No) | NA | logical |
| gpa\_score | Grade Point Average | Ratio | 0.00 to 4.00 | NaN | numeric (double) |
| timestamp | Record Entry Time | Continuous | YYYY-MM-DD HH:MM:SS | NA | POSIXct |

### ---

**Key R Data Type Distinctions**

* **numeric vs integer**: While both represent numbers, numeric (double) allows for decimals, whereas integer is strictly for whole numbers (often denoted in R code as 1L, 2L, etc.).  
* **factor**: This is R’s way of handling categorical data. It stores labels as integers under the hood to save memory and ensure statistical models treat them as discrete categories.  
* **ordered factor**: A special case of factor where the levels have a specific rank (e.g., "Small" \< "Medium" \< "Large").  
* **logical**: Specifically for Boolean values (TRUE/FALSE). In R, these can also be treated as 1 and 0 for mathematical operations.

## **POSIXct**: The standard class for date-time data, allowing for precise time-zone calculations and temporal analysis.

## **5\. Processing & Cleaning**

### **5.1 Quality Control**

* **Logic Checks:** \[Describe consistency checks between variables.\]  
* **Cleaning Steps:** \[Detail how "straight-lining" or "speeders" were handled.\]

### **5.2 Anonymization (De-identification)**

* **PII Removal:** \[Confirmed removal of names, emails, and exact birthdates.\]  
* **Top-coding:** \[Were extreme outliers capped to prevent re-identification? e.g., Incomes \> $250k capped.\]

## **6\. Files & Distribution**

### **6.1 Replication Package Structure**

* data/raw/: Original unaltered data (Archival).  
* data/processed/: Final analytical dataset.  
* scripts/: R/Stata/Python code for cleaning and analysis.  
* instruments/: Copy of the original survey/interview guide.

### **6.2 Access & License**

* **License:** \[e.g., CC-BY 4.0 / CC0 1.0 / Restricted Access\]  
* **Recommended Citation:** \[PI Name\] (\[Year\]). \[Study Title\]. \[Repository Name\]. \[DOI\]

## **7\. Known Limitations**

\[Document any known biases, measurement errors, or data collection interruptions that may affect the validity of secondary analysis.\]