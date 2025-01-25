---
page-tags: "[[tableau]]"
---

## **Table of Contents**

1. **Project Overview**
   - Project Goal
   - Key Stakeholders
   - Data Sources
   - Audience

2. **Setup**
   - Required Software and Tools
   - Initial Data Preparation
   - Connection to Data Sources

3. **Data Cleaning and Transformation**
   - Data Preparation in Tableau
   - Filters and Parameters

4. **Building the Dashboard**
   - Worksheets
   - Visualizations
   - Layout and Design

5. **Interactivity and Functionality**
   - Filters
   - Parameters
   - Actions (Filter, Highlight, URL)

6. **Validation and Testing**
   - Data Accuracy
   - Performance Optimization

7. **Final Deployment**
   - Publishing to Tableau Server/Online
   - Sharing and Permissions

---

### 1. **Project Overview**

#### **1.1 Project Goal:**
Clearly define the purpose of the dashboard. For example:
- *Goal*: To provide sales performance insights by region and product category.

#### **1.2 Key Stakeholders:**
- List the individuals or teams who will be using or reviewing the dashboard.

#### **1.3 Data Sources:**
- List each data source used (e.g., SQL Database, Excel files, etc.).
- Provide the connection details or credentials needed to access the data.

#### **1.4 Audience:**
- Define the intended audience for the dashboard and their data consumption needs.

---

### 2. **Setup**

#### **2.1 Required Software and Tools:**
- **Tableau Desktop version:** Specify the exact version of Tableau used.
- **Additional tools:** (if needed) Specify any additional tools used, e.g., Excel, Alteryx, etc.

#### **2.2 Initial Data Preparation:**
Provide detailed steps on how the data should be prepared before it is brought into Tableau:
- E.g., "Remove unnecessary columns, clean up null values in Excel."

#### **2.3 Connection to Data Sources:**
- *Step 1:* Open Tableau Desktop and navigate to the "Connect" pane on the left.
- *Step 2:* Select the correct data source (e.g., Microsoft Excel, Server).
- *Step 3:* Provide step-by-step instructions on connecting to the data source (e.g., database connection string, Excel file path).

---

### 3. **Data Cleaning and Transformation**

#### **3.1 Data Preparation in Tableau:**
- Explain if any data joins, unions, or data extracts are necessary.
- *Step 1:* "Join the Sales table and Region table using the Region ID field."
- *Step 2:* "Rename columns for consistency (e.g., change 'RegionID' to 'Region')."

#### **3.2 Filters and Parameters:**
- Define the filters you will use (e.g., date ranges, specific categories).
- *Step 1:* "Create a Date Range filter by dragging the Date field to the Filters shelf and selecting the relevant range."
- *Step 2:* "Create a 'Region' filter by dragging 'Region' to the Filters shelf."

---

### 4. **Building the Dashboard**

#### **4.1 Worksheets:**
For each worksheet, describe the following:

- *Name of Worksheet*: (e.g., "Sales by Region")
- *Data Source*: (e.g., "Sales Data 2023")
- *Fields used*: List each field and explain why it was selected (e.g., “Region – used to break down sales performance by region”).
- *Type of chart/visualization*: Explain why you selected the specific chart (e.g., "Bar Chart to show regional comparison").

#### **4.2 Visualizations:**
Describe each visualization and its components:
- *Visualization Type*: (e.g., bar chart, line chart, scatter plot).
- *Axis setup*: (e.g., "X-axis: Region, Y-axis: Sales").
- *Color Scheme*: Provide details on the colors used and their significance.
- *Calculated Fields*: Describe any calculated fields used in the visualization (e.g., Profit Margin = SUM(Profit) / SUM(Sales)).

#### **4.3 Layout and Design:**
- Explain the dashboard layout and structure, including specific positioning of elements:
  - E.g., "Place the 'Sales by Region' bar chart in the top-left quadrant."
- Describe font choices, colors, and other design elements, explaining the reasoning behind them (e.g., “Use blue for positive values and red for negative values”).

---

### 5. **Interactivity and Functionality**

#### **5.1 Filters:**
- Define how filters should be applied across worksheets.
  - E.g., "Use a global filter on 'Region' to filter all visualizations by selected region."

#### **5.2 Parameters:**
- Describe any parameters used and their impact on the dashboard.
  - E.g., "Create a 'Date Range' parameter to allow users to dynamically select a specific time range."

#### **5.3 Actions:**
- Detail any user interaction actions set up (e.g., filter, highlight).
  - *Step 1:* "Set up a Filter Action from the 'Sales by Region' chart to filter the 'Sales by Product Category' chart."
  - *Step 2:* "Highlight Action to emphasize the selected region in other visualizations."

---

### 6. **Validation and Testing**

#### **6.1 Data Accuracy:**
- Explain how to validate that the data is correctly represented in the dashboard.
  - E.g., "Cross-check sales figures against the original data source to ensure no discrepancies."

#### **6.2 Performance Optimization:**
- Describe any optimization steps taken to ensure the dashboard performs well.
  - E.g., "Use data extracts to reduce load time for large datasets."

---

### 7. **Final Deployment**

#### **7.1 Publishing to Tableau Server/Online:**
- Provide instructions for publishing the dashboard to Tableau Server/Online, including access permissions.
  - *Step 1:* "Click File > Publish to Server."
  - *Step 2:* "Set permissions to allow only specific users to view or edit."

#### **7.2 Sharing and Permissions:**
- Describe how to share the dashboard with stakeholders.
  - E.g., "Send the published link with a read-only role to ensure data security."

---

### **Appendices (Optional)**

- **Data Dictionary**: Define each field and its purpose in the dashboard.
- **Additional Notes**: Provide any other instructions or contextual details.

---
