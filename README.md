# Films Data Analysis Using PostgreSQL and Tableau for Visualization
## Table of Content
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools and Concept Demonstrated](#tools-and-concept-demonstrated)
- [Project Objectives](#project-objectives)
- [Visualization](#visualization)

## Project Overview

This data analysis project is designed to deliver insights into the film industry spanning the years 1916 to 2006. By examining various dimensions, including roles, reviews, personnel, and film datasets, the project aims to retrieve, filter, and analyze data to address practical business questions relevant to the industry. The goal is to provide data-driven insights, enhance understanding of film-related trends and patterns, and showcase proficiency in SQL and Tableau.

## Data Sources
This data is a public data and its not in any form a real-world industry data and its only used for the purpose of learning and showing my data analytic skills.

## Tools and Concept Demonstrated
- SQL
  - Select,From,where,Orderby,Groupby,Having,Table join Aggregate functions:(sum, average, count, Distinct)e.t.c
  - SQL Queries prensentation containing all codes and results [click](https://github.com/lolade-ab/Public_Films_Data_Project/tree/main/Sql%20Queries%20ppt)
- Tableau
  - Creating easy to Understand visualization Dashboard report.


## Project Objectives
- Develop hands-on experience in leveraging SQL for comprehensive data analysis.  
- Utilize SQL queries to extract and analyze data from the "Films data" database.  
- Address real-world business questions through the application of SQL techniques.  
- Present analysis findings in a structured and professional format.

### Films Entity Relationship Diagram(ERD) For Tables in the Dataset
<img width="1310" alt="FILMS ERD FOR DB" src="https://github.com/user-attachments/assets/a01a9842-e85d-4666-971f-d868ca6f992a">

### Few Key business questions that guided the development of a visualization dashboard

- How many films in the database were released in each country, and what are the top five countries?
```sql
SELECT COUNT(title), Country
FROM films
GROUP BY country
ORDER BY count DESC
LIMIT 5;
```

- Which country has made the highest profit from movies?
```sql
SELECT 
(gross - budget) AS profit, 
FROM films
WHERE (gross - budget) IS NOT NULL
ORDER BY (gross - budget);
```

- Which movie made the highest profit in the 21st century
```sql
SELECT 
title,(gross - budget) AS profit, release_year
FROM films
WHERE (gross - budget) IS NOT NULL
AND release_year >1999
ORDER BY profit DESC;
```
- SQL Queries prensentation containing all codes and results [click](https://github.com/lolade-ab/Public_Films_Data_Project/tree/main/Sql%20Queries%20ppt)
## Visualization

[<img width="1188" alt="Films dashboard" src="https://github.com/user-attachments/assets/76b23e29-6362-473f-883c-41fe5580d646">](https://github.com/lolade-ab/Public_Films_Data_Project/blob/main/Images/Films%20dashboard.png)

## Insights
Disclaimer: This dataset is a public data and NOT an active industry data.

1. This film data contains movies recorded from 1916 to 2016.
2. The country with the highest movis releases is the USA with 3750 movies.
3. Movie that made the highest profit from 1916 to 2016 is "The Avengers" and in the year 2012.
4. Movie with the highest number of critic is "The Conformist"
5. Number of people who are currently still alive are 5371
6. Top actor and director in the time frame of 1916 to 2016 is "Robert de Niro" and "Morgan Freeman"
7. The year 2009 has the highest release movie with movie count of 260.

