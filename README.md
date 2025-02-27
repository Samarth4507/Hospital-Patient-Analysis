# Hospital Patient Analysis


## Overview
This document outlines the end-to-end process of developing a Power BI dashboard using publicly available healthcare data on patient waiting lists.

## Steps for Dashboard Development

### 1. Requirement Gathering
- **Identify Stakeholders:** Determine key stakeholders and end-users.
- **Understand Business Objectives:** Conduct meetings to define goals and expected outcomes.
- **High-Level Data Study:** Understand data sources, column descriptions, types, volume, frequency, and quality.
- **Define Scope:** Identify key metrics, KPIs, and timelines.
- **Problem Statement:**
  - Track current patient waiting list status.
  - Analyze historical trends for inpatient & outpatient categories.
  - Perform specialty-level and age-profile analysis.
  - Data Scope: 2018 – 2021.
  - Metrics: Average & Median Waiting List, Current Total Wait List.
  - Views: Summary and Detailed Analysis Pages.

### 2. Data Collection
- Power BI supports multiple data connectors such as Excel, CSV, SQL Server, Power BI services, cloud platforms, ERP systems, SharePoint, and web sources.
- Use a folder connector to import inpatient and outpatient data.
- Steps:
  1. Open Power BI Desktop, click **Get Data**, and select **Folder**.
  2. Browse the folder and select the data source.
  3. Click **Combine & Load** to merge the files.

### 3. Data Transformation
- **Power Query Editor:**
  - Rename Columns for consistency.
  - Rearrange Columns to match structures.
  - Append Tables (Inpatient & Outpatient) into a single dataset.
  - Replace & Trim values for data consistency.
- **Data Modeling:**
  - Hide unnecessary tables.
  - Create relationships (e.g., Specialty Name with a Mapping Table).
  - Implement data categorization (e.g., bucketing specialties).

### 4. Visualization Blueprint
- Create a wireframe before dashboard development.
- Get approval from stakeholders before proceeding.

### 5. Dashboard Layout & Design
- **Enable:** Gridlines & Snap to Grid for alignment.
- **Create DAX Measures:**
  ```DAX
  Latest Month Wait List = CALCULATE(SUM(All_Data[Total]),All_Data[Archive_Date] = MAX(All_Data[Archive_Date])) + 0
  PY Latest Month Wait List = CALCULATE(SUM(All_Data[Total]),All_Data[Archive_Date]= EDATE(MAX(All_Data[Archive_Date]),-12)) + 0
  Median Wait List = MEDIAN(All_Data[Total])
  Average Wait List = AVERAGE(All_Data[Total])
  ```
- **Insert Visuals:** Card visuals for KPIs, Doughnut Charts, Column Charts, Multi-Row Cards.
- **Create Interactive Buttons:** Use slicers for toggling between average and median values.

### 6. Adding Interactivity
- **Navigation Buttons** for seamless movement between pages.
- **Tooltips** to enhance data insights.
- **Dynamic Titles & Labels** using DAX.

### 7. Testing & Deployment
- Validate data accuracy and KPI calculations.
- Ensure all interactions work correctly.
- Deploy the dashboard on Power BI Service.
- Schedule data refresh.

### 8. Sharing & Maintenance
- Share dashboard via Power BI service.
- Set up scheduled refresh cycles.
- Monitor performance and optimize for efficiency.

## Resources
You can download the resources for this project from: [Download Link]

---
This README serves as a guide for developing a Power BI dashboard from scratch, covering all key aspects from data gathering to deployment.

