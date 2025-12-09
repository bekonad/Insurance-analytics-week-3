Perfect! I can update the Markdown so that **all figure placeholders point to `reports/figures/`** and include **short captions/interpretations** for each. This way, once you drop the figures there, your README will be fully ready. Here's the updated version:

````markdown
# End-to-End Insurance Risk Analytics & Predictive Modeling

**Project:** 10 Academy – Artificial Intelligence Mastery, Week 3  
**Prepared by:** Bereket Feleke  
**Date:** December 2025  

---

## **Business Objective**
AlphaCare Insurance Solutions (ACIS) aims to enhance its car insurance marketing strategy by identifying low-risk segments for which premiums can be reduced. The objective is to attract new clients while optimizing profitability. This project focuses on analyzing historical insurance data to understand risk patterns, loss ratios, and key drivers of claims, and to implement reproducible data pipelines.

**Key Goals:**
- Identify high- and low-risk segments based on historical claims.
- Understand patterns in premiums, claims, vehicle types, and client demographics.
- Establish reproducible data pipelines using DVC for audit and regulatory compliance.
- Lay the foundation for predictive modeling and A/B hypothesis testing.

---

## **Task 1: Git, GitHub & Exploratory Data Analysis (EDA)**

### **1.1 Git & GitHub Setup**
- Created a structured Git repository for project code and documentation.
- Initialized Git with version control and linked to a remote repository on GitHub.
- Implemented CI/CD using GitHub Actions to automate testing and workflow validation.
- Branching strategy:
  - `task-1` → Initial EDA and statistics.
  - `task-2` → DVC setup and data versioning.
- Commits were descriptive and frequent, ensuring clear traceability of progress.
- **KPIs Achieved:** Proficiency in Git, adherence to versioning best practices, and collaborative workflow setup.

---

### **1.2 Data Understanding & Preparation**
- **Dataset:** Insurance data spanning February 2014 – August 2015.
- **Columns include:**
  - **Policy Information:** PolicyID, UnderwrittenCoverID, TransactionMonth
  - **Client Attributes:** Gender, MaritalStatus, Language, Citizenship, IsVATRegistered
  - **Location Data:** Province, PostalCode, MainCrestaZone, SubCrestaZone
  - **Vehicle Info:** VehicleType, Make, Model, RegistrationYear, Cylinders, CustomValueEstimate
  - **Plan Data:** TotalPremium, TotalClaims, CalculatedPremiumPerTerm, CoverType
- Checked **data types** for numerical, categorical, and date columns.
- Addressed **missing values** and outliers (boxplots and summary statistics) to ensure data quality.

---

### **1.3 Exploratory Data Analysis (EDA)**

#### **Univariate Analysis**
- Visualized distributions of key variables:
  - Numerical: `TotalPremium`, `TotalClaims`, `CustomValueEstimate`, `SumInsured`
  - Categorical: `Province`, `VehicleType`, `Gender`, `CoverType`
- Insights:
  - `TotalClaims` is skewed; a few policies contribute to high claim amounts.
  - Certain vehicle types (e.g., SUVs, sports cars) have higher average claims.
  - Provinces show variability in loss ratios.

**Figures & Interpretations:**  
- **Distribution of TotalPremium**  
  `![](reports/figures/totalpremium_distribution.png)`  
  *Shows the spread of premiums; highlights high-value policies and potential outliers.*

- **Claims by VehicleType**  
  `![](reports/figures/claims_by_vehicle.png)`  
  *Identifies vehicle types with higher claim frequency for targeted risk assessment.*

- **Loss Ratio by Province**  
  `![](reports/figures/lossratio_by_province.png)`  
  *Reveals provinces with higher loss ratios, informing regional premium adjustments.*

---

#### **Bivariate & Multivariate Analysis**
- Relationships analyzed:
  - `TotalClaims` vs `TotalPremium` to evaluate profitability.
  - `LossRatio` across `Province` and `VehicleType`.
  - Correlation matrix of numerical features.
- Temporal trends:
  - Monthly changes in claims and premiums over the 18-month period.
  - Seasonal patterns identified in certain vehicle categories.

**Figures & Interpretations:**  
- **Premium vs Claims by Vehicle Type**  
  `![](reports/figures/premium_vs_claims_vehicle.png)`  
  *Highlights the relationship between premiums and claims across vehicle types, useful for adjusting premiums.*

- **Trend of TotalClaims over Time**  
  `![](reports/figures/totalclaims_trend.png)`  
  *Shows seasonality and temporal spikes in claims.*

- **Correlation Heatmap of Key Features**  
  `![](reports/figures/correlation_heatmap.png)`  
  *Displays relationships between numerical variables to identify predictive patterns.*

**KPIs Achieved:**
- Comprehensive data understanding
- Identification of key risk drivers
- Actionable insights for premium optimization

---

## **Task 2: Data Version Control (DVC)**

### **2.1 Overview**
- Implemented **DVC** to ensure reproducibility, auditable pipelines, and proper dataset versioning.
- DVC links analyses and model outputs to exact dataset versions for audit and compliance.

### **2.2 Implementation Steps**
1. Installed DVC:  
   ```bash
   pip install dvc
````

2. Initialized DVC in project directory:

   ```bash
   dvc init
   ```
3. Configured **local remote storage**:

   ```bash
   mkdir /path/to/local/storage
   dvc remote add -d localstorage /path/to/local/storage
   ```
4. Added datasets to DVC:

   ```bash
   dvc add data/insurance.csv
   ```
5. Committed `.dvc` files to Git.
6. Pushed data to local remote:

   ```bash
   dvc push
   ```

### **2.3 Branching & Version Management**

* Merged `task-1` into `main` using Pull Requests.
* Created `task-2` branch for DVC work.
* Commits are descriptive for auditability and reproducibility.
* Multiple dataset versions are tracked and recoverable.

### **2.4 Outcome**

* Reproducible, auditable data pipeline ready for predictive modeling and A/B testing.
* Ensures compliance with data governance and regulatory standards.

---

## **Summary**

* **Task 1:** Completed in-depth EDA with key insights on claims, premiums, vehicle types, and geographic risk patterns.
* **Task 2:** Established a reproducible DVC workflow for version-controlled datasets.
* Prepared the foundation for **Task 3 (A/B Testing)** and **Task 4 (Predictive Modeling)**.

**Next Steps:**

* Conduct statistical hypothesis testing to identify significant risk differences.
* Build predictive models for claim severity and premium optimization.

---

**References & Tools:**

* **Git & GitHub**, **GitHub Actions (CI/CD)**
* **Python Libraries:** pandas, numpy, matplotlib, seaborn, scipy
* **DVC Documentation:** [https://dvc.org/doc](https://dvc.org/doc)
* Insurance analytics references for data interpretation and modeling.