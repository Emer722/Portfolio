# Overview:

Welcome to my analysis of social inequalities by race in Brazil. This project stems from my personal experience growing up in Brazil, where I witnessed firsthand the inequalities that affect various racial groups. This analysis aims to go deeper into these disparities to understand and highlight that they are not merely stereotypes but are rooted in systemic issues.

The data was sourced from IBGE(Brazilian Institute of Geography and Statistics) which provides multiple tables containing detailed information on quantity, race, salary, and region. Through a series of Python scripts, I explore key questions such as the number of races in Brazil, the salary between races, the house conditions between races, etc.

# The Question:
1.  What are the racial demographics in each region, and what is the percentage distribution of each race?

2.  How has the population of each racial group changed over the years? Which racial group has the largest population?

3.  How do different racial groups compare in terms of financial status? What are the income levels and economic conditions across races?

4.  What is the percentage of homeless people by race? How has this percentage changed over the years?
  
5.  What are the homicide rates by region and race? How have these rates evolved over the years?
   
6.  How do political representation and influence vary by race and region? What is the level of political engagement and power held by different racial groups?

# Tools I Used:
1.  Python: The backbone of my analysis, allowing me to analyze the data and find critical insights. I also used the following Python library:

    •	Pandas Library: This was used to analyze the data.

    •	NumPy: This was used to calculate some parts of the analysis.

2.  Jupyter Notebooks: The tool I used to run my Python scripts which let me easily include my notes and analysis.
  
3.  Visual Studio Code: My go-to for executing my Python scripts.

4.  Power BI: Essential tool for my visualization graphs, for better readability.

# Data Preparation and Cleanup:
In total I gathered 5 tables for my analysis, I am only showing the first one as an example, the rest of the table went through a similar cleaning method:
## Table 1: Distribution of the population by Race and Region (2021 – 2012)
## 1. Reading and Cleaning Data:
•	The function ‘process_population_data’ reads an Excel file containing population distribution data by race or color for different regions and states in Brazil.

•	It drops rows and columns with all NaN values and sets appropriate column names.

•	It drops specific rows that are not needed.

•	It renames columns to English for easier understanding.



