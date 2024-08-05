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
### 1. Reading and Cleaning Data:
+	The function ‘process_population_data’ reads an Excel file containing population distribution data by race or color for different regions and states in Brazil.

+	It drops rows and columns with all NaN values and sets appropriate column names.

+	It drops specific rows that are not needed.

+	It renames columns to English for easier understanding.

```ruby
import pandas as pd
import numpy as np

file_path = 'C:\\Users\\Emerson Wu Li\\Desktop\\Files Para Social... Project\\Tabela 1.1 (Pop_Geo).xls'

df_Distribuição_etária_da_população_por_cor_ou_raça_segundo_regioes = pd.read_excel(file_path, sheet_name = '2021')
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

```
### 2. Mapping Regions and Reshaping Data:
+	The code creates a dictionary ‘Region’ to map each state to its respective region in Brazil.

+	It adds two new columns, ‘Region’ and’ State’, to the DataFrame based on the values in column ‘r’.

+ Data Frame is reshaped using the 'melt' function to have a long format where each row represents a percentage of a specific race or color in a region or state.

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
+	It adjusts the population quantities to ensure consistency across regions.

+	It rounds the final population quantities and retains only the relevant columns.
  
+	I also needed to correct the values because I initially misinterpreted the percentages from the table.

```ruby
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
```
### 4. Combining Data For Multiple Years:
+ The function ‘combine_data’ combines the population data for multiple years by calling ‘process_population_data’ for each year and concatenating the results into a single Data Frame.
  
+ I did this after cleaning the Data Frame for the year 2021.

+ The resulting Data Frame ‘df_Distribution_population_Region’ contains the cleaned and processed population data, ready for analysis and reporting.

```ruby
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
```
# The Analysis:
Combining Python and Power BI this is how I approached each question:
### 1.  What are the racial demographics in each region, and what is the percentage distribution of each race?
To find the answer, I filtered the data by State and Race. Then, I calculated the total population and its percentage. Finally, I imported the resulting table into Power BI to create the graph.

View my notebook with detailed steps here: Table 1.1.ipynb

