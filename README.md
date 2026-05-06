Enterprise IT Operations Analysis Dashboard
Project Overview

This project is an end-to-end Power BI dashboard solution designed to analyze enterprise IT operations data and provide actionable insights into incident management, SLA compliance, ticket aging, and engineer performance.

The dashboard simulates a real-world IT service management (ITSM) environment and helps monitor operational efficiency across support teams.

Business Problem

Enterprise IT teams handle a large volume of support tickets across multiple departments. Monitoring ticket lifecycle, SLA adherence, backlog, escalations, and engineer performance is critical for maintaining service quality.

This dashboard was built to solve key operational challenges such as:

Tracking ticket inflow and resolution trends
Monitoring SLA compliance and breaches
Identifying aging/backlog tickets
Evaluating engineer workload and performance
Analyzing incidents across categories and regions
Dataset Information

The dataset used in this project is a simulated enterprise IT operations dataset containing 6,000 ticket records.

Data Period
January 2026
February 2026
March 2026
Dataset Includes
Ticket ID
Created Date
Resolved Date
Closed Date
Priority
Category
Subcategory
Assignment Group
Assigned Engineer
Department
Status
SLA Due Date
SLA Status
Resolution Time (Hours)
Reopened Flag
Escalated Flag
Region
Customer Type
Dashboard Pages
1. Executive Dashboard

Provides a high-level operational overview.

KPIs:

Total Tickets
Open Tickets
In Progress Tickets
Resolved Tickets
Closed Tickets
Average Resolution Time
SLA Compliance %
SLA Breach Count
Reopened %
Escalation %
2. Incident Analysis Dashboard

Focused on operational incident insights.

Analysis Includes:

Backlog Tickets
Priority Distribution
Category Analysis
Region Analysis
Customer Type Analysis
Aging Tickets Analysis
3. Engineer Performance Dashboard

Measures support engineer performance.

Metrics Include:

Total Assigned Tickets
Resolved Tickets
Closed Tickets
Average Resolution Time
SLA Breach Count
Reopened Tickets
Escalated Tickets
Data Model

This project follows a Star Schema Data Model.

Fact Table
Fact_Tickets
Dimension Tables
Dim_Date
Dim_Engineer
Dim_Group
Dim_Department
Dim_Category
Dim_Priority
Power BI Features Used
Power Query for data transformation
DAX for calculated columns and measures
Data modeling and relationships
Bookmarks for navigation
KPI cards
Trend analysis visuals
Donut charts
Bar charts
Interactive slicers
Key DAX Measures
Total Tickets
Total Tickets = COUNT(Fact_Tickets[Ticket ID])
SLA Compliance %
SLA Compliance % =
DIVIDE(
    CALCULATE(COUNTROWS(Fact_Tickets), Fact_Tickets[SLA Status]="Met"),
    COUNTROWS(Fact_Tickets)
)
Average Resolution Time
Avg Resolution Time = AVERAGE(Fact_Tickets[Resolution Time (Hours)])
Aging Days
Aging Days =
IF(
    Fact_Tickets[Status] IN {"Open", "In Progress"},
    DATEDIFF(Fact_Tickets[Created Date], DATE(2026,3,31), DAY),
    0
)
Project Insights
SLA compliance maintained above 75%
Ticket inflow trends identified across three months
Engineer-level performance tracked effectively
Aging tickets monitored to identify backlog risks
Department-wise ticket distribution analyzed
Project Files
Power BI Dashboard (.pbix)
Dataset (.xlsx)
Dashboard Screenshots
Project Demo Video
Dashboard Preview
<img width="1437" height="806" alt="image" src="https://github.com/user-attachments/assets/d994f0b7-a11b-461f-8db5-1e5d01130424" />
<img width="1431" height="803" alt="image" src="https://github.com/user-attachments/assets/865800b3-c1df-40b8-9494-b927a16683ad" />
<img width="1435" height="801" alt="image" src="https://github.com/user-attachments/assets/75c51410-04c0-44d5-8b49-848fd2b98a43" />


Tools Used
Microsoft Power BI
Power Query
DAX
Excel
Future Enhancements
Real-time ticket monitoring
Predictive SLA breach analysis
Root cause analysis dashboard
MTTR and MTTA metrics
Author

Suhaim Sulaiman

If you found this project useful, feel free to connect and share feedback.
