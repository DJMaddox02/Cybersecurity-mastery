# LAB: Applying Filters to SQL Queries for Security Investigations
Date Completed: 10/10/2024
Skills: SQL Filtering, Log Analysis, Pattern matching
Source: Google Cybersecurity Certificate

## Project Description 
This organization tasked me with investigating potential security incidents by querying login and employee data. I used SQL filters to extract specific events from login logs and employee records.

The goal was to identify:
- Suspicious login activity (e.g., after-hours access, forign logins)
- Employee machines that required software updates based on department

## Key SQL Task
### 1. **Failed Login Attempts After Buisness Hours**
```sql
SELECT * FROM log_in_attempts
WHERE login_time > '18:00' AND success = FALSE;
```
- Filtered failed login attempts occurring after 6PM

### 2. Login Attempts on Specific Dates 
```sql
SELECT * FROM log_in_attempts
WHERE login_date = '2022-05-09' or login_date = '2022-05-08";
```
- Investigated suspicious activity surrounding a known incident date

### 3. Login Attempts Outside of Mexico
```sql
SELECT * FROM log_in_attempts
WHERE country NOT LIKE 'MEX%';
```
- Used NOT LIKE and % wildcard to catch both "MEX" and "MEXICO".

### 4. Employees in Marketing, East Building
```sql
SELECT * FROM log_in_attempts
WHERE department = 'Marketing' AND office LIKE 'East%';
```
- Prepared a list of machines in Marketing (East Wing) for updates

### 5. Employees in Finance or Sales
```sql
SELECT * FROM employees
WHERE department = 'Finance' OR department = 'Sales';
```
- Queried machines that needed a diffrent security update

### 6. Employees Not in IT
```sql
SELECT * FROM employees
WHERE department != 'Information Technology';
```
- Isoloated users not in IT for security rollout

## Summary
In this lab, I demonstrated how to:
- Use SQL WHERE, AND, OR, NOT, and LIKE filters
- Investigate login behaviors and identity outliers
- Query employee data for role-based security task
This type of work is typicall for SOC analysts who need to filter large datasets for threat investigation and endpoint managment.

# Tools Used 
- SQL (SELECT, WHERE, AND, OR, NOT, LIKE)
- Log and employee data tables
    (log_in_attempts, employees)

