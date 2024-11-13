# BI-Assessment
An assessment completed for Business Intelligence Role


Tech Assessment
 
This role requires in-depth expertise in Tableau for visualization, SQL for querying large datasets, to coordinate cross-functional projects. The ideal candidate will guide the team in delivering key analytics solutions that empower business stakeholders to make informed decisions.
 
Summary:
·         Please complete this assessment all by yourself. Assistance from AI tools or another person will lead to disqualification.
·         Please complete this assessment within two business days
·         Answer as much as you can. Please contact the recruiter or me if you have any questions during the completion process.
·         You are required to present/demo/explain your answers during the interview
·         Your answer could be in any format, including but not limited to word, pdf, ppt, Tableau workbook, text file, etc.
 
Part A. Answer the SQL-related questions below.
1.      What is the difference between CTE, VIEW, TEMP Table, and Table?
a.      CTE (Common Table Expression) – a named temporary result set that is saved in memory, and can be used multiple times within a query in order to simplify and organize complex queries.  CTE uses a WITH statement to create essentially a subquery to grab the data defined, but it is not accessible anywhere except within the query created.
b.      VIEW - An object that can be found in the database.  A virtual table that shows data without storing it physically.  In order to see the data, the query must be executed, but the results are not saved.  Virtual table based on the result set of a query, without storing the data in the database.  Views are persisted SQL queries in the database.  
Table = physical table, and View = virtual table.
Each view has an attached query.  When we SELECT FROM View we’re triggering the query attached to the view.  The views are an abstraction layer from the view and the data.
Views are easier to change and maintain.
Views will take longer to pull than if pulling from a table.  Read only, cant write to table.
We use views to store central complex query logic in the database for access by multiple queries, reducing project complexity.
c.       TEMP Table - Exists until the session ends.
d.      Table - Where the data persists and is physically stored.  Hard to change or maintain.  Fast response from selecting from table.  Can Read/write.
A table is an object in the database structure.  A table is structured collection of data, similar to a spreadsheet or grid, like excel.  Columns/rows.  Its an abstraction of the physical data in the database.
Permanent tables exist until they are dropped.
create/select or CTAS to create tables.
Create/insert
First define the structure of the table.
Insert data into the table. Like from a CSV, another database, or manually entered.
CTAS - create table as select
Create a new table based on the result of an SQL query.
The structure and data of the new table comes from the result of the query. Always needs a database table to look at in the query.
Tables store the data, which makes it faster to query a table than a view.  But views update dynamically, while the table is not dynamically updated and must be manually updates.
CREATE TABLE table-name
(column names.
Insert into table-name
CREATE TABLE table-name AS
(SELECT FROM WHERE)


SELECT INTO new-table
FROM WHERE
2.      When and how do you use the different CTE, VIEW, TEMP Table, and Table?
a.      CTE – Used to eliminate redundant subqueries that would normally be needed to aggregate multiple complex queries.  A WITH statement would be used at the start of your query to define the result, that can then be used multiple times throughout the query, as opposed to using subqueries, which can only be used once in your main query.  Improves readability and makes the query more manageable by breaking the data down into parts.  Could be used as a standalone query, independent from the main query, or multiple CTE’s.  The main query must begin immediately following the CTE query.
                                                              i.      Non-recursive CTE vs. Recursive CTE.  Recursive CTE is a self-referencing query that repeatedly processes data until a specific condition is met.  Essentially looping the CTE until the exit parameter is met.  The recursive query process begins with an anchor query which is only ran once, then the recursive query in ran until the parameter is met.
Common Table Expression is temporary, named result set that can be used multiple times within the query.  Result of CTE is like a Table, but only stored in memory, and cannot be used from multiple queries

b.      VIEW – If multiple teams need to access the same data in order to conduct different analysis, views allow you to create a single source of information, rather than creating independent queries to achieve the same result.  Reduces redundancy across multiple queries.  Improve reusability.  Persists logic.  Needs to be maintained - create/drop.
	Vs. CTE - Reduces redundancy in 1 query, improve reusability in 1 query, temporary logic (on the fly), and no maintenance.
Views look to be better for dynamic data.
CREATE VIEW name-of-view AS (SELECT etc.)
c.       TEMP Table – Stores intermediate results in temporary storage within the database during the session.  The database will drop all temporary tables once the session ends.  Can be accessed in the same ways as a regular table until the session ends.  
The # signals New-Table is a temp table.
SELECT
INTO #New-Table

Extract data into a temporary table, perform transformations to store intermediate results that can be used to create permanent tables.  Best to be used in testing, to ensure the table you want to create 
d.      Table – If the queries are complex where a view would cause a long time to be needed to query the view, than a table would likely be better because querying a table is always faster due to the data being persistent and stored in the table after running once.  IE updating a table daily to be accessed by multiple users for different reasons would be faster for daily data.
	Helpful for creating a persistent snapshot of your data.
3.      Describe the differences between different JOINs.
Inner Join - Only the matching rows from each table based on the JOIN Key specified with the ON statement.
LEFT - Return all rows in the left table, and only matching rows in the right table.
RIGHT - Return all rows in the right table, and only the matching rows in the left table.
FULL - Return all ROWS from both tables. 
4.      Write SQL code to extract all columns from the JSON code below:
{"data":{"isSuggested":false,"searchTerm":"customer service","searchPhrase":""},"pageLoadDetails":{},"deviceDetails":{"device":"Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/130.0.0.0 Safari/537.36"},"eventDetails":{"eventName":"div c-tracking-log-dom"}}
5.      Write SQL code to convert the string below to the appropriate data format:
‘2024-02-10 13:01:50 EST’
 
 
Part B. Answer the Tableau related questions below.
1.      When do you decide to use LIVE or EXTRACT data connection?
2.      When do you decide to save the workbook as twb vs. twbx?
3.      Describe a use case with the application of LOD
4.      Describe a case of PARAMETERS and FILTERS to create interactive and dynamic dashboards.
5.      Differentiate between data joining and blending in Tableau, and provide scenarios for their use.
6.      Explain how to implement row-level security and manage user permissions within Tableau
 
 
 
Part C. Build a Tableau Dashboard using the data structure below and answer the questions from the business.
 
Hint: Be creative; add or remove the columns as needed.  You are not required to use all tables or columns. You must build your mock-up data for this practice based on your domain knowledge of customer experience. 
 
The database below includes Table_name: column_name (comments).
·         Customers: customer_id, name, email, created_at, loyalty_tier, age_group, preferred_channel (e.g., mobile, desktop, in-store)
·         Interactions: interaction_id, customer_id, date, channel (e.g., call, email, social media), resolution_status, issue_type, product_category
·         Feedback: feedback_id, interaction_id, rating, feedback_text, sentiment_score, survey_type (e.g., post-interaction, annual survey), feedback_date
·         Agents: agent_id, agent_name, department, hire_date, current_performance_rating, escalation_rate
·         Service_Metrics: metric_id, interaction_id, response_time, resolution_time, first_contact_resolution (boolean), escalation (boolean)
·         Customer_Segments: segment_id, segment_name, criteria (e.g., "high-value repeat buyers"), created_at
·         Promotions: promo_id, promo_name, start_date, end_date, discount_percentage, targeted_segment_id
·         Purchases: purchase_id, customer_id, purchase_date, product_id, amount, promo_applied (boolean), purchase_channel
·         Customer_Lifecycle: lifecycle_id, customer_id, lifecycle_stage (e.g., acquisition, growth, retention), start_date, end_date
Business Questions (Please write SQL to join/blend the data together if needed:
 
1.      What is the average lifetime value (total purchase amount) of customers segmented by loyalty tier and preferred interaction channel. Include details on average interaction count per lifecycle stage.
2.      Identify which promotions resulted in the highest increase in purchase frequency among high-value segments (segment_id criteria = "high-value repeat buyers"). Calculate average purchase frequency pre- and post-promotion for each promotion.
3.       Identify the top 5 agents with the highest average performance rating, broken down by product category and escalation rate. Show each agent’s resolution time and customer rating averages.
4.      Map out a cross-channel journey for a sample segment (e.g., mobile-first users) showing interaction types, average response times, and resolution statuses over multiple touchpoints.
5.      Identify anything you feel would be a good metric/KPI to help the business improve customer service, and explain why. (Optional)
