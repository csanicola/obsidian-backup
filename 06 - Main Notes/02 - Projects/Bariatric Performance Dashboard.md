---
project_type:
  - Work Project
start_date: "[[2024.10.17]]"
due_date: 
status:
  - Not Started
priority:
  - Medium
team:
  - Self
tags:
  - "#work"
  - "#project"
  - tableau
  - dashboard
tech_stack: []
code_repo: 
related_projects:
---
# Work Project: Bariatric Performance Dashboard

## Overview
- **Start Date**: 2024.10.17
- **Due Date**: N/A
- **Status**: Not Started
- **Priority**: Medium

## Objective
- **Goal**: Create an interactive dashboard for both the data analyst and the surgeons/bariatric team to be able to see how the program is doing at any time while comparison to previous years.
- **Client / Team**: Bariatric Team 

## Code Involvement
- **Tech Stack**: {{List of programming languages, frameworks, or tools used}}
- **Code Repo**: {{Link to repository or internal Git link}}
- **Scripts/Modules**: {{List of specific scripts or modules written}}

## Steps / Tasks
- [ ] #task find a template to create the dashboard based off of
- [ ] 
- [ ] 

## Requirements
- **Software/Tools**: Tableau
- **Hardware**: N/A
- **Access**: Use Tableau student version with work email otherwise unable to access
- **Documentation**: {{Links to documentation, guidelines, or design documents}}

## Related Projects
- **Past Work**: {{List or link any relevant past projects or codebases}}
- **Dependencies**: {{List any projects or modules that this project depends on}}
- **Future Extensions**: {{Possible follow-up projects or improvements}}

## Challenges / Roadblocks
- {{List known or potential issues, bugs, or dependencies that could affect progress}}

## Resources & References
- **Links**: [Stony Brook SharePoint Site](https://stonybrookmedicine-my.sharepoint.com/:u:/g/personal/caroline_sanicola_stonybrookmedicine_edu/EV1Rs9SKBzlKiuPSwPE8AugBUbBGlc-h8OeuHc6F9DLxTw?e=kNggEm)
- **Team Contacts**: {{List key people you might need to consult for questions}}
- **Notes**: {{Any additional context or notes}}

___
## Step-by-Step Guide to Creating a Tableau Dashboard for a Bariatric Surgery Center

This guide walks you through the process of building a dashboard to track patient data related to bariatric surgery, including the number of patients contacted, seen, underwent surgery, post-surgery occurrences, and filters for contact, consultation, surgery date, and surgeon.

---
### **Step 1: Project Overview**

### **Objective:**

The dashboard will allow the Bariatric Surgery Center to monitor patient activity from initial contact to surgery and post-surgery outcomes. The dashboard tracks:

- **Patients Contacted**: How many patients have been contacted.
- **Patients Seen**: How many patients had a consultation.
- **Patients Who Underwent Surgery**: How many surgeries were performed.
- **Occurrences**: Post-surgery complications or follow-ups.

### **Audience**:

- Surgeons, Clinic Administrators, and Staff.

### **Data Sources**:

- **Patient Data Table**: Contains patient information such as name, contact date, consultation date, surgery date, and surgeon.
- **Surgery Outcome Table**: Contains information on any post-surgery occurrences or complications.

---
### **Step 2: Setup**

### **2.1 Required Software and Tools:**

- **Tableau Desktop**: Make sure you have the correct version installed.
- **Data Source**: Make sure you have access to the patient data and surgery outcome data in a format Tableau can connect to (e.g., Excel, SQL Database, etc.).

### **2.2 Connecting to the Data Source:**

1. Open Tableau Desktop.
2. In the left-hand pane, under "Connect", choose the appropriate data source (e.g., **Microsoft Excel** or **SQL Server**).
3. Navigate to and select your data file or establish a connection to your database.
4. Load the necessary tables: `Patient Data` and `Surgery Outcomes`.

### **2.3 Data Preparation:**

- Join the `Patient Data` table and `Surgery Outcome` table on **Patient ID** if necessary.
- Ensure all fields like contact date, consultation date, surgery date, and surgeon names are clean and formatted properly.

---
### **Step 3: Data Cleaning and Transformation**

### **3.1 Rename Fields:**

- Rename columns to something easily recognizable (e.g., `Surgery Date`, `Consultation Date`, `Contact Date`, `Surgeon`, `Occurrences`).

### **3.2 Calculated Fields:**

Create some calculated fields to summarize patient stages and outcomes:

1. **Number of Patients Contacted**:
    - Formula: `COUNTD([Patient ID])` (Ensure you use distinct patient counts).
2. **Number of Patients Seen (Consultation)**:
    - Formula: `IF NOT ISNULL([Consultation Date]) THEN 1 END`
3. **Number of Surgeries Performed**:
    - Formula: `IF NOT ISNULL([Surgery Date]) THEN 1 END`
4. **Post-Surgery Occurrences**:
    - Formula: `IF NOT ISNULL([Occurrence]) THEN 1 END`

---

### **Step 4: Building the Dashboard**

### **4.1 Create Individual Worksheets:**

1. **Patients Contacted Worksheet**:
    - Drag **Patient ID** to `Rows`.
    - Use the `COUNTD([Patient ID])` measure to count the distinct number of patients contacted.
    - Add this as a numeric KPI visualization (text-based).
2. **Patients Seen (Consultation)**:
    - Use the calculated field `Number of Patients Seen` to show a KPI for patients who attended consultation.
3. **Surgeries Performed Worksheet**:
    - Use the calculated field `Number of Surgeries Performed` to display surgeries performed as a bar or KPI visualization.
4. **Occurrences Post-Surgery Worksheet**:
    - Use the calculated field `Post-Surgery Occurrences` to track complications or outcomes.

### **4.2 Combining Worksheets into a Dashboard**:

1. Click on the **New Dashboard** icon in Tableau.
2. Drag each worksheet (Contacted, Seen, Surgeries, Occurrences) onto the dashboard canvas.
3. Arrange KPIs (patients contacted, seen, surgeries, occurrences) in a grid for easy overview:
    - **Top Row**: KPIs for Contacted, Seen, Surgeries.
    - **Bottom Row**: Occurrences as a detailed bar or table view for tracking.
4. Adjust fonts, colors, and text size to make important metrics stand out. Use consistent color schemes (e.g., green for successful outcomes, red for occurrences).

---

### **Step 5: Filters and Interactivity**

### **5.1 Adding Filters**:

1. **Filter by Contact Date**:
    - Drag **Contact Date** to the `Filters` shelf.
    - Choose filter options for `Month`, `Quarter`, and `Year`.
    - Add this filter to all worksheets by selecting "Apply to all relevant worksheets" via the filter dropdown.
2. **Filter by Consultation Date**:
    - Repeat the steps as above but use **Consultation Date** instead.
3. **Filter by Surgery Date**:
    - Add **Surgery Date** filter to all worksheets and provide options for `Month`, `Quarter`, `Year`.
4. **Filter by Surgeon**:
    - Drag the **Surgeon** field to the `Filters` shelf.
    - Allow for multi-select so users can filter the dashboard by one or multiple surgeons.
    - Apply this filter to all worksheets.

### **5.2 Interactivity and Filter Actions**:

- **Drill-Down by Surgeons**:
    - Set up a filter action by surgeon to allow the user to click on a KPI or chart and filter down by surgeon across the entire dashboard.
- **Date Range Interactivity**:
    - Add an interactive date slider to allow users to easily adjust the date range of contact, consultation, or surgery.

---

### **Step 6: Validation and Testing**

### **6.1 Data Accuracy**:

- Compare the dashboard outputs (number of patients, surgeries, and occurrences) with the raw data files to ensure accurate representation of data.

### **6.2 Performance Optimization**:

- If working with large datasets, create data extracts for faster performance.
- Consider limiting the data displayed by default (e.g., default to the current quarter) to optimize load times.

---

### **Step 7: Final Deployment**

### **7.1 Publishing to Tableau Server/Online**:

1. After building and testing your dashboard, publish it to **Tableau Server** or **Tableau Online**.
2. Set permissions for clinic administrators and surgeons to view or interact with the dashboard.
3. Ensure all filters and interactivity options are working as intended.

### **7.2 Sharing the Dashboard**:

- Share the link to the dashboard with appropriate stakeholders.
- Provide access to data filtering, saving views, and downloading reports as needed.

---

### **Appendices (Optional)**

- **Data Dictionary**: Include descriptions for each field used (e.g., Contact Date, Surgery Date, Occurrence, etc.).
- **Post-Surgery Outcome Definitions**: Clarify what constitutes an “occurrence” (e.g., complications, follow-up visits).

---

This step-by-step guide ensures the bariatric surgery center can track patient progress efficiently, giving visibility into every stage of the process from contact to post-surgery.>)
