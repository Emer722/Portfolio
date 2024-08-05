# Overview:

Welcome to my analysis of social inequalities by race in Brazil. This project stems from my personal experience growing up in Brazil, where I witnessed firsthand the inequalities that affect various racial groups. This analysis aims to go deeper into these disparities to understand and highlight that they are not merely stereotypes but are rooted in systemic issues.

The data was sourced from IBGE(Brazilian Institute of Geography and Statistics) which provides multiple tables containing detailed information on quantity, race, salary, and region. Through a series of Python scripts, I explore key questions such as the number of races in Brazil, the salary between races, the house conditions between races, etc.

# The Question:
1.  What are the racial demographics in each region, and what is the percentage distribution of each race?
 -- 
2.  How has the population of each racial group changed over the years? Which racial group has the largest population?
-- from 3. stalks about the racial issue.
3.  How do different racial groups compare in terms of financial status? What are the income levels and economic conditions across races?

4.  What is the percentage of homeless people by race? How has this percentage changed over the years?
  
5.  What are the homicide rates by region and race? How have these rates evolved over the years?
   
6.  How do political representation and influence vary by race and region? What is the level of political engagement and power held by different racial groups?

# Tools I Used:
1.  Python: (NOT NEEDED - LINGUICA)The backbone of my analysis, allowing me to analyze the data and find critical insights. I also used the following Python library:
-- which one to use for cleaning and manipulating data ?
    •	Pandas Library: This was used to analyze the data.

    •	NumPy: This was used to calculate some parts of the analysis. -- some parts -> especify. Otherwise is vague

2.  Jupyter Notebooks: The tool I used to run my Python scripts which let me easily include my notes and analysis. -> Run python scripts and document the data requiremenet and cleaning process 
  
3.  Visual Studio Code: My go-to for executing my Python scripts. either choose vs code or jupyter. You don't need both 

4.  Power BI: Essential tool for my visualization graphs, for better readability. -> Build visualization for data storytelling

# Data Preparation and Cleanup:
In total I gathered 5 tables for my analysis, I am only showing the first one as an example, the rest of the table went through a similar cleaning method:

-> All of the codes should be in the code files. Put a """ """ comment at the start of each function that explains the function's input, output. And something else ( search how to annotate a function). 
To explain each line of code, or parts of it, write #comment on top of it. 


## Table 1: Distribution of the population by Race and Region (2021 – 2012)
### 1. Reading and Cleaning Data:
+	The function ‘process_population_data’ reads an Excel file containing population distribution data by race or color for different regions and states in Brazil.

+	It drops rows and columns with all NaN values and sets appropriate column names.

+	It drops specific rows that are not needed. -> especify which rows, why they are not needed. Something like Dropped rows that contains headers, or whitespaces

+	It renames columns to English for easier understanding.

```ruby
import pandas as pd
import numpy as np

file_path = 'C:\\Users\\Emerson Wu Li\\Desktop\\Files Para Social... Project\\Tabela 1.1 (Pop_Geo).xls'

-- name your variables all lower case. And make them shorter. Try to make them as descriptive as possible with fewer words. 
df_Distribuição_etária_da_população_por_cor_ou_raça_segundo_regioes = pd.read_excel(file_path, sheet_name = '2021')
df_cleaned_r = df_Distribuição_etária_da_população_por_cor_ou_raça_segundo_regioes.copy()
df_cleaned_r = df_cleaned_r.dropna(how = 'all')
df_cleaned_r.columns = df_cleaned_r.iloc[2]

rows_to_drop = [2, 3, 4, 5, 39]
df_cleaned_r = df_cleaned_r.drop(rows_to_drop)
df_cleaned_r.columns.values[1] = 'Quantity'
df_cleaned_r.columns.values[0] = 'r'

-- underline btw names and r if they should be read separatedly
new_column_namesr = {
    'Branca': 'White',
    'Preta': 'Black',
    'Parda': 'Mixed',
    'Preta ou parda': 'Black or Mixed',
    'Quantity': 'Quantity1(10^3)' -- try to put a comment here explaining why you put in this form. 
}

df_cleaned_r = df_cleaned_r.rename(columns = new_column_namesr)

```
### 2. Mapping Regions and Reshaping Data:
+	The code creates a dictionary ‘Region’ to map each state to its respective region in Brazil.

+	It adds two new columns, ‘Region’ and’ State’, to the DataFrame based on the values in column ‘r’. r is race right? So tell the reader in the first time you mention about r

+ Data Frame is reshaped using the 'melt' function to have a long format where each row represents a percentage of a specific race or color in a region or state. -- what is a   long format


```ruby
Region = {
    'Norte': 'Norte', 'Rondônia': 'Norte', 'Acre': 'Norte', 'Amazonas': 'Norte', 'Roraima': 'Norte', 'Pará': 'Norte', 'Amapá': 'Norte', 'Tocantins': 'Norte',
    'Nordeste': 'Nordeste', 'Maranhão': 'Nordeste', 'Piauí': 'Nordeste', 'Ceará': 'Nordeste', 'Rio Grande do Norte': 'Nordeste', 'Paraíba': 'Nordeste', 'Pernambuco': 'Nordeste', 'Alagoas': 'Nordeste', 'Sergipe': 'Nordeste', 'Bahia': 'Nordeste',
    'Sudeste': 'Sudeste', 'Minas Gerais': 'Sudeste', 'Espírito Santo': 'Sudeste', 'Rio de Janeiro': 'Sudeste', 'São Paulo': 'Sudeste',
    'Sul': 'Sul', 'Paraná': 'Sul', 'Santa Catarina': 'Sul', 'Rio Grande do Sul': 'Sul',
    'Centro-Oeste': 'Centro-Oeste', 'Mato Grosso do Sul': 'Centro-Oeste', 'Mato Grosso': 'Centro-Oeste', 'Goiás': 'Centro-Oeste', 'Distrito Federal': 'Centro-Oeste'
}


df_cleaned_r['Region'] = df_cleaned_r['r'].apply(lambda x: Region[x] if x in Region else x)
df_cleaned_r['State'] = df_cleaned_r['r'].apply(lambda x: x if x in Region else '')
df_cleaned_r = df_cleaned_r.drop(columns = 'r')


df_cleaned_r = df_cleaned_r.melt(id_vars=['Region', 'State', 'Quantity1(10^3)'], 
                    value_vars = ['White', 'Black', 'Mixed', 'Black or Mixed'],  
                    value_name ='Percentage')
    
df_Distribution_population_Region = df_cleaned_r.copy()
df_Distribution_population_Region['Year'] = 2021
```
### 3. Updating and Calculating Population Quantities:
+	It adjusts the population quantities to ensure consistency across regions. -- what do you mean? It adjusts the units of measure? It seems that you adjusted the scale?

+	It rounds the final population quantities and retains only the relevant columns. 
  
+	I also needed to correct the values because I initially misinterpreted the percentages from the table. How did you correct the values? What you misterpreted about the percentages? What are the corrected versions? ( what's the result?)

```ruby
df_Distribution_population_Region['Quantity(10^3)'] = (df_Distribution_population_Region['Quantity1(10^3)'] * df_Distribution_population_Region['Percentage']) / 100

columns_to_drop = ['Quantity1(10^3)', 'Percentage']
df_Distribution_population_Region = df_Distribution_population_Region.drop(columns = columns_to_drop)


region_totals = df_Distribution_population_Region.groupby(['Region', 'Year'])['Quantity(10^3)'].sum().reset_index()
region_totals = region_totals.rename(columns={'Quantity(10^3)': 'Region_Total'})


df_Distribution_population_Region = pd.merge(df_Distribution_population_Region, region_totals, on=['Region', 'Year'])

-- updated_qunatity = lower case 
df_Distribution_population_Region['Updated_Quantity'] = df_Distribution_population_Region['Region_Total'] * (df_Distribution_population_Region['Quantity(10^3)'] / df_Distribution_population_Region.groupby(['Region', 'Year'])['Quantity(10^3)'].transform('sum'))

df_Distribution_population_Region['Quantity(10^3)'] = df_Distribution_population_Region['Updated_Quantity']

df_Distribution_population_Region = df_Distribution_population_Region.drop(columns=['Region_Total', 'Updated_Quantity'])
df_Distribution_population_Region['Quantity(10^3)'] = df_Distribution_population_Region['Quantity(10^3)'].round().astype(int) -- you can just do astype(int) that it will round up for you, i think 
df_Distribution_population_Region = df_Distribution_population_Region.rename(columns = {4 : 'Race'})
```
### 4. Combining Data For Multiple Years:
+ The function ‘combine_data’ combines the population data for multiple years by calling ‘process_population_data’ for each year and concatenating the results into a single Data Frame.
  
+ I did this after cleaning the Data Frame for the year 2021.

+ The resulting Data Frame ‘df_Distribution_population_Region’ contains the cleaned and processed population data, ready for analysis and reporting.

```ruby

-- comment here that this is the function anterior , so reader doesn't misunderstand that it's a new function
def process_population_data(file_path, sheet_name):
    df_Distribuição_etária_da_população_por_cor_ou_raça_segundo_regioes = pd.read_excel(file_path, sheet_name = sheet_name)
    df_cleaned_r = df_Distribuição_etária_da_população_por_cor_ou_raça_segundo_regioes.copy()
    df_cleaned_r = df_cleaned_r.dropna(how = 'all')
    df_cleaned_r.columns = df_cleaned_r.iloc[2]

    rows_to_drop = [2, 3, 4, 5, 39]
    df_cleaned_r = df_cleaned_r.drop(rows_to_drop)
    df_cleaned_r.columns.values[1] = 'Quantity'
    df_cleaned_r.columns.values[0] = 'r'

    new_column_namesr = {
        'Branca': 'White',
        'Preta': 'Black',
        'Parda': 'Mixed',
        'Preta ou parda': 'Black or Mixed',
        'Quantity': 'Quantity1(10^3)'
    }

    df_cleaned_r = df_cleaned_r.rename(columns = new_column_namesr)



    Region = {
        'Norte': 'Norte', 'Rondônia': 'Norte', 'Acre': 'Norte', 'Amazonas': 'Norte', 'Roraima': 'Norte', 'Pará': 'Norte', 'Amapá': 'Norte', 'Tocantins': 'Norte',
        'Nordeste': 'Nordeste', 'Maranhão': 'Nordeste', 'Piauí': 'Nordeste', 'Ceará': 'Nordeste', 'Rio Grande do Norte': 'Nordeste', 'Paraíba': 'Nordeste', 'Pernambuco': 'Nordeste', 'Alagoas': 'Nordeste', 'Sergipe': 'Nordeste', 'Bahia': 'Nordeste',
        'Sudeste': 'Sudeste', 'Minas Gerais': 'Sudeste', 'Espírito Santo': 'Sudeste', 'Rio de Janeiro': 'Sudeste', 'São Paulo': 'Sudeste',
        'Sul': 'Sul', 'Paraná': 'Sul', 'Santa Catarina': 'Sul', 'Rio Grande do Sul': 'Sul',
        'Centro-Oeste': 'Centro-Oeste', 'Mato Grosso do Sul': 'Centro-Oeste', 'Mato Grosso': 'Centro-Oeste', 'Goiás': 'Centro-Oeste', 'Distrito Federal': 'Centro-Oeste'
    }


    df_cleaned_r['Region'] = df_cleaned_r['r'].apply(lambda x: Region[x] if x in Region else x)
    df_cleaned_r['State'] = df_cleaned_r['r'].apply(lambda x: x if x in Region else '')
    df_cleaned_r = df_cleaned_r.drop(columns = 'r')


    df_cleaned_r = df_cleaned_r.melt(id_vars=['Region', 'State', 'Quantity1(10^3)'], 
                    value_vars = ['White', 'Black', 'Mixed', 'Black or Mixed'],  
                    value_name ='Percentage')

    return df_cleaned_r

    

def combine_data(file_path, years):
    combined_df = pd.DataFrame()
    
    for year in years:
        sheet_name = str(year)
        df_year = process_population_data(file_path, sheet_name)
        df_year['Year'] = year
        combined_df = pd.concat([combined_df, df_year], ignore_index=True)
    
    return combined_df


file_path = 'C:\\Users\\Emerson Wu Li\\Desktop\\Files Para Social... Project\\Tabela 1.1 (Pop_Geo).xls'
years = [2021, 2020, 2019, 2018, 2017, 2016, 2015, 2014, 2013, 2012]
df_Distribution_population_Region = combine_data(file_path, years)

df_Distribution_population_Region['Quantity(10^3)'] = (df_Distribution_population_Region['Quantity1(10^3)'] * df_Distribution_population_Region['Percentage']) / 100
columns_to_drop = ['Quantity1(10^3)', 'Percentage']
df_Distribution_population_Region = df_Distribution_population_Region.drop(columns = columns_to_drop)

region_totals = df_Distribution_population_Region.groupby(['Region', 'Year'])['Quantity(10^3)'].sum().reset_index()
region_totals = region_totals.rename(columns={'Quantity(10^3)': 'Region_Total'})


df_Distribution_population_Region = pd.merge(df_Distribution_population_Region, region_totals, on=['Region', 'Year'])

df_Distribution_population_Region['Updated_Quantity'] = df_Distribution_population_Region['Region_Total'] * (df_Distribution_population_Region['Quantity(10^3)'] / df_Distribution_population_Region.groupby(['Region', 'Year'])['Quantity(10^3)'].transform('sum'))

df_Distribution_population_Region['Quantity(10^3)'] = df_Distribution_population_Region['Updated_Quantity']

df_Distribution_population_Region = df_Distribution_population_Region.drop(columns=['Region_Total', 'Updated_Quantity'])
df_Distribution_population_Region['Quantity(10^3)'] = df_Distribution_population_Region['Quantity(10^3)'].round().astype(int)
df_Distribution_population_Region = df_Distribution_population_Region.rename(columns = {4 : 'Race'})


-- prob show the final cleaned table, the head of it. And explain how each field would be used for analysis. 
```
# The Analysis:
Combining Python and Power BI this is how I approached each question:
### 1.  What are the racial demographics in each region, and what is the percentage distribution of each race?
To find the answer, I filtered the data by State and Race. Then, I calculated the total population and its percentage. Finally, I imported the resulting table into Power BI to create the graph.

View my notebook with detailed steps here: Table 1.1.ipynb

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

View my notebook with detailed steps here:

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

View my notebook with detailed steps here:

### 4. What is the percentage of homeless people by race? How has this percentage changed over the years?
+	This analysis examines the proportion of homeless individuals in Brazil, categorized by race and region. It aims to provide insights into the housing situation of different racial groups across various regions, highlighting disparities and revealing how well each group is faring in terms of stable housing.

+	Next, I will present the percentage of homeless individuals categorized by race across different years. This analysis aims to identify any significant challenges faced by specific racial groups over the past decade.

### Results:

![image](https://github.com/user-attachments/assets/04ae8862-7b9c-4310-9685-3f99006f3421)

![image](https://github.com/user-attachments/assets/dffc9ced-7d39-4fba-8870-6de5439e25fc)

### Insights:
+	The analysis of the proportion of homeless individuals by race and region shows that, overall, the distribution among racial groups is quite balanced. However, there are notable exceptions: white individuals are disproportionately represented in the South and Central West regions, while the percentages of black and mixed-race individuals are nearly identical.

+ In the final analysis, I compared homelessness rates from 2016 to 2019. As anticipated, white individuals have a lower proportion of homelessness compared to black and mixed-race individuals, averaging around 8% less. Additionally, the proportions of homelessness among black and mixed-race individuals are almost identical. This indicates that black and mixed-race populations experience significantly more challenging housing conditions compared to their white counterparts.

View my notebook with detailed steps here:

### 5. What are the homicide rates by region and race? How have these rates evolved over the years?
+	This analysis focuses on assessing the safety and living conditions of different racial groups by examining homicide case quantity over time. By evaluating how each racial group is affected by violence and how these rates have evolved, we can gain insights into the safety and quality of life experienced by these communities.

+ The analysis of homicide case quantities alone is insufficient because the populations of the three racial groups differ. Therefore, I also calculated the homicide rate for each racial group over the years to account for these population differences and provide a more accurate comparison.

### Results:

![image](https://github.com/user-attachments/assets/0edbe492-5410-46ce-87e0-6d503063f2c9)

![image](https://github.com/user-attachments/assets/4a0ae362-da3f-4335-982f-64053d5a8c7a)

### Insights:
+	From the homicide case graph, it is evident that the mixed-race group has the highest number of homicide cases, surpassing both the white and black racial groups. While the white population also has more homicide cases compared to the black population, this does not necessarily imply that the black population is in a safer condition. To obtain a clearer picture, it is crucial to examine the homicide rate, which accounts for differences in population sizes.

+ Upon reviewing the homicide rate graph, we see that the mixed-race group continues to lead in terms of homicide rate. This is because the mixed-race and white populations are relatively similar in size. Additionally, the black population has a higher homicide rate compared to the white population. Consequently, the data suggests that the white population experiences the safest living conditions compared to the other racial groups.

View my notebook with detailed steps here:

### 6. How do political representation and influence vary by race and region? What is the political engagement and power held by different racial groups?
+	In this analysis, I examined how different racial groups, including East Asian and Native races newly added to the dataset by the IBGE (Brazilian Institute of Geography and Statistics), influence political dynamics(Mayor and City Council). Specifically, I investigated the distribution of political power among various regions and racial groups.

### Results:

![image](https://github.com/user-attachments/assets/737c367b-f61f-4f0c-aa43-dc56a0863182)

![image](https://github.com/user-attachments/assets/2a49c7b9-ab3e-4496-9326-fe779b419770)

### Insights:
+	The white race generally holds a dominant position across most regions(Mayor), in the North and Northeast where the mixed race is more prominent. In the North, there is a significant disparity in population size, with mixed-race individuals comprising 74.5% and whites 18%. Similarly, in the Northeast, mixed-race individuals make up 63.6% of the population, compared to 25% for whites. However, in the Central-West region, despite a higher proportion of mixed-race individuals, the white race remains superior in terms of overall numbers.

+	In Brazil, the mixed-race population generally holds a dominant position in city councils across most regions, particularly in the Northeast, North, and Central-West. In contrast, the white race shows a clear advantage in the South and Southeast. Despite the predominance of mixed-race individuals in city councils, the mayor-council system in Brazil gives the mayor significant executive powers. The city council, while influential in approving budgets and overseeing the mayor, cannot fully offset the political influence held by the white population due to their superior numbers in mayoral positions. Therefore, white race have more influence in the political part.

View my notebook with detailed steps here:
