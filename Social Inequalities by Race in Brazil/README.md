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
1. Pandas Library: This was used to analyze, clean, and manipulate the data.

2.  Jupyter Notebooks: Run Python scripts and document the data requirement and cleaning process 
   
3.  Power BI: Build visualization for data storytelling

# Data Preparation and Cleanup:
In total I gathered 5 tables for my analysis, the data preparation and cleanup detailed steps are in my notebook.

# The Analysis:
Combining Python and Power BI this is how I approached each question:
### 1.  What are the racial demographics in each region, and what is the percentage distribution of each race?
To find the answer, I filtered the data by State and Race. Then, I calculated the total population and its percentage. Finally, I imported the resulting table into Power BI to create the graph.

View my notebook with detailed steps here: [Social Inequalities by Race in Brazil/Distribution by Race.ipynb]
(https://github.com/Emer722/Portfolio/blob/main/Social%20Inequalities%20by%20Race%20in%20Brazil/Demographic%20Distribution%20by%20Race.ipynb)

### Results:

<img width="709" alt="1" src="https://github.com/user-attachments/assets/39d1c907-daf3-44f1-83ed-8cb69f084cfb">


<img width="709" alt="2" src="https://github.com/user-attachments/assets/9ef5ec5d-f649-41fd-b191-cb5516edc577">

### Insights:

+	In Brazil, the majority of the population across all regions is mixed-race, with particularly high concentrations in the North (56.3%), Northeast (74.5%), and Central-West (63.6%) regions.

+	The white population constitutes the second largest demographic group in the country. Notably, it has significant concentrations in the South (75.6%) and Southeast (51.2%), where it surpasses the mixed-race population.

+	The black population represents the minority demographic, with small percentages across all regions.


### 2. How has the population of each racial group changed over the years? Which racial group has the largest population?
The analysis was conducted using Power BI, eliminating the need for Python in this case. Power BI efficiently sums the population of each racial group across all regions and years. -- take  the adjective or adverb words - efficiently. 

### Results:

<img width="624" alt="3" src="https://github.com/user-attachments/assets/67f8a7d3-15e3-463d-99db-05317a986a26">

### Insights:

+	Over the last decade (2012 – 2021), the demographic composition in Brazil has remained relatively stable, with the mixed-race population being the largest group, followed by the white population, and the black population as the minority.

+	The graph clearly illustrates the significant disparity between the black population and the other racial groups, highlighting a substantial gap.

View my notebook with detailed steps here: [Social Inequalities by Race in Brazil/Distribution by Race.ipynb]
(https://github.com/Emer722/Portfolio/blob/main/Social%20Inequalities%20by%20Race%20in%20Brazil/Demographic%20Distribution%20by%20Race.ipynb)

### 3. How do different racial groups compare in terms of financial status? What are the income levels and economic conditions across races?
+ This analysis focuses on the salary data categorized by race and region in Brazil, specifically examining formal employment. In this context, formal employment refers to jobs that are officially recognized by the government, typically offering job security, benefits, and compliance with labor laws.
 
+ To provide a clearer picture, we filtered the dataset to include only formal employment data.

+	Next, I grouped the data by year, race, and employment type, and calculated the median salary per month for each group. The resulting data was sorted in descending order by year, providing a clear view of the median salary trends from 2021 to 2012.

### Results:

![image](https://github.com/user-attachments/assets/04186984-6884-4b3d-a36b-2cfcc04da26f)


![image](https://github.com/user-attachments/assets/eff4dc29-10c6-4a6a-beca-caaa09350228)

### Insights:

+	The analysis reveals that the white population consistently has the highest average salary across all regions, with an average of approximately R$ 1,500 in each region. In contrast, the financial situation for mixed-race and black individuals is nearly identical in 2021.

+	To determine whether this financial advantage for the white race was a trend specific to 2021 or a consistent pattern, I extended the analysis to cover the period from 2012 to 2021. The results show that the white population continues to have an average salary that is R$ 1,200 higher than that of mixed-race and black individuals over the decade.

View my notebook with detailed steps here: [Social Inequalities by Race in Brazil/Financial Comparison Among Races.ipynb](https://github.com/Emer722/Portfolio/blob/main/Social%20Inequalities%20by%20Race%20in%20Brazil/Financial%20Comparison%20Among%20Races.ipynb)


### 4. What is the percentage of homeless people by race? How has this percentage changed over the years?
+	This analysis examines the proportion of homeless individuals in Brazil, categorized by race and region. It aims to provide insights into the housing situation of different racial groups across various regions, highlighting disparities and revealing how well each group is faring in terms of stable housing.

+	Next, I will present the percentage of homeless individuals categorized by race across different years. This analysis aims to identify any significant challenges faced by specific racial groups over the past decade.

### Results:

![image](https://github.com/user-attachments/assets/04ae8862-7b9c-4310-9685-3f99006f3421)

![image](https://github.com/user-attachments/assets/dffc9ced-7d39-4fba-8870-6de5439e25fc)

### Insights:
+	The analysis of the proportion of homeless individuals by race and region shows that, overall, the distribution among racial groups is quite balanced. However, there are notable exceptions: white individuals are disproportionately represented in the South and Central West regions, while the percentages of black and mixed-race individuals are nearly identical.

+ In the final analysis, I compared homelessness rates from 2016 to 2019. As anticipated, white individuals have a lower proportion of homelessness compared to black and mixed-race individuals, averaging around 8% less. Additionally, the proportions of homelessness among black and mixed-race individuals are almost identical. This indicates that black and mixed-race populations experience significantly more challenging housing conditions compared to their white counterparts.

View my notebook with detailed steps here: [Social Inequalities by Race in Brazil/Homelessness by Race.ipynb](https://github.com/Emer722/Portfolio/blob/main/Social%20Inequalities%20by%20Race%20in%20Brazil/Homelessness%20by%20Race.ipynb)

### 5. What are the homicide rates by region and race? How have these rates evolved over the years?
+	This analysis focuses on assessing the safety and living conditions of different racial groups by examining homicide case quantity over time. By evaluating how each racial group is affected by violence and how these rates have evolved, we can gain insights into the safety and quality of life experienced by these communities.

+ The analysis of homicide case quantities alone is insufficient because the populations of the three racial groups differ. Therefore, I also calculated the homicide rate for each racial group over the years to account for these population differences and provide a more accurate comparison.

### Results:

![image](https://github.com/user-attachments/assets/0edbe492-5410-46ce-87e0-6d503063f2c9)

![image](https://github.com/user-attachments/assets/4a0ae362-da3f-4335-982f-64053d5a8c7a)

### Insights:
+	From the homicide case graph, it is evident that the mixed-race group has the highest number of homicide cases, surpassing both the white and black racial groups. While the white population also has more homicide cases compared to the black population, this does not necessarily imply that the black population is in a safer condition. To obtain a clearer picture, it is crucial to examine the homicide rate, which accounts for differences in population sizes.

+ Upon reviewing the homicide rate graph, we see that the mixed-race group continues to lead in terms of homicide rate. This is because the mixed-race and white populations are relatively similar in size. Additionally, the black population has a higher homicide rate compared to the white population. Consequently, the data suggests that the white population experiences the safest living conditions compared to the other racial groups.

View my notebook with detailed steps here: [Social Inequalities by Race in Brazil/Homicide Rates by Region and Race.ipynb](https://github.com/Emer722/Portfolio/blob/main/Social%20Inequalities%20by%20Race%20in%20Brazil/Homicide%20Rates%20by%20Region%20and%20Race.ipynb)

### 6. How do political representation and influence vary by race and region? What is the political engagement and power held by different racial groups?
+	In this analysis, I examined how different racial groups, including East Asian and Native races newly added to the dataset by the IBGE (Brazilian Institute of Geography and Statistics), influence political dynamics(Mayor and City Council). Specifically, I investigated the distribution of political power among various regions and racial groups.

### Results:

![image](https://github.com/user-attachments/assets/737c367b-f61f-4f0c-aa43-dc56a0863182)

![image](https://github.com/user-attachments/assets/2a49c7b9-ab3e-4496-9326-fe779b419770)

### Insights:
+	The white race generally holds a dominant position across most regions(Mayor), in the North and Northeast where the mixed race is more prominent. In the North, there is a significant disparity in population size, with mixed-race individuals comprising 74.5% and whites 18%. Similarly, in the Northeast, mixed-race individuals make up 63.6% of the population, compared to 25% for whites. However, in the Central-West region, despite a higher proportion of mixed-race individuals, the white race remains superior in terms of overall numbers.

+	In Brazil, the mixed-race population generally holds a dominant position in city councils across most regions, particularly in the Northeast, North, and Central-West. In contrast, the white race shows a clear advantage in the South and Southeast. Despite the predominance of mixed-race individuals in city councils, the mayor-council system in Brazil gives the mayor significant executive powers. The city council, while influential in approving budgets and overseeing the mayor, cannot fully offset the political influence held by the white population due to their superior numbers in mayoral positions. Therefore, white race have more influence in the political part.

View my notebook with detailed steps here: [Social Inequalities by Race in Brazil/Political Influence by Race and Region.ipynb](https://github.com/Emer722/Portfolio/blob/main/Social%20Inequalities%20by%20Race%20in%20Brazil/Political%20Influence%20by%20Race%20and%20Region.ipynb)

# Conclusion:
+	This exploration of social inequalities by race in Brazil provided several insights. Although I was aware of racial inequalities from my education, I had never delved deeply into the data to understand their manifestation. The results highlight regional disparities in Brazil, illustrating why some areas are less affluent compared to others. Additionally, the analysis revealed that white individuals tend to have superior financial status, housing conditions, safety, and political influence. This project can be valuable to policymakers, researchers, and advocates by providing data-driven evidence to inform strategies aimed at addressing racial inequalities and improving socio-economic conditions across different regions.
