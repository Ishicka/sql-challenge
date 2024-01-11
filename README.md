# sql-challenge
# Instructions
This Challenge is divided into three parts: data modeling, data engineering, and data analysis.

Data Modeling
Inspect the CSV files, and then sketch an Entity Relationship Diagram of the tables. To create the sketch, feel free to use a tool like QuickDBDLinks to an external site..

Data Engineering
Use the provided information to create a table schema for each of the six CSV files. Be sure to do the following:

Remember to specify the data types, primary keys, foreign keys, and other constraints.

For the primary keys, verify that the column is unique. Otherwise, create a composite keyLinks to an external site., which takes two primary keys to uniquely identify a row.

Be sure to create the tables in the correct order to handle the foreign keys.

Import each CSV file into its corresponding SQL table.

HINT
Data Analysis
List the employee number, last name, first name, sex, and salary of each employee.

List the first name, last name, and hire date for the employees who were hired in 1986.

List the manager of each department along with their department number, department name, employee number, last name, and first name.

List the department number for each employee along with that employee’s employee number, last name, first name, and department name.

List first name, last name, and sex of each employee whose first name is Hercules and whose last name begins with the letter B.

List each employee in the Sales department, including their employee number, last name, and first name.

List each employee in the Sales and Development departments, including their employee number, last name, first name, and department name.

List the frequency counts, in descending order, of all the employee last names (that is, how many employees share each last name).

# Data Overview
There were 6 total tables included in the CSV dataset:
•	departments
•	dept_emp
•	dept_manager
•	employees
•	salaries
•	titles
# Relationships Overview:
1.	Relationship between departments and dept_emp:
•	One-to-Many relationship from departments to dept_emp.
•	Each department in the departments table can have multiple records in the dept_emp table, but each record in the dept_emp table is associated with only one department.
2.	Relationship between departments and dept_manager:
•	One-to-Many relationship from departments to dept_manager.
•	Each department in the departments table can have multiple records in the dept_manager table, but each record in the dept_manager table is associated with only one department.
3.	Relationship between employees and dept_emp:
•	One-to-Many relationship from employees to dept_emp.
•	Each employee in the employees table can have multiple records in the dept_emp table, but each record in the dept_emp table is associated with only one employee.
4.	Relationship between employees and dept_manager:
•	One-to-One relationship from employees to dept_manager.
•	Each employee in the employees table is associated with exactly one record in the dept_manager table.
5.	Relationship between employees and salaries:
•	One-to-One relationship between employees to salaries.
•	Each employee in the employees table is associated with exactly one record in the salaries table.
6.	Relationship between employees and titles:
•	One-to-Many relationship from employees to titles.
•	Each employee in the employees table can have multiple records in the titles table, but each record in the titles table is associated with only one employee. 

## Data Type Summary:
1.	Departments Table:
•	dept_no (Primary Key, VARCHAR(4))
•	dept_name (TEXT)

2.	Employees Table:
•	emp_no (Primary Key, INT)
•	emp_title_id (VARCHAR(5), Foreign Key references titles.title_id)
•	birth_date (DATE)
•	first_name (TEXT)
•	last_name (TEXT)
•	gender (VARCHAR(1))
•	hire_date (DATE)

3.	Dept_Emp Table:
•	emp_no (Primary Key, Foreign Key references employees.emp_no)
•	dept_no (Foreign Key references departments.dept_no)

4.	Dept_Manager Table:
•	dept_no (Foreign Key references departments.dept_no)
•	emp_no (Foreign Key references employees.emp_no)

5.	Salaries Table:
•	emp_no (Primary Key, Foreign Key references employees.emp_no)
•	salary (INT)

6.	Titles Table:
•	title_id (Primary Key, VARCHAR(5))
•	title (TEXT)

