# Employee Compensation Forecasting Application

This project is a Power BI-based application built as part of the Spaulding Ridge case study to help HR and business stakeholders:
- Analyze current employee compensation
- Simulate future compensation based on fixed or variable increments
- View workforce distribution
- Export actionable insights

## Tools & Technologies Used

- Power BI Desktop – for dashboard creation and analysis
- MySQL – for setting up the relational database
- DAX (Data Analysis Expressions) – for custom calculations
- SQL – to create tables, normalize data (3NF), and define stored procedures
- Excel – for data preparation and loading into Power BI
- Power BI Q&A Visual – for natural language querying

## Database Setup & Execution

1. Import all `.csv` files into MySQL as separate tables
2. Normalize tables into 3NF
3. Use provided SQL scripts to:
   - Create tables
   - Insert sample data
   - Define stored procedures

4. Connect Power BI to MySQL database
5. Perform data modeling using primary/foreign keys
6. Load transformed tables into Power BI for visualization

## User Stories & Implementation

### User Story 1: Filter and Display Active Employees by Role
- Used slicers for **Role**, **Location**, and **Active status**
- Table visual displays: Name, Role, Location, Compensation
- Added measure for `Updated_Compensation` based on slider input
- Visuals: Bar chart comparing average compensation across locations

### User Story 2: Group Employees by Years of Experience
- Created calculated column `Experience_Range`
- Used bar and pie charts to show count of employees by experience
- Optional slicers: group by Role and Location

### User Story 3: Simulate Compensation Increments
- Added What-If Parameter (`Increment_Percentage`)
- Dynamic measure `Updated_Compensation` reflects incremented values
- Visuals: Gauge for average updated comp, KPI cards for totals

### User Story 4: Download Filtered Employee Data
- Table visual includes: Name, ID, Role, Location, Experience, Status, Compensation
- Export feature enabled via Power BI (ellipsis → Export Data → CSV)
- Export reflects current filters and incremented values

## Q&A Visual
- Added Power BI Q&A visual to allow users to type natural questions
- Examples:  
   - “Total compensation for Managers in Bangalore”  
   - “Employees with more than 5 years experience”

## Author
- Jyothy Jacob 
- PGDM (2025) 
- Email ID: jyothy07che@xime.org
- https://www.linkedin.com/in/jyothy-jacob/


