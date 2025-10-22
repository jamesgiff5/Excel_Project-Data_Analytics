# Excel Salary Dashboard

![1_Salary_Dashboard.png](/0_Resources/Images/1_Salary_Dashboard_Final_Dashboard.gif)

## Introduction

This project was completed as part of Luke Barousse’s Excel for Data Analytics course. It focused on foundational Excel skills including formulas, functions, data validation, and basic charting.

Using a dataset of data-related job listings, I followed structured exercises to explore salary trends across job titles, countries, and work types. This project helped me build a solid foundation in Excel before moving on to more advanced tools in later projects.

### Dashboard File
The final dashboard is available in the [1_Salary_Dashboard.xlsx](1_Salary_Dashboard.xlsx) file.

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **Charts**
- **Formulas and Functions**
- **Data Validation**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. The dataset is available via my Excel course, which provides a foundation for analyzing data using Excel. It includes detailed information on:

- **Job titles**
- **Salaries**
- **Locations**
- **Skills**

## Dashboard Build

### 📉 Charts

#### Data Science Job Salaries - Bar Chart

<img src="https://raw.githubusercontent.com/lukebarousse/Excel_Data_Analytics_Course/refs/heads/main/0_Resources/Images/1_Salary_Dashboard_Chart1.png" alt="Salary Dashboard Chart1" width="500px">

- **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
- **Data Organization:** Sorted job titles by descending salary for improved readability.
- **Insights Gained:** This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

#### 🗺️ Country Median Salaries - Map Chart

<img src="https://raw.githubusercontent.com/lukebarousse/Excel_Data_Analytics_Course/refs/heads/main/0_Resources/Images/1_Salary_Dashboard_Country_Map.gif" alt="Salary Dashboard Country Map" width="500px">

- **Excel Features:** Utilized Excel's map chart feature to plot median salaries globally.
- **Design Choice:** Color-coded map to visually differentiate salary levels across regions.
- **Data Representation:** Plotted median salary for each country with available data.
- **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends.
- **Insights Gained:** Enables quick grasp of global salary disparities and highlights high/low salary regions.

### Formulas and Functions

#### 💰 Median Salary by Job Titles

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

- **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
- **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
- **Tailored Insights:** Provides specific salary information for job titles, regions, and schedule types.
- **Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

📋 Background Table

![1_Salary_Dashboard_Screenshot1.png](/0_Resources/Images/1_Salary_Dashboard_Screenshot1.png)

📉 Dashboard Implementation

<img src="https://raw.githubusercontent.com/lukebarousse/Excel_Data_Analytics_Course/refs/heads/main/0_Resources/Images/1_Salary_Dashboard_Job_Title.png" alt="Salary Dashboard Title" width="350px">


#### Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
- **Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

Background Table

![1_Salary_Dashboard_Type.png](/0_Resources/Images/1_Salary_Dashboard_Screenshot2.png)

📉 Dashboard Implementation:

<img src="https://raw.githubusercontent.com/lukebarousse/Excel_Data_Analytics_Course/refs/heads/main/0_Resources/Images/1_Salary_Dashboard_Type.png" alt="Salary Dashboard by Job Type" width="350px">

### Data Validation

#### Filtered List

- **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    - User input is restricted to predefined, validated schedule types
    - Incorrect or inconsistent entries are prevented
    - Overall usability of the dashboard is enhanced

<img src="https://raw.githubusercontent.com/lukebarousse/Excel_Data_Analytics_Course/refs/heads/main/0_Resources/Images/1_Salary_Dashboard_Data_Validation.gif" alt="Salary Dashboard Data Validation" width="350px">



## Conclusion

I built this dashboard to explore how job title, location, and work type affect salaries in the data field. It’s meant to help others get a clearer picture of where they stand and what to aim for, while also showing what Excel can do when used well. 
