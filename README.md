# SQL-Data-Cleaning-World-Layoffs
A comprehensive data cleaning project using MySQL to process global layoffs data.
SQL Data Cleaning Project: World Layoffs Dataset
📌 Project Overview
This project focuses on the comprehensive data cleaning of a raw "World Layoffs" dataset using MySQL. The goal was to transform a "messy" raw dataset into a clean, structured format ready for exploratory data analysis (EDA).

🛠️ Tech Stack
Database Management System: MySQL

Tool: MySQL Workbench

Language: SQL

🧹 Data Cleaning Steps
In this project, I implemented a robust multi-step cleaning process:

Removing Duplicates: * Identified duplicate records using ROW_NUMBER() with PARTITION BY across all columns.

Created a staging2 table to securely delete redundant rows, as MySQL does not support direct DELETE operations on CTEs with window functions.

Standardizing Data:

Fixed inconsistent naming (e.g., trimming whitespace and standardizing industry names).

Converted the date column from a string format to a proper DATE type.

Handling Null Values: * Used self-joins to populate missing industry data where information was available in other rows of the same company.

Removing Unnecessary Columns: * Dropped columns that were redundant for the final analysis to optimize performance.

🚀 Key Challenges & Solutions
The "Safe Update" Trap: Encountered and resolved Error 1175 by managing SQL_SAFE_UPDATES settings, demonstrating an understanding of MySQL's safety protocols in a production-like environment.

Complex Deletion Logic: Since MySQL cannot delete from a CTE, I strategically utilized a Staging Table approach to maintain data integrity while removing over 2,000 duplicate entries.
