# Overview:

Welcome to my analysis of longevity. In this project, I focus on three key areas. First, I examine life expectancy at birth and at age 60 across all countries, analyzing both the actual values and percentages. Second, I explore how factors like food quality and living conditions impact the longevity of different populations. Lastly, I delve into how various causes of death affect the overall life expectancy of a country, providing insights into the relationship between health and longevity.

This project stems from my interest in understanding health and longevity. I gathered data from reputable sources such as the WHO and FAO, and conducted the analysis using Python for data processing and Power BI for visualization. Through this approach, I aim to provide a comprehensive view of the factors influencing longevity worldwide.

# The Question:

1.  Which countries have the highest life expectancy at birth and at age 60, and which countries have the lowest in both categories?

2.  How has life expectancy at birth and at age 60 increased over the years for both genders? Are the top-ranking and bottom-ranking countries also experiencing an increase in life expectancy?

3.  What is the difference in life expectancy between men and women at birth and at age 60? How has this difference changed over the years?

4.  How do the top and bottom countries in life expectancy at birth and at age 60 compare in terms of food and living conditions? This includes factors such as access to basic drinking water, obesity rates, average protein supply, and minimum dietary energy requirements.

5.  How do the top and bottom countries differ across each category and subcategory of death causes?

6.  How do different causes of death impact life expectancy at age 60 in the top and bottom countries?

7.  What are the leading causes of death in each category for both the top and bottom countries?

# Tools I Used:

1. Pandas Library: This was used to analyze, clean, and manipulate the data.

2. Statistics Library: This was used to perform the necessary calculations for my analysis.

3.  Jupyter Notebooks: Run Python scripts and document the data requirement and cleaning process.
   
4.  Power BI: Build visualization for data storytelling.

# The Analysis:
Combining Python and Power BI this is how I approached each question:

### 1.  Which countries have the highest life expectancy at birth and at age 60, and which countries have the lowest in both categories?
First, I separated the top and bottom countries by identifying the top 30% and bottom 30% in each category, from 2000 to 2021, to improve the analysis. This approach reduced the number of countries in Python, making it more manageable, and then I visualized the results in Power BI.

### Results:

#### At birth:
##### Top:
<img width="1000" alt="1 a" src="https://github.com/user-attachments/assets/bdbc100e-3f6b-40eb-b1d3-36adb77017af">

##### Bottom:
<img width="996" alt="1 b" src="https://github.com/user-attachments/assets/fd626bb1-cebc-4597-9777-738378c62511">

#### At 60:
##### Top:
<img width="1024" alt="1 c" src="https://github.com/user-attachments/assets/0a156173-fddc-4412-85bc-2374aa5693b1">

##### Bottom:
<img width="1018" alt="1 d" src="https://github.com/user-attachments/assets/94c11bdb-c079-4fa1-8a27-d4dfff7246e5">

### Insights:
+ The graph reveals a significant difference in life expectancy between the top and bottom countries, with a gap of **16.45** years at birth and **6.17** years at age 60.

+ The graph also highlights that **Japan** leads in both categories, with the highest life expectancy at birth and at age 60.

### How has life expectancy at birth and at age 60 increased over the years for both genders? Are the top-ranking and bottom-ranking countries also experiencing an increase in life expectancy?
In this analysis, I used Python to calculate the median increase in life expectancy at birth and at age 60, and utilized Power BI for the visualization.

### Results:

#### At birth:
##### Top:
<img width="508" alt="2-a" src="https://github.com/user-attachments/assets/cdf1d1af-a5b1-4e90-be08-33f99d60abff">

##### Bottom:
<img width="510" alt="2 b" src="https://github.com/user-attachments/assets/29e7ef5f-ab8c-40e7-ba4e-98708b838d74">

#### At 60:
##### Top:
<img width="508" alt="2 c" src="https://github.com/user-attachments/assets/2783c579-8756-415e-80e0-29d52a1eca53">

##### Bottom:
<img width="508" alt="2 d" src="https://github.com/user-attachments/assets/49b50e20-6fb1-4f04-9dd4-74d283d201cf">

### Insights:
+ All the top and bottom countries showed an overall increase in life expectancy, with only a slight decline observed in the last two years for both groups.

+ The increase in life expectancy at birth for the top countries is **0.22 years**, while for the bottom countries, it's **0.49 years**. Similarly, the increase in life expectancy at age 60 is **0.16 years** for the top countries and **0.09 years** for the bottom countries.

+ It is evident that the top countries experienced a smaller increase in life expectancy at birth compared to the bottom countries. However, the opposite trend is observed for life expectancy at age 60, where the top countries saw a greater increase than the bottom countries.

### What is the difference in life expectancy between men and women at birth and at age 60? How has this difference changed over the years?
In this analysis, I used Python to perform all the necessary calculations and Power BI for data visualization.

### Results:

#### At birth:
##### Top:
<img width="563" alt="3 a" src="https://github.com/user-attachments/assets/597c8f39-9b56-4682-a4db-ed5c37322fd6">

##### Bottom:
<img width="565" alt="3 b" src="https://github.com/user-attachments/assets/c21accdd-b194-4ed0-8934-62d31580a8a3">

#### At 60:
##### Top:
<img width="569" alt="3 c" src="https://github.com/user-attachments/assets/cef13b2f-6b13-4557-94e3-5b5c21150f6d">

##### Bottom:
<img width="566" alt="3 d" src="https://github.com/user-attachments/assets/b4f38afa-c504-402d-9cbb-811aa5231534">

### Insights:
+ In every category, females have a higher life expectancy than males in both the top and bottom countries. The median difference is **3.66 years** for the top countries and **3 years** for the bottom countries across both categories.

+ For males: the increase in life expectancy at birth for the top countries is **0.29 years**, while for the bottom countries, it's **0.48 years**. Similarly, the increase in life expectancy at age 60 is **0.17 years** for the top countries and **0.13 years** for the bottom countries.

+ For females: The increase in life expectancy at birth for the top countries is **0.22 years**, while for the bottom countries, it's **0.60 years**. Similarly, the increase in life expectancy at age 60 is **0.16 years** for the top countries and **0.11 years** for the bottom countries.

### How do the top and bottom countries in life expectancy at birth and at age 60 compare in terms of food and living conditions? This includes factors such as access to basic drinking water, obesity rates, average protein supply, and minimum dietary energy requirements.








