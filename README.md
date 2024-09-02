# Apply filters to SQL queries

## Project description
My organization is working to make their system more secure. It is my job to ensure the system is safe, investigate all potential security issues, and update employee computers as needed. The following steps provide examples of how I used SQL with filters to perform security-related tasks.

## Retrieve after-hours failed login attempts
There was a potential security incident that occurred after business hours (after 18:00). All after-hours login attempts that failed need to be investigated.

The following code demonstrates how I created a SQL query to filter for failed login attempts that occurred after business hours.

![](/docs/sql1.png)

The first part of the screenshot is my query, and the second part is a portion of the output. This query filters for failed login attempts that occurred after 18:00. First, I started by selecting all data from the **log_in_attempts** table. Then, I used a **WHERE** clause with an **AND** operator to filter my results to output only login attempts that occurred after 18:00 and were unsuccessful. The first condition is **login_time > '18:00'**, which filters for the login attempts that occurred after 18:00. The second condition is **success = FALSE**, which filters for the failed login attempts.

## Retrieve login attempts on specific dates
A suspicious event occurred on 2022-05-09. Any login activity that happened on 2022-05-09 or on the day before needs to be investigated.

The following code demonstrates how I created an SQL query to filter for login attempts that occurred on specific dates.

![](/docs/sql2.png)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred on 2022-05-09 or 2022-05-08. First, I started by selecting all data from the **log_in_attempts** table. Then, I used a **WHERE** clause with an **OR** operator to filter my results to output only login attempts that occurred on either 2022-05-09 or 2022-05-08. The first condition is **login_date = '2022-05-09'**, which filters for logins on 2022-05-09. The second condition is **login_date = '2022-05-08'**, which filters for logins on 2022-05-08.

## Retrieve login attempts outside of Mexico
After investigating the organization’s data on login attempts, I believe there is an issue with the login attempts that occurred outside of Mexico. These login attempts should be investigated.

The following code demonstrates how I created a SQL query to filter for login attempts that occurred outside of Mexico.

![](/docs/sql3.png)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred in countries other than Mexico. First, I started by selecting all data from the **log_in_attempts** table. Then, I used a **WHERE** clause with **NOT** to filter for countries other than Mexico. I used **LIKE** with **MEX%** as the pattern to match because the dataset represents Mexico as **MEX** and **MEXICO**. The percentage sign **(%)** represents any number of unspecified characters when used with **LIKE**.

## Retrieve employees in Marketing
My team wants to update the computers for certain employees in the marketing department. To do this, I have to get information on which employee machines to update.

The following code demonstrates how I created a SQL query to filter for employee machines from employees in the marketing department in the East building.

![](/docs/sql4.png)

My query is in the screenshot, followed by some output. This query returns all employees in the marketing department in the East building. 

First, I started by selecting all data from the **employees** table. Then, I used a **WHERE** clause with **AND** to filter for employees who work in the marketing department and in the East building. I used **LIKE** with **East%** as the pattern to match because the data in the **office** column represents the East building with the specific office number. The first condition is the **department = 'Marketing'** portion, which filters for employees in the Marketing department. The second condition is the **office LIKE 'East%'** portion, which filters for employees in the East building.