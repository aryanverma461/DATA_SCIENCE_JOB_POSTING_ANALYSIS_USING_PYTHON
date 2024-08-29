# Overview
Welcome to my analysis of the data job market, focusing on data analyst roles. This project was created out of a desire to navigate and understand the job market more effectively. It delves into the top-paying and in-demand skills to help find optimal job opportunities for data analysts.

The data sourced from Luke Barousse's Python Course which provides a foundation for my analysis, containing detailed information on job titles, salaries, locations, and essential skills. Through a series of Python scripts, I explore key questions such as the most demanded skills, salary trends, and the intersection of demand and salary in data analytics.
### Dataset:
[Data set of Data science job postings 2023](/1_Data_science_job_postings_dataset/)
### Data_Science_Job_Postings_analysis:
[Click Here](/Data_Science_Job_Postings_analysis/)

Includes Python scripts with all the detailed analysis.

# The Questions
Below are the questions I want to answer in my project:

1. What are the skills most in demand for the top 3 most popular data roles?
2. How are in-demand skills trending for Data Analysts?
3. Top 10 skills for Data Analyst? (High Demand)
4. What are the Median Salaries offered across Top 5 country for 3 popular data role
5. How do Median salary vary across different data jobs Titles
6. What are the optimal skills for data analysts to learn? (High Demand AND High Paying)
# Tools I Used
For my deep dive into the data analyst job market, I harnessed the power of several key tools:
- **Python**: The backbone of my analysis, allowing me to analyze the data and find critical insights.

- I also used the following Python libraries:
    - Pandas Library: This was used to analyze the data.
    - Matplotlib Library: I visualized the data.
    - Seaborn Library: Helped me create more advanced visuals.
- **Jupyter Notebooks**: The tool I used to run my Python scripts which let me easily include my notes and analysis.
- **Visual Studio Code**: My go-to for executing my Python scripts.
- **Git & GitHub**: Essential for version control and sharing my Python code and analysis, ensuring collaboration and project tracking.
# Data Preparation and Cleanup
This section outlines the steps taken to prepare the data for analysis, ensuring accuracy and usability
## Import & Clean Up Data
I start by importing necessary libraries and loading the dataset, followed by initial data cleaning tasks to ensure data quality.
```python
# Importing Libraries
import pandas as pd
import ast
from datasets import load_dataset
import matplotlib.pyplot as plt  

# Loading Data
parquet_file= r'C:\Users\verma\OneDrive\Desktop\PYTHON_DATA_PROJECT\1_Data_science_job_postings_dataset\0000.parquet'
df = pd.read_parquet(parquet_file, engine='auto')

# Data Cleanup
df['job_posted_date'] = pd.to_datetime(df['job_posted_date'])
df['job_skills'] = df['job_skills'].apply(lambda skill:ast.literal_eval(skill) if pd.notna(skill) else skill)
```
# The Analysis
## 1. What are the most demanded skills for the top 3 most popular data roles?
To find the most demanded skills for the top 3 most popular data roles. I filtered out those positions by which ones were the most popular, and got the top 5 skills for these top 3 roles. This query highlights the most popular job titles and their top skills, showing which skills I should pay attention to depending on the role I'm targeting.

View my notebook with detailed steps here: [2_Skill_Demand](/Data_Science_Job_Postings_analysis/8_Top_skillsFor_DataScientists_Engineers_Analysts.ipynb)

### Results:
![alt text](/assets/image.png)

Bar graph visualizing the salary for the top 3 data roles and their top 5 skills associated with each.

## 2. How are in-demand skills trending for Data Analysts?

To find how skills are trending in 2023 for Data Analysts, I filtered data analyst positions and grouped the skills by the month of the job postings. This got me the top 5 skills of data analysts by month, showing how popular skills were throughout 2023.

View my notebook with detailed steps here:
[Top 5 Skills Trend](/Data_Science_Job_Postings_analysis/7_Top5_skills_trend_across_year_DataAnalyst.ipynb)

### Result:
![alt text](/assets/image-1.png)



## 3. Top 10 skills for Data Analyst? (High Demand)

To identify the Top 10 skills For Data Analyst, I only got jobs in the United States and also filtered the data specially for Data Analyst and looked at Total count of each Skilss in job postings data.

View my notebook with detailed steps here: [Top_10](/Data_Science_Job_Postings_analysis/6_Top_10_skills_for_Data_Analyst.ipynb)

### Result:
![alt text](/assets/image-3.png)

The Graph shows Skills like: **SQL**, **Excel**, **Python** are The One in high demand 

## 4. What are the Median Salaries offered across Top 5 country for 3 popular data role
To identify the Median salaries offered across different countries for 3 popular data roles, Used pandas pivot_table function to retrieve the data for the analysis and filtered that pivot table specially for the Top 3 data roles.

View my notebook with detailed steps here: [Top_5_countires](/Data_Science_Job_Postings_analysis/4_Top5_country_median_salary_analysis.ipynb)

### Result:
![alt text](/assets/image-4.png)

## 5. How do Median salary vary across different data jobs Titles?

To identify the highest-paying job roles, I only got jobs in the United States and looked at their median salary.

View my notebook with detailed steps here:[Media Salary For Diff JOB TITLES](/Data_Science_Job_Postings_analysis/3_MedianSalary_of_Diff_JobTitles.ipynb)

### Result:
![alt text](/assets/image-2.png)
## 6. What are the optimal skills for data analysts to learn? (High Demand AND High Paying)
To identify the most optimal skills to learn ( the ones that are the highest paid and highest in demand) I calculated the percent of skill demand and the median salary of these skills. To easily identify which are the most optimal skills to learn.

View my notebook with detailed steps here: [Scatter_plot](/Data_Science_Job_Postings_analysis/11_Data_Analyst_skills_MedianSalaryVsTotalCount.ipynb)

### Result:
![alt text](/assets/image-5.png)
- More commonly required skills like Excel and SQL have a large presence in job listings but lower median salaries compared to specialized skills like Python and Tableau, which not only have higher salaries but are also moderately prevalent in job listings.
- Skills such as Python, Tableau, and SQL Server are towards the higher end of the salary spectrum while also being fairly common in job listings, indicating that proficiency in these tools can lead to good opportunities in data analytics.

# What I Learned
Throughout this project, I deepened my understanding of the data analyst job market and enhanced my technical skills in Python, especially in data manipulation and visualization. 

Here are a few specific things I learned:
- **Advanced Python Usage**: Utilizing libraries such as Pandas for data manipulation, Seaborn and Matplotlib for data visualization, and other libraries helped me perform complex data analysis tasks more efficiently.
- **Data Cleaning Importance**: I learned that thorough data cleaning and preparation are crucial before any analysis can be conducted, ensuring the accuracy of insights derived from the data.
- **Strategic Skill Analysis**: The project emphasized the importance of aligning one's skills with market demand. Understanding the relationship between skill demand, salary, and job availability allows for more strategic career planning in the tech industry.

# Challenges I Faced
This project was not without its challenges, but it provided good learning opportunities:

- **Data Inconsistencies**: Handling missing or inconsistent data entries requires careful consideration and thorough data-cleaning techniques to ensure the integrity of the analysis.
- **Complex Data Visualization**: Designing effective visual representations of complex datasets was challenging but critical for conveying insights clearly and compellingly.
- **Balancing Breadth and Depth**: Deciding how deeply to dive into each analysis while maintaining a broad overview of the data landscape required constant balancing to ensure comprehensive coverage without getting lost in details.

# Conclusion
This exploration into the data analyst job market has been incredibly informative, highlighting the critical skills and trends that shape this evolving field. The insights I got enhance my understanding and provide actionable guidance for anyone looking to advance their career in data analytics. As the market continues to change, ongoing analysis will be essential to stay ahead in data analytics. This project is a good foundation for future explorations and underscores the importance of continuous learning and adaptation in the data field.