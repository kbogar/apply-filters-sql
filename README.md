# Apply filters to SQL queries

## Project description
My organization is working to make their system more secure. It is my job to ensure the system is safe, investigate all potential security issues, and update employee computers as needed. The following steps provide examples of how I used SQL with filters to perform security-related tasks.

## Retrieve after-hours failed login attempts
There was a potential security incident that occurred after business hours (after 18:00). All after-hours login attempts that failed need to be investigated.

The following code demonstrates how I created a SQL query to filter for failed login attempts that occurred after business hours.

![](/docs/sql1.png)

The first part of the screenshot is my query, and the second part is a portion of the output. This query filters for failed login attempts that occurred after 18:00. First, I started by selecting all data from the **log_in_attempts** table. Then, I used a **WHERE** clause with an **AND** operator to filter my results to output only login attempts that occurred after 18:00 and were unsuccessful. The first condition is **login_time > '18:00'**, which filters for the login attempts that occurred after 18:00. The second condition is **success = FALSE**, which filters for the failed login attempts. 