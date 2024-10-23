# Overview:

Welcome to my analysis of longevity. In this project, I focus on three key areas. First, I examine life expectancy at birth and at age 60 across all countries, analyzing both the actual values and percentages. Second, I explore how factors like food quality and living conditions impact the longevity of different populations. Lastly, I delve into how various causes of death affect the overall life expectancy of a country, providing insights into the relationship between health and longevity.

This project stems from my interest in understanding health and longevity. I gathered data from reputable sources such as the WHO and FAO, and conducted the analysis using Python for data processing and Power BI for visualization. Through this approach, I aim to provide a comprehensive view of the factors influencing longevity worldwide.

# The Question:

1.  Which countries have the highest life expectancy at birth and at age 60, and which countries have the lowest in both categories?

2.  How has life expectancy at birth and at age 60 increased over the years for both genders? Are the top-ranking and bottom-ranking countries also experiencing an increase in life expectancy?

3.  What is the difference in life expectancy between men and women at birth and at age 60? How has this difference changed over the years?

4.  How do the top and bottom countries in life expectancy at birth and at age 60 compare in terms of food and living conditions? 

5.  How do the top and bottom countries differ across each category and subcategory of death causes?

6.  How do different causes of death impact life expectancy at age 60 in the top and bottom countries?

7.   What are the leading causes of death in each category for the top 10 and bottom 10 countries?
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

View my notebook with detailed steps here: [Longevity/Life expectancy.ipynb](https://github.com/Emer722/Portfolio/blob/main/Longevity/Life%20expectancy.ipynb)

### How has life expectancy at birth and at age 60 increased over the years for both genders? Are the top-ranking and bottom-ranking countries also experiencing an increase in life expectancy?
In this analysis, I used Python to calculate the median increase in life expectancy at birth and at age 60, and utilized Power BI for the visualization.

### Results:

#### At birth:
##### Top:
<img width="600" alt="2-a" src="https://github.com/user-attachments/assets/cdf1d1af-a5b1-4e90-be08-33f99d60abff">

##### Bottom:
<img width="600" alt="2 b" src="https://github.com/user-attachments/assets/29e7ef5f-ab8c-40e7-ba4e-98708b838d74">

#### At 60:
##### Top:
<img width="600" alt="2 c" src="https://github.com/user-attachments/assets/2783c579-8756-415e-80e0-29d52a1eca53">

##### Bottom:
<img width="600" alt="2 d" src="https://github.com/user-attachments/assets/49b50e20-6fb1-4f04-9dd4-74d283d201cf">

### Insights:
+ All the top and bottom countries showed an overall increase in life expectancy, with only a slight decline observed in the last two years for both groups.

+ The increase in life expectancy at birth for the top countries is **0.22 years**, while for the bottom countries, it's **0.49 years**. Similarly, the increase in life expectancy at age 60 is **0.16 years** for the top countries and **0.09 years** for the bottom countries.

+ It is evident that the top countries experienced a smaller increase in life expectancy at birth compared to the bottom countries. However, the opposite trend is observed for life expectancy at age 60, where the top countries saw a greater increase than the bottom countries.

View my notebook with detailed steps here: [Longevity/Life expectancy.ipynb](https://github.com/Emer722/Portfolio/blob/main/Longevity/Life%20expectancy.ipynb)

Also here: [Longevity/Analysis.ipynb](https://github.com/Emer722/Portfolio/blob/main/Longevity/Analysis.ipynb)

### What is the difference in life expectancy between men and women at birth and at age 60? How has this difference changed over the years?
In this analysis, I used Python to perform all the necessary calculations and Power BI for data visualization.

### Results:

#### At birth:
##### Top:
<img width="800" alt="3 a" src="https://github.com/user-attachments/assets/597c8f39-9b56-4682-a4db-ed5c37322fd6">

##### Bottom:
<img width="800" alt="3 b" src="https://github.com/user-attachments/assets/c21accdd-b194-4ed0-8934-62d31580a8a3">

#### At 60:
##### Top:
<img width="800" alt="3 c" src="https://github.com/user-attachments/assets/cef13b2f-6b13-4557-94e3-5b5c21150f6d">

##### Bottom:
<img width="800" alt="3 d" src="https://github.com/user-attachments/assets/b4f38afa-c504-402d-9cbb-811aa5231534">

### Insights:
+ In every category, females have a higher life expectancy than males in both the top and bottom countries. The median difference is **3.66 years** for the top countries and **3 years** for the bottom countries across both categories.

+ For males: the increase in life expectancy at birth for the top countries is **0.29 years**, while for the bottom countries, it's **0.48 years**. Similarly, the increase in life expectancy at age 60 is **0.17 years** for the top countries and **0.13 years** for the bottom countries.

+ For females: The increase in life expectancy at birth for the top countries is **0.22 years**, while for the bottom countries, it's **0.60 years**. Similarly, the increase in life expectancy at age 60 is **0.16 years** for the top countries and **0.11 years** for the bottom countries.

View my notebook with detailed steps here: [Longevity/Life expectancy.ipynb](https://github.com/Emer722/Portfolio/blob/main/Longevity/Life%20expectancy.ipynb)

Also here: [Longevity/Analysis.ipynb](https://github.com/Emer722/Portfolio/blob/main/Longevity/Analysis.ipynb)

### How do the top and bottom countries in life expectancy at birth and at age 60 compare in terms of food and living conditions?
In this analysis, I collected factors such as access to basic drinking water, obesity rates, average protein supply, and minimum dietary energy requirements from FAO to evaluate the living conditions in different countries. I used Python for the analysis and Power BI for the visualization.

### Results:

#### Basic drinking water(%):
##### Top:
  <img src="https://github.com/user-attachments/assets/60afee69-081d-4a28-967d-970fadf2f5ac" alt="Image 2" width="1000"/>
</p>

##### Bottom: 
  <img src="https://github.com/user-attachments/assets/d96fcd4f-7e4e-4179-bef0-d5619dfa74c0" alt="Image 2" width="1000"/>
</p>

#### Obesity in adults(%):
##### Top:
   <img src="https://github.com/user-attachments/assets/eae96c25-6220-469a-9cde-3adc96fa0347" alt="Image 2" width="1000"/>
</p>

##### Bottom:
   <img src="https://github.com/user-attachments/assets/f96bcb00-193d-4f6b-aa93-69af067e9997" alt="Image 2" width="1000"/>
</p>

#### Avg. Protein Supply(g/cap/d):
##### Top:
<img src="https://github.com/user-attachments/assets/f463c829-3075-4f18-acba-9ff854cb054e" alt="Image 2" width="1000"/>
</p>

##### Bottom:
<img src="https://github.com/user-attachments/assets/ee0dbfd1-bda2-4081-8739-fe0b2638a9f9" alt="Image 2" width="1000"/>
</p>

#### Min. Dietary Energy Requirement(kcal/cap/d):
##### Top:
<img src="https://github.com/user-attachments/assets/55c58871-9024-48fd-a43e-373be1ae17b1" alt="Image 2" width="1000"/>
</p>

##### Bottom:
<img src="https://github.com/user-attachments/assets/ecb1f81a-8ce6-48b3-9089-4ac4d634454b" alt="Image 2" width="1000"/>
</p>

### Insights:

+ First of all, the top countries outperform in all areas except for obesity, where they face a disadvantage compared to other factors.

+ This disparity could impact longevity, as obesity-related diseases often emerge later in life, typically in one's 50s or 60s. In contrast, for the bottom countries, obesity is less prevalent, likely due to nutritional deficiencies, which may contribute to shorter life spans.

+ There is a **35.5%** difference in access to basic drinking water between the top and bottom countries. The difference in obesity rates is **13.08%**. In terms of average protein supply, there is a gap of **36.9** grams per capita per day, and for minimum dietary energy requirements, the difference is **183.25** kcal per capita per day.

View my notebook with detailed steps here: [Longevity/Food and Agriculture Organization of the United Nations.ipynb](https://github.com/Emer722/Portfolio/blob/main/Longevity/Food%20and%20Agriculture%20Organization%20of%20the%20United%20Nations.ipynb)

### How do the top and bottom countries differ across each category and subcategory of death causes?

The dataset is categorized into three main groups: communicable diseases, noncommunicable diseases, and injuries. Each category is further divided into subcategories, providing more detailed information about specific death causes, for all the death cause analysis is from 2000,2010,2015 and 2021(only years provided by WHO)

I used Python to clean and organize the data by various factors, such as category, subcategory, death cause, gender, and top or bottom countries. After processing and organizing the data, I utilized Power BI to visualize and present the insights.

### Results:
#### Communicable Diseases:
##### Top:
###### Category(%):
<img src="https://github.com/user-attachments/assets/3667bc07-6e4a-4a93-9359-0741c494f897" alt="Image 2" width="1000"/>
</p>

###### Sub-Category(%):
<img width="700" alt="5 cc" src="https://github.com/user-attachments/assets/95117357-a6df-4f10-9359-393674db8b3a">

##### Bottom:
###### Category:
<img src="https://github.com/user-attachments/assets/4f3330b4-4278-4cf0-bc11-600ae63634c3" alt="Image 2" width="1000"/>
</p>

###### Sub-Category:
<img width="700" alt="5 bb" src="https://github.com/user-attachments/assets/8d8c94a7-ffb9-426b-ad9d-1037948dca9b">

#### Injuries:
##### Top:
###### Category:
<img src="https://github.com/user-attachments/assets/0fcb4bb5-771c-4fdf-8db3-3487575ab6e0" alt="Image 2" width="1000"/>
</p>

###### Sub-Category:
<img width="700" alt="5 cc" src="https://github.com/user-attachments/assets/e9dbedce-651a-46e4-9df0-041794cf70fd">

##### Bottom:
###### Category:
<img src="https://github.com/user-attachments/assets/c21901a6-2aa4-4efe-a89b-8f9a8af9a73e" alt="Image 2" width="1000"/>
</p>

###### Sub-Category:
<img width="700" alt="5 dd" src="https://github.com/user-attachments/assets/dd81a0f6-ad71-48b4-bc9c-42cefac372b4">

#### Noncommunicable Diseases:
##### Top:
###### Category:
<img src="https://github.com/user-attachments/assets/2d452931-11ed-4fc2-9ad4-65bc39115f0c" alt="Image 2" width="1000"/>
</p>

###### Sub-Category:
<img width="700" alt="5 ee" src="https://github.com/user-attachments/assets/4a9475e3-f790-4b33-b363-00925d56b3c8">

##### Bottom:
###### Category:
<img src="https://github.com/user-attachments/assets/0e71e820-532b-4ce1-81ae-a3dec0ed46cc" alt="Image 2" width="1000"/>
</p>

###### Sub-Category:
<img width="700" alt="5 ff" src="https://github.com/user-attachments/assets/6fc7ca83-089e-4bc2-ab92-081ac68438dc">

### Insights:
+ In the communicable diseases category, the top countries show significantly lower rates compared to the bottom countries. The injury category displays similar levels for both groups. However, a large disparity is observed in the noncommunicable diseases category, with the top countries having much higher rates. Specifically, there is a **35.99%** difference favoring the bottom countries in communicable diseases, while noncommunicable diseases show a **32.06%** higher rate in the top countries.

+ In the subcategory of communicable diseases, there is a notable contrast between the top and bottom countries. Neonatal conditions are not prevalent in either group. However, in the bottom countries, **Infectious and parasitic diseases** account for **82.17%** of deaths, which is **28.17%** higher than in the top countries. Conversely, in the top countries, the distribution is more balanced, with **infectious and parasitic diseases** accounting for **54%**, while **respiratory infections** make up **44.55%**.

+ In the injury category, there is no significant difference between the top and bottom countries. However, in both groups, unintentional injuries are the leading cause of death, surpassing intentional injuries.

+ The non-communicable diseases category includes a wider range of subcategories, but the key differences between the top and bottom countries lie in the prevalence of **malignant neoplasms (cancers)** and **cardiovascular diseases**. In the top countries, malignant neoplasms account for nearly **50%** of deaths in this category, while cardiovascular diseases make up **29.12%**. In contrast, in the bottom countries, malignant neoplasms represent **29.22%** of deaths, cardiovascular diseases **36.11%**, and digestive diseases stand out with **13.32%**. These are the most prominent causes of death in each group.

+ For the communicable diseases category, I concluded that the higher prevalence of infectious and parasitic diseases in the bottom countries is strongly linked to poor hygiene, limited access to clean water, and inadequate sanitation. Since these countries face significant challenges in accessing clean water and maintaining proper sanitation, they experience a higher burden of these diseases. In contrast, the top countries, with better sanitation and water access, have a lower incidence of infectious and parasitic diseases.

+ In the top countries, cancer is more prevalent than in the bottom countries, largely because cancer risk increases with age. Since these top countries generally have higher life expectancy, cancers are more frequently observed as the leading cause of death within the non-communicable diseases category. In contrast, cardiovascular diseases dominate this category in the bottom countries, primarily due to factors such as poor diet, physical inactivity, and smoking, which can negatively impact health at a younger age. Similarly, digestive diseases also contribute significantly to mortality in these lower-income countries.

View my notebook with detailed steps here: [Longevity/Death_Cause.ipynb](https://github.com/Emer722/Portfolio/blob/main/Longevity/Death_Cause.ipynb)

### How do different causes of death impact life expectancy at age 60 in the top and bottom countries?
In this section, I focused on analyzing the impact of different types of death causes on longevity for individuals aged 60, by examining data for ages 5 to 59. I delved into greater detail, beyond the subcategories, to explore specific death causes. Python was used for data cleaning and analysis, while Power BI was employed for visualization.

The percentage corresponds to each specific category; for instance, in the communicable diseases category, HIV/AIDS accounts for **30.36%** of the total deaths within that category, and similar logic applies to other diseases.

### Results:

#### Communicable Diseases:
##### Top:
<img src="https://github.com/user-attachments/assets/51c3d257-8d06-47ad-82ae-32e06e099cb3" alt="Image 2" width="700"/>
</p>

##### Bottom:
<img src="https://github.com/user-attachments/assets/e5959d98-b28a-4c0a-8ac9-bd3029d76d6b" alt="Image 2" width="700"/>
</p>

#### Injuries:
##### Top:
<img src="https://github.com/user-attachments/assets/77ca0c30-2a69-453f-917b-3f011214d5f3" alt="Image 2" width="700"/>
</p>

##### Bottom:
<img src="https://github.com/user-attachments/assets/97513900-0b64-472f-b642-605e376619fd" alt="Image 2" width="700"/>
</p>

#### Noncommunicable Diseases:
##### Top:
<img src="https://github.com/user-attachments/assets/7e462ff8-a3ee-45ba-838f-6358e3e44059" alt="Image 2" width="700"/>
</p>

##### Bottom:
<img src="https://github.com/user-attachments/assets/b14b882b-5cd5-4385-b10a-b22945e09f79" alt="Image 2" width="700"/>
</p>

### Insights:
+ For the top countries, the three leading death causes in the communicable category are **lower respiratory infections** at **44.24%**, **HIV/AIDS** at **18.88%**, and **other infectious diseases** at **17.58%**. In contrast, for the bottom countries, the leading death causes are **HIV/AIDS** at **30.36%**, **tuberculosis** at **25.23%**, and **lower respiratory infections** at **18%**.

+ In the **Injury category**, for the top countries, the leading death causes are **road injury** at **36%**, **self-harm** at **25.73%**, **other unintentional injuries** at **13%**, and **interpersonal violence** at **10.55%**. For the bottom countries, the leading causes are **road injury** at **35.72%**, **interpersonal violence** at **16.46%**, **other unintentional injuries** at **13%**, and **self-harm** at **12.27%**.

+ In the **noncommunicable category**, the percentage differences between death causes are not as pronounced as in previous categories, but certain causes still stand out. For the top countries, the leading causes of death are **Ischaemic heart disease** at **18.61%**, **Trachea, bronchus, and lung cancers** at **7%**, **breast cancer** at **6.63%**, **stroke** at **5%**, and **colon and rectum cancers** at **4.90%**.

+ In contrast, for the bottom countries, the leading causes of death are **stroke** at **17.5%**, **Ischaemic heart disease** at **12.57%**, **cirrhosis of the liver** at **6%**, and **kidney diseases** at **5.45%**. While these percentages may seem small, it's important to note that this category includes a wide variety of death causes, so even **5%** represents a significant portion of the total deaths.

+ In the **top countries**, deaths from Communicable diseases are relatively low compared to the **bottom countries**. However, **Lower respiratory infections** remain a significant public health concern, being the primary cause of death within this category. In contrast, in the **bottom countries**, **HIV/AIDS** and **Tuberculosis** are the leading causes of death. Limited access to proper treatment and healthcare in these regions significantly affects life expectancy, as these diseases continue to have a major impact on public health.

+ In the **Injury** category, the main difference between the top and bottom countries lies in the leading causes of death. In the top countries, **self-harm** accounts for a higher number of deaths compared to the bottom countries. Conversely, in the bottom countries, **interpersonal violence** leads to more deaths than in the top countries.

+ In the **Noncommunicable category**, the leading causes of death in top countries are predominantly related to **cancer**, supporting my previous conclusion that these factors contribute to prolonged longevity. In contrast, the bottom countries experience higher mortality rates from **stroke**, **cirrhosis of the liver**, and **kidney diseases**, which negatively impact longevity.

View my notebook with detailed steps here: [Longevity/Death_Cause.ipynb](https://github.com/Emer722/Portfolio/blob/main/Longevity/Death_Cause.ipynb)

###  What are the leading causes of death in each category for the top 10 and bottom 10 countries?
In this analysis, I aim to achieve greater precision by minimizing the influence of significant outliers. I will identify the leading causes of death within each sub-category and category. For this purpose, I utilized Python for data cleaning and DataFrame construction, while leveraging Power BI for visualization.

### Results:
In the graphs presented below, the x-axis displays the causes of death, while the sub-categories are listed beneath them. The percentages represent the total death causes within each category, rather than within the sub-categories.

#### Communicable Diseases:
##### Top:
<img width="1000" alt="ct_" src="https://github.com/user-attachments/assets/3d8e9b86-c473-4f95-938c-f49db454abb9">

##### Bottom:
<img width="1000" alt="cb_" src="https://github.com/user-attachments/assets/98c9a123-fd73-49e0-a36f-6092dc0de9d7">

#### Injuries:
##### Top:
<img width="1000" alt="it_" src="https://github.com/user-attachments/assets/d51e3bde-87ec-47cc-9ec0-c4b2ff805490">

##### Bottom:
<img width="1000" alt="ib_" src="https://github.com/user-attachments/assets/2925f3fe-0334-45f5-9f3e-ad6c3bbd262f">

#### Noncommunicable Diseases:
##### Top:
<img width="1000" alt="nt_" src="https://github.com/user-attachments/assets/f39aba7a-cdc7-4f5b-9c74-8236027f1bda">

##### Bottom:
<img width="1000" alt="nb_" src="https://github.com/user-attachments/assets/04e9237a-614b-451f-9f74-1f602d22aa9f">

### Insights:
+ In the Communicable category, the leading diseases for the top countries show minimal variation in their values, with **HIV/AIDS** not ranking as the primary cause in the **infectious and parasitic diseases** sub-category. In contrast, for the bottom countries, **lower respiratory infections** emerge as the leading cause in the **respiratory infectious** sub-category, while **HIV/AIDS** and **Tuberculosis** dominate the **infectious and parasitic diseases** sub-category.

+ In the Injury category, the top countries see **self-harm** rise to account for **50%** of the deaths, making it the leading cause, surpassing **road injury**. Similarly, in the bottom countries, **self-harm** also emerges as the primary cause within the **intentional injuries** sub-category, displacing **interpersonal violence** from its leading position.

+ In the noncommunicable category, there is little change among the top countries compared to the previous analysis. However, for the bottom countries, **ischaemic heart disease** has emerged as the leading cause of death, replacing **stroke**, while the remaining causes remain largely consistent.

+ I conclude that the top 10 countries continue to experience significant issues with suicide, likely due to high levels of pressure in their competitive environments. In the noncommunicable category, the leading causes of death remain consistent, with **cancer** and **heart problems** contributing to prolonged longevity. Conversely, in the bottom 10 countries, **HIV/AIDS** is a leading cause of death, often attributed to a lack of education regarding sexual health. Additionally, there is a lower prevalence of cancer-related diseases in these countries, which can be linked to limited access to healthcare facilities. Consequently, many individuals do not receive timely treatment, preventing them from reaching advanced stages of cancer, which shortens their longevity.

View my notebook with detailed steps here: [Longevity/Death_Cause.ipynb](https://github.com/Emer722/Portfolio/blob/main/Longevity/Death_Cause.ipynb)

Also here: [Longevity/Analysis.ipynb](https://github.com/Emer722/Portfolio/blob/main/Longevity/Analysis.ipynb)

### Conclusion:
