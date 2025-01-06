# Apply filters to SQL queries

## Objective
My organization is working to make their system more secure. It is my job to ensure the system is safe, investigate all potential security issues, and update employee computers as needed. The following steps provide examples of how I used SQL with filters to perform security-related tasks.

## Description of Work Done
### Retrieve after hours failed login attempts
There was a potential security incident that occurred after business hours (after 18:00). All after hours login attempts that failed need to be investigated.

The following code demonstrates how I created a SQL query to filter for failed login attempts that occurred after business hours.

![after hours failed login attempts](https://github.com/user-attachments/assets/f385111d-4797-4bc1-aa81-a6b5c89f4764)

he first part of the screenshot before the table is my query, and the second part is a portion of the output from my query. This query filters for failed login attempts that occurred after my organization closing hour (18:00). First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an AND operator to filter my results to output only failed login attempts that occurred after 18:00. 
The first condition login_time > '18:00', filters for the login attempts that occurred after 18:00. The second condition success = FALSE, filters for the failed login attempts. 

### Retrieve login attempts on specific dates
A suspicious event occurred on 2022-05-09. Any login activity that happened on 2022-05-09 or on the day before (2022-05-08) needs to be investigated.

Here is how I tackled the problem with the following code:
![login attempts on specific date](https://github.com/user-attachments/assets/c5893808-2382-4425-ac71-7c85c29227fb)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred on 2022-05-09 or 2022-05-08. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an OR operator to filter my results to output only login attempts that occurred on either 2022-05-09 or 2022-05-08. The first condition is login_date = '2022-05-09', which filters for logins on 2022-05-09. The second condition is login_date = '2022-05-08', which filters for logins on 2022-05-08.

### Retrieve login attempts outside of Mexico
After investigating the organization’s data on login attempts, I believe there is an issue with the login attempts that occurred outside of Mexico. These login attempts should be investigated.

The following code demonstrates how I created a SQL query to filter for login attempts that occurred outside of Mexico. 
![login attempts outside Mexico](https://github.com/user-attachments/assets/b9d55ded-b6c8-425a-934d-2a592ae0e552)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred in countries other than Mexico. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with NOT to filter for countries other than Mexico. I used LIKE with MEX% as the pattern to match because the dataset represents Mexico as MEX and MEXICO. The percentage sign (%) represents any number of unspecified characters when used with LIKE.

### Retrieve employees in Marketing
My team wants to update the computers for certain employees in the Marketing department. To do this, I have to get information on which employee machines to update.

Here is the code I ran to to tackle this situation:
![employees in Marketing](https://github.com/user-attachments/assets/6259d838-aaa4-4f4b-b5ab-d675a230698b)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Marketing department in the East building. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with AND to filter for employees who work in the Marketing department and in the East building. I used LIKE with East% as the pattern to match because the data in the office column represents the East building with the specific office number. The first condition is the department = 'Marketing' portion, which filters for employees in the Marketing department. The second condition is the office LIKE 'East%' portion, which filters for employees in the East building.

### Retrieve employees in Finance or Sales
The machines for employees in the Finance and Sales departments also need to be updated. Since a different security update is needed, I have to get information on employees only from these two departments.

The following were the code I used to filter for employee machines from employees in the Finance or Sales departments
![Employees in Finance or Sales](https://github.com/user-attachments/assets/6a28ad44-b16d-44ec-a4a3-4670061360af)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Finance and Sales departments. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with OR to filter for employees who are in the Finance and Sales departments. I used the OR operator instead of AND because I want all employees who are in either department. The first condition is department = 'Finance', which filters for employees from the Finance department. The second condition is department = 'Sales', which filters for employees from the Sales department.

### Retrieve all employees not in IT
My team needs to make one more security update on employees who are not in the Information Technology department. To make the update, I first have to get information on these employees.

To solve this, I ran a code that filters out Information technology department and shows all other departments
![All Employees Not in IT](https://github.com/user-attachments/assets/8dbaa156-7fc3-47c9-a24a-e3d9dfb91e10)

The first part of the screenshot is my query, and the second part is a portion of the output. The query returns all employees not in the Information Technology department. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with NOT to filter for employees not in this department.

## Summary
In this project, I applied filters to SQL queries to get specific information on login attempts and employee machines. I used two different tables from my organization database, log_in_attempts and employees. I used the AND, OR, and NOT operators to filter for the specific information needed for each task. I also used LIKE and the percentage sign (%) wildcard to filter for patterns.
