# PwC-Diversity
This data analysis was conducted as part of the PricewaterhouseCooper (PwC) Job Simulation program.

[Overview](#overview)
[Dataset](#dataset)
[Objectives](#objectives)
[Methods](#methods)
[Discovery](#discovery)
[Visualizations](#visualizations)

## Diversity and Inclusion KPIs for Pharma Group 
### Overview
---
This analysis of Pharma Group's employee data was conducted with a focus on understanding diversity and inclusion pattern in the company's hiring and promotion actions.The goal was to measure gender balance at said company.


### Dataset
---
The dataset used in generating this report is the 03 Diversity-Inclusion-Dataset.xlsx obtained from the _PricewaterhouseCooper_ (PWC) Power BI Job Simulation Program. See [Forage](https://www.theforage.com/virtual-experience/a87GpgE6tiku7q3gu/pw-c-switzerland/power-bi-cqxg/introduction) for more.


### Objectives
---
The objective was to generate the following KPIs with a magnified focus on gender:
	1. Hiring Rate
	2. Promotion Pattern (FY21)
	3. Turnover Rate
	4. Performance Rate
	5. Executive Gender Scale
       6. Age Groups

### Methods
---
The following tools were used in the creation of this report.
1. **Microsoft Excel:** For data cleaning and preparation.
       
2. **Microsoft Power BI:**
 * Further Data Processing: including data loading, quality inspection, sorting and transformation.
 * Data Analysis: The following measures were created for an efficient analysis of the data:

  Total #employees that left
  ```DAX
  Employees Leaving = CALCULATE(COUNTA('Pharma Group AG'[FY20 leaver]), 'Pharma Group AG'[FY20 leaver] = "Yes")
  ```

  Total #male employees
  ```DAX
  Male = CALCULATE(DISTINCTCOUNT('Pharma Group AG'[Employee ID]), FILTER('Pharma Group AG','Pharma Group AG'[Gender] = "Male"))
  ```

or

  ```DAX
  Male = CALCULATE(COUNTA('Pharma Group AG'[Gender]), 'Pharma Group AG'[Gender] = "Male")
  ```

  Total #female employees
  ```DAX
  Female = CALCULATE(DISTINCTCOUNT('Pharma Group AG'[Employee ID]), FILTER('Pharma Group AG','Pharma Group AG'[Gender] = "Female"))
  ```

or

  ```DAX
  Female = CALCULATE(COUNTA('Pharma Group AG'[Gender]), 'Pharma Group AG'[Gender] = "Female")
  ```

  Average Performance Rating: Men
  
  ```DAX
  Avg. Rating Men = CALCULATE(AVERAGE('Pharma Group AG'[FY20 Performance Rating]), FILTER('Pharma Group AG', 'Pharma Group AG'[Gender] = "Male"))
  ```

  Average Performance Rating: Women
  
  ```DAX
  Avg. Rating Women = CALCULATE(AVERAGE('Pharma Group AG'[FY20 Performance Rating]), FILTER('Pharma Group AG', 'Pharma Group AG'[Gender] = "Female"))
  ```
  
  Employees Promoted in FY21
  
  ```DAX
  Employees Promoted FY21 = CALCULATE(COUNTA('Pharma Group AG'[Promotion in FY21]), 'Pharma Group AG'[Promotion in FY21] = "Yes")
  ```
  
  %Employees promoted in FY21
  
  ```DAX
  %Employees Promoted FY21 = DIVIDE(CALCULATE(COUNT('Pharma Group AG'[Promotion in FY21]), 'Pharma Group AG'[Promotion in FY21] = "Yes"), CALCULATE(COUNT('Pharma Group AG'[Employee ID]), ALLSELECTED('Pharma Group AG'[Employee ID])))
  ```

  %Female Employees promoted in FY21

  ```DAX
  %Female promoted FY21 = DIVIDE(CALCULATE(COUNT('Pharma Group AG'[Promotion in FY21]), FILTER('Pharma Group AG','Pharma Group AG'[Gender] = "Female")), COUNT('Pharma Group AG'[Promotion in FY21]))
  ```

or
  
  ```DAX
  %Female promoted FY21 = DIVIDE(CALCULATE(COUNTA('Pharma Group AG'[Promotion in FY21]), FILTER('Pharma Group AG','Pharma Group AG'[Gender] = "Female")), COUNTA('Pharma Group AG'[Promotion in FY21]))
  ```

  %Female Hired

  ```DAX
  %Female Hired = DIVIDE(CALCULATE(DISTINCTCOUNT('Pharma Group AG'[Employee ID]), FILTER('Pharma Group AG', 'Pharma Group AG'[Gender] = "Female")), COUNT('Pharma Group AG'[Employee ID]))
  ```

  %Male Hired
  
  ```DAX
  %Male Hired = DIVIDE(CALCULATE(DISTINCTCOUNT('Pharma Group AG'[Employee ID]), FILTER('Pharma Group AG', 'Pharma Group AG'[Gender] = "Male")), COUNT('Pharma Group AG'[Employee ID]))
  ```

  %Turnover
  
  ```DAX
  %Turnover = DIVIDE(CALCULATE(DISTINCTCOUNT('Pharma Group AG'[Employee ID]), FILTER('Pharma Group AG', 'Pharma Group AG'[FY20 leaver] = "Yes")), DIVIDE(CALCULATE(DISTINCTCOUNT('Pharma Group AG'[Employee ID]), FILTER('Pharma Group AG', 'Pharma Group AG'[In base group for turnover FY20] = "Y")) + CALCULATE(DISTINCTCOUNT('Pharma Group AG'[Employee ID]), FILTER('Pharma Group AG', NOT 'Pharma Group AG'[Department @01.07.2020] = BLANK())), 2))![image](https://github.com/user-attachments/assets/b723e75b-0972-4024-9e42-530c366d40f1)
  ```


 * Data Visualization: A diverse range of visualization tools including Cards, Ribbon, Donut, Column, Line, Stacked Area and Bar Charts; were used to visually bring these metrics to life.

3. **GitHub:** For portfolio building and communication.


### Discovery
---
The following was discovered:
 * Junior Officers made up the highest number of employees hired in the fiscal year 2020; 53.4% were female.
 * A total number of 16 employees were hired into executive postions with just 12.5% being female.
 * In sum, the ratio of male to female hires was 59:41 respectively.
 * 56.02% of employees promoted in the fiscal year 2021 were male.
 * Before promotions in FY 21, the average time employees spent on the job was 2.35 years.
 * 47 employees responsible for 10.06% of company's turnover, left the job in FY20; 26 males and 21 females.
 * The average rating of female employees was 2.11 while the males was 2.21 employees.
 * 3.41% of the total number of female employees were rated 4 and 41.95% were rated 2. (The data provided did not specify what these ratings mean.)
 * Similarly, 4.07% male employees got a 4 rating and 46.78% were rated 2. (The data provided did not specify what these ratings mean.)
 * The Strategy department holds the highest number of executives. All are male.
 * Females make up just 15.79% of the total number of employees and belong to the Sales & Marketing, HR, and Internal Services departments.
 * Majority of the employees fall within the age groups 20-29 and 30-39.
 * A small minority are between the ages 16-19 and are Junior Officers.
 * The Executive team of 16 is made up of 10 employees in the age bracket 40-49.
 * Only 4 employees are 60-69 years of age. 


### Visualizations
---
![Viz1](https://github.com/kayeneii/PwC-Diversity/blob/main/PWC_Pharma-Group-AG.png)

![Viz2](https://github.com/kayeneii/PwC-Diversity/blob/main/PWC_Pharma-Group-AG1.png)
