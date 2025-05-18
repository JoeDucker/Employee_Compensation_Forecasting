# Employee Compensation Forecasting Application

This project was developed as part of the Spaulding Ridge case study for the Management Trainee role. It provides HR and business stakeholders with an interactive way to:
- Analyze current employee compensation
- Apply forecasting adjustments using a What-If slider
- Understand employee distribution by role, experience, and location
- Compare compensation across roles and locations
- Export actionable data

## Tools & Technologies Used

- Power BI Desktop – for interactive visualizations and dashboard creation
- MySQL – to build and normalize relational database tables
- DAX – for custom calculations and dynamic measures
- SQL Scripts – for table creation, inserts, and stored procedures
- Excel/CSV – for uploading sample datasets

## Database Setup & Execution

Database Setup (MySQL)
- Import employee-related CSV files into MySQL.
- Normalize tables into Third Normal Form (3NF)
- Use provided SQL scripts to:
    * Create tables (Employee, Assignment, Role, Location, Rating)
    *  Insert sample data (~300 rows)
    *  Define stored procedures (e.g., GetEmployeeCompensation)

Power BI Setup
- Connect to MySQL database via Power BI
- Perform data modeling:
    * Relationships: Employee → Assignment → Role/Location
    * One-to-many relations between normalized tables
- Load data tables and measures
- Add visual elements with interactivity:
    * Slicers (Role, Location, Active)
    * KPI cards, gauges, charts, Q&A panel

## User Stories & Implementation

### User Story 1: Filter and Display Active Employees by Role
- Table with: Name, Role, Location, Experience, Compensation
- Slicers to filter by: Role, Location, and Active status
- Gauge shows average updated compensation
- Bar chart shows average compensation by location

### User Story 2: Group Employees by Years of Experience
- Created Experience_Range column using calculated DAX
- Pie chart and bar chart show count of employees in each range
- Additional breakdown possible by Role or Location

### User Story 3: Simulate Compensation Increments
- Used Power BI What-If Parameter: Increment_Percentage
- Measures:
   * Updated_Compensation
   * Total_Increment_Impact
   * Compensation_Growth_Percent
- KPI visual shows Total Increment Impact vs Target Budget
- Gauge and card visuals reflect dynamic values

### User Story 4: Download Filtered Employee Data
- Table visual includes: Name, ID, Role, Location, Experience, Status, Compensation
- Export feature enabled via Power BI (ellipsis → Export Data → CSV)
- Export reflects current filters and incremented values

## Q&A Visual (Chatbot-style)
- Added Power BI Q&A visual to allow users to type natural questions
- Allows users to ask:
    * "Average compensation by role"
    *  "Employees in Bangalore with more than 5 years experience"
    *  "Top 5 paid employees"

## Author
- Jyothy Jacob 
- PGDM (2025) 
- Email ID: jyothy07che@xime.org
- https://www.linkedin.com/in/jyothy-jacob/


