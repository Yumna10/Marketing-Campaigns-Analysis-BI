## ETL for OLAP (Data Warehouse)

###  Main Steps
1. **Extract** raw records from staging/OLTP (Excel & SQL Server).  
2. **Transform** data by applying lookups, surrogate key mapping, cleaning, and type conversions.  
3. **Load** dimension tables first, then fact tables, ensuring referential integrity.  

###  ETL Control Flow
- **Phase 1: Create Dimension Tables**  
   Ensures all surrogate keys are available before loading facts.  
- **Phase 2: Create Fact Tables**  
   Loads transactional and analytical fact data referencing dimension tables.  
- **Final Step: Backup Data Warehouse**  
   Ensures data safety post-load.  

✔ Dependencies are enforced using SSIS control flow arrows, ensuring proper sequencing.

---

##  Data Warehouse Schema Design

The warehouse follows a **Galaxy Schema** structure:
- **Fact Tables** hold business metrics (transactions, campaign results, engagement).  
- **Dimension Tables** provide descriptive context (products, customers, companies, campaigns, dates).  

This design supports:
- High performance queries.  
- Business-friendly navigation in BI tools.  
- Seamless integration with **SSAS**, **SSRS**, **Power BI**, and **Tableau**.  

---

##  Dimension Tables

| Dimension        | Description |
|------------------|-------------|
| **Dim_Product** | Catalog of products (name, category, price, stock, availability, URL). |
| **Dim_Customer** | Customer demographics & behavior (name, gender, age, location, past purchases, preferred platform). |
| **Dim_Company** | Company details (name, website, country, industry, year founded). |
| **Dim_Target_Audience** | Campaign audience attributes (interests, behaviors, location, age range). |
| **Dim_Ad_Content** | Metadata of ad creatives (type, headline, description). |
| **Dim_Date** | Universal time dimension (date, month, quarter, year, weekday/weekend flag). |

---

##  Fact Tables

| Fact Table                   | Purpose | Key Metrics | Linked Dimensions |
|-------------------------------|---------|-------------|-------------------|
| **Fact_Campaign**             | Campaign performance | Impressions, clicks, conversions, revenue, budget, spend, duration | Company, Ad_Content, Target_Audience, Date |
| **Fact_Engagement_Acquisition** | Customer engagement | Event count, value, session duration, session number, new users | Customer, Company, Date |
| **Fact_Transaction**          | Sales transactions | Transaction value, payment method, quantity purchased | Customer, Product, Date |

---

##  Keys & Relationships
- **Primary Keys (PK):** Ensure uniqueness in dimension/fact records.  
- **Foreign Keys (FK):** Connect facts to dimensions (e.g., `Product_ID` in Fact_Transaction → Dim_Product).  
- Enforces **referential integrity** and supports reliable OLAP queries.  

---

##  Data Quality & Auditing
- Truncate-and-load pattern with **row count validation**.  
- **Error handling**: failed lookups logged in error tables.  
- **Unknown SK handling** for missing dimension matches.  

---

##  Scheduling & Orchestration
- Packages are executed in order with **SQL Server Agent**.  
- Dimensions load first (parallelized when possible), followed by dependent fact tables.  

---

##  Testing & Validation
After each fact load:
- Row counts match staging tables.  
- No foreign key mismatches.  
- Calculated measures (e.g., revenue = qty × price) are validated.  

---

##  Common Pitfalls & Mitigation
- **Forgotten dimensions before fact loads** → Controlled by SSIS execution order.  
- **Bad data causing FK errors** → Mitigated with "Unknown" surrogate keys.  
