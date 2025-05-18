# Employee Compensation Forecasting Application (WinForms Edition)

This version of the Employee Compensation Forecasting App was developed using Windows Forms (C#) and SQL Server as part of the Spaulding Ridge case study for the Management Trainee role. It offers HR and business users an interactive desktop tool to:

- View current employee compensation
- Apply percentage-based forecasting adjustments via a user input field
- Filter employees by role and location
- Display average updated compensation
- Export updated compensation data
- Package and deploy the app to other PCs

---

## Tools & Technologies Used

- **Visual Studio (WinForms / .NET Framework)** – for building the desktop application
- **Microsoft SQL Server Management Studio (SSMS)** – for database creation, normalization, and queries
- **C# with ADO.NET** – to connect UI with the SQL database and apply business logic
- **CSV Files** – to import and populate employee-related tables
- **ClickOnce Deployment** – for packaging the app to run on other machines

---
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

## Database Setup & Execution for app

1. **Database Engine**: SQL Server (not MySQL)
2. **Tables Created**:
   - `employee_data` (with Role, Location, Compensation, and Experience fields)
   - `employee_rating`, `employment_assignment`, `location`, and `role`
3. **Normalization**: Third Normal Form (3NF)
4. **Import**: CSV files uploaded using SSMS's *Import Flat File Wizard*
5. **Issues Handled**:
   - Adjusted data types for `Last_Working_Day` to handle NULLs
   - Renamed or temporarily duplicated tables (`role_temp`, etc.) when name conflicts occurred
   - Error-handled `Role_ID`/`Location_ID` mismatches by querying using actual names (`Role`, `Location`)

---

## Application Features

### 1. **Load Filtered Employee Data**
- Select Role and Location from dropdown menus
- Query filters based on values in `employee_data` table
- Results populate a `DataGridView` with: Employee ID, Name, Years of Experience, Compensation

### 2. **Apply Increment Percentage**
- Enter a percentage value in the input box
- Compensation updates dynamically in the grid
- Label shows total number of records and average compensation

### 3. **Export Updated Compensation**
- Option to export grid data to `.CSV` (to be implemented if not yet done)

### 4. **Deploy to Other PCs**
- Used Visual Studio’s **Publish Wizard** (ClickOnce)
- No update URL selected (offline mode)
- Target path specified manually (e.g., `C:\Users\Documents\Employee Compensation App\`)
- Output is a self-contained installer and shortcut

---

## Deployment Steps (ClickOnce)

1. Right-click project > **Publish**
2. Set file system folder for output (e.g., `C:\Users\<User>\Documents\EmployeeCompensationApp`)
3. Choose **“The application will not check for updates”**
4. Click **Finish**
5. Locate the `.application` file in the publish folder and install

---

## Data Notes

- Source data (~300+ records) was imported from:
   - `employee_data.csv`
   - `employee_rating.csv`
   - `employment_assignment.csv`
   - `location.csv`
   - `role.csv`
   - `bonus_location.csv`
- Various data cleaning and format alignment steps were done (especially for null dates)

---

## Author

- Jyothy Jacob  
- PGDM (2025)  
- Email: jyothy07che@xime.org  
- [LinkedIn](https://www.linkedin.com/in/jyothy-jacob/)
