
# Project 2 Analysis

## Introduction

This project was completed as part of Luke Barousse’s Excel for Data Analytics course. I followed along with the guided exercises and built this dashboard to practice real-world Excel skills such as data cleaning, pivot tables, conditional formatting, and interactive dashboard creation.

The dataset contains job listings for data analyst and data science roles. While the analysis framework came from the course, I completed each step independently and personalized sections of the dashboard to reinforce the concepts.


### Questions to Analyze

To understand the data science job market, I asked the following:

1. **Do more skills get you better pay?**
2. **What’s the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📊 Pivot Tables**
- **📈 Pivot Charts**
- **🧮 DAX (Data Analysis Expressions)**
- **🔍 Power Query**
- **💪 Power Pivot**

### Data Jobs Dataset

The dataset used in this project contains real-world data science job listings from 2023. It was provided as part of the Excel course I followed, which focused on building foundational skills in data analysis using Excel.  

It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## 1️⃣ Do more skills get you better pay?

### 🔍 Skill: Power Query (ETL)

#### 📥 Extract

I used Power Query to pull in the original dataset (`data_salary_all.xlsx`) and created two queries:

- 🗃️ `data_jobs_all`: contains all job listing information

- 🔧 `data_job_skills`: lists the required skills by job ID

#### 🔄 Transform

Next, I cleaned and prepared each query by:
- Changing column types
- Removing unnecessary columns
- Cleaning up text (removing keywords, trimming whitespace)

    - 📊 `data_jobs_all`

        ![2_Project_Analysis_Screenshot1.png](/0_Resources/Images/2_Project_Analysis_Screenshot1.png)

    - 🛠️ `data_job_skills`

        ![2_Project_Analysis_Screenshot2.png](/0_Resources/Images/2_Project_Analysis_Screenshot2.png)

#### 🔗 Load

- Finally, I loaded both cleaned queries into the workbook for analysis.

    - 📊 `data_jobs_all`

        ![2_Project_Analysis_Screenshot3.png](/0_Resources/Images/2_Project_Analysis_Screenshot3.png)

    - 🛠️ `data_job_skills`

        ![2_Project_Analysis_Screenshot4.png](/0_Resources/Images/2_Project_Analysis_Screenshot4.png)

### 📊 Analysis

#### 💡 Insights

- 📈 There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
- 💼 Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

    ![2_Project_Analysis_Chart1.png](/0_Resources/Images/2_Project_Analysis_Chart1.png)

#### 🤔 So What

- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.

## 2️⃣ What’s the salary for data jobs in different regions?

### 🧮 Skills: PivotTables & DAX

#### 📈Pivot Table

- 🔢 I created a PivotTable using the Data Model I created with Power Pivot.
- 📊 I moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
- 🧮 Then I added new measure to calculate the median salary for United States jobs.
    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```

#### 🧮 DAX
```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
```

### 📊 Analysis

#### 💡 Insights

- 💼 Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.
- 💰 The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.

    ![2_Project_Analysis_Chart2.png](/0_Resources/Images/2_Project_Analysis_Chart2.png)

#### **🤔 So What**

- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## 3️⃣ What are the top skills of data professionals?

### 🔧 Skill: Power Pivot

#### 💪 Power Pivot

- 🔗 I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- 🧹 Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

#### 🔗 Data Model

- I created a relationship between my two tables using the `job_id` column.

    <img src="https://raw.githubusercontent.com/lukebarousse/Excel_Data_Analytics_Course/refs/heads/main/0_Resources/Images/2_Project_Analysis_Screenshot5.png" alt="Project Analysis Screenshot 5" width="500px">


#### 📃 Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.

    ![2_Project_Analysis_Screenshot6.png](/0_Resources/Images/2_Project_Analysis_Screenshot6.png)

### 📊Analysis

#### 💡Insights

- 💻 SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- ☁️ Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

    ![2_Project_Analysis_Chart3.png](/0_Resources/Images/2_Project_Analysis_Chart3.png)

#### 🤔So What

- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.

## 4️⃣ What’s the pay of the top 10 skills?

### 📊 Skill: Advanced Charts (Pivot Chart)

#### 📈 PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
    - 🪙 **Primary Axis:** Median Salary (as a Clustered Column)
    - 👍 **Secondary Axis:** Skill Likelihood (as a Line with Markers)
- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

### 📊 Analysis

#### 💡Insights

- 💰 Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.
- 📉 Skills like PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

    ![2_Project_Analysis_Chart4.png](/0_Resources/Images/2_Project_Analysis_Chart4.png)

#### 🤔So What

- This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.

## Conclusion

This project gave me practical experience using Excel tools like Power Query, PivotTables, DAX, and charts to analyze real-world job market data. While the course provided the structure, I completed each step independently and added customizations to deepen my understanding.

It reinforced how in-demand tools like Python, SQL, and cloud platforms align with higher salaries, and it proved how Excel can drive meaningful insights when used well. Projects like this continue to build my foundation as a data analyst ready to tackle real business problems.
