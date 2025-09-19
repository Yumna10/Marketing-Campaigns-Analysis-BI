# Marketing Campaigns Analysis - Project Overview
This project provides a Business Intelligence solution for DigiHype, a digital marketing company managing campaigns for clients like Apple, Samsung, Sony, Lenovo, Dell, and Huawei.
 As BI developers, we analyzed customer, product, and campaign data  over a defined period to measure performance, track KPIs, and deliver insights through an interactive dashboard, Our goal is to transform raw marketing data into **actionable business insights** that help evaluate campaigns, optimize targeting, and improve ROI.  

The system integrates multiple tools:
- **SQL Server (OLTP & OLAP)**
- **SSIS (ETL Packages)**
- **SSAS (Data Modeling & Cubes)**
- **SSRS (Paginated Reports)**
- **Power BI (Interactive Dashboards)**
- **Tableau (Advanced Visualizations)**


##  Objectives
- Consolidate marketing data from multiple sources into a **centralized Data Warehouse**.  
- Automate **ETL processes** for clean, consistent, and reliable data.  
- Build **analytical cubes (SSAS)** for multidimensional performance analysis.  
- Deliver **reports and dashboards** tailored to decision-makers, marketers, and analysts.  
- Provide **actionable insights** into campaign effectiveness, customer engagement, and ROI.  

---

##  Scope of Analysis
- **Company Perspective** → overall reach, budget allocation, ROI.  
- **Campaign Perspective** → clicks, impressions, conversions, engagement rate.  
- **Customer Perspective** → demographics, acquisition channels, retention.  
- **Product Perspective** → sales volume, pricing impact, promotions.  
- **Website Perspective** → traffic, sessions, event tracking linked to campaigns.  

---

##  Tech Stack & Tools
- **Database & ETL**: SQL Server, SSIS  
- **Data Warehouse**: **Galaxy Schema** (multiple fact tables with shared dimension tables)  
- **Analytics**: SSAS (OLAP Cubes, KPIs)  
- **Reporting**: SSRS (Paginated Reports)  
- **Visualization**: Power BI & Tableau 

---

##  Data Flow
1. **Raw Data (Excel)** → staging via **SSIS (Phase 1)**  
2. **SQL Server OLTP** → structured storage with relationships  
3. **Data Warehouse (OLAP)** → **Galaxy Schema** with multiple fact tables
4. **SSAS Cubes** → multidimensional models & KPIs  
5. **SSRS Reports** → campaign profit & performance analysis  
6. **Power BI & Tableau Dashboards** → interactive insights & visual exploration 

---

##  Deliverables
-  Centralized **Data Warehouse** based on **Galaxy Schema**  
-  Automated **ETL workflows** with error handling & scheduling  
-  Analytical **OLAP Cubes** with KPIs (SSAS)  
-  **SSRS Reports** for campaign profitability & audience details  
-  **Power BI Dashboards**: Campaign Insights, Customers, Engagement, Ads  
-  **Tableau Dashboards**: Revenues, Transactions, Ad Stats  

---

##  Business Value Delivered
- Unified view of marketing data (eliminating silos).  
- Faster, data-driven decisions with real-time insights.  
- Optimized marketing budget allocation & campaign targeting.  
- Improved customer engagement & higher conversion rates.  
- Scalable BI platform for future analytics needs.  

---

##  Lessons Learned
- Importance of **data consistency** across multiple sources.  
- Balancing **technical implementation** with **business relevance**.  
- Hands-on experience with full BI lifecycle (ETL → DW → Analysis → Reporting → Visualization).  

---

##  Dashboards Preview
![Alt Text](Power%20BI%20Dashboard/overview.png)  
![Alt Text](Power%20BI%20Dashboard/campaigns1.png)  
![Alt Text](Power%20BI%20Dashboard/campaigns2.png)  
![Alt Text](Power%20BI%20Dashboard/ads.png)  
![Alt Text](Power%20BI%20Dashboard/companies1.png)  
![Alt Text](Power%20BI%20Dashboard/companies2.png)  
![Alt Text](Power%20BI%20Dashboard/product.png)  
![Alt Text](Power%20BI%20Dashboard/engagement.png)  
![Alt Text](Power%20BI%20Dashboard/customers.png)  

---

## Detailed documentation
A detailed explanation of each project phase (ETL, Data Warehouse design, SSAS modeling, SSRS reporting, Power BI and Tableau dashboards) is available in its respective folder. See:
- `ETL_SSIS/`
- `DataWarehouse/`
- `SSAS/`
- `SSRS/`
- `Power BI Dashboard/`
- `Tableau/`

Each folder contains step-by-step documentation, diagrams, and implementation notes for that stage.

---
