# School District Analysis

## Overview of the School District Analysis

### Purpose

Maria, a chief data scientist for a city school district, and her supervisor have been notified that the “students_complete.csv” file (data source/dataset) shows evidence of academic dishonesty. This is specific to the reading and math grades for Thomas High School ninth graders, which appear to have been altered.

The purpose of this analysis is to help Maria replace the math and reading scores for Thomas High School with NaNs (Not a Number) while keeping the rest of the data intact. Additionally, she has requested to use Python and the Pandas library to analyze school district data and showcase trends in school performance with the updated numbers/figures (metrics=benchmark). 

These insights are used to inform discussion and strategic decisions at the school and district level. Moreover, the updated analysis will assist the school board, the superintendent and stakeholders in making decisions regarding the school budgets and priorities for the upcoming school year.

## Results

### Data Source and Files

The updated school district analysis is available here: [PyCitySchools_Challenge](PyCitySchools_Challenge.ipynb)

The school district analysis is based on the following data sources/datasets: 
* School Data: [schools_complete](Resources/schools_complete.csv)
* Student Data: [students_complete](Resources/students_complete.csv)

### Software and Application

The software and web-based application used for this analysis are:
* Python 3.7.11 (using PythonData environment and Pandas Library)
* Anaconda 4.11.0
* Jupyter Notebook 6.4.6

### Outcomes 

* How is the district summary affected?

The school district summary is a high-level snapshot of the district's key metrics: Total number of students, Total number of schools, Total budget, Average math score, Average reading score, Percentage of students who passed math, Percentage of students who passed reading and Overall passing percentage.
Even after the reading and math scores for the ninth grade at Thomas High School were replaced with NaNs, the school district summary was affected with a slight negative change across the board, except for the Average Reading Score which stayed at 81.9
Prior to replacing scores for the ninth grade at Thomas High School, the school district summary was as follows:

![district_summary_oldnumbers](district_summary_oldnumbers.png)

In comparison/contrast, the updated school district summary is shown below:

![District_summary_new_total_student_count](District_summary_new_total_student_count.png)
 
* How is the school summary affected?

It was determined that math and reading grades of 461 students in the 9th grade (the ninth grade) at Thomas High School were not going to be considered for both the school district summary as well as the school summary. Therefore (As a result), only the math and reading grades of students in the 10th, 11th and 12th grade were being calculated for Thomas High School instead to uphold state-testing standards.

For example, in order to calculate the overall passing percentage of the 10th to 12th grade from Thomas High School the following code was used:
```
ThomasHS_overallpassing_mathreading_percentage = ThomasHS_passing_mathreading.count()["student_name"] / ten_eleven_twelve_count * 100
ThomasHS_overallpassing_mathreading_percentage

90.63032367972743
```
Then to replace the overall passing percentage with the updated 90.63 overall passing percentage for Thomas High School, this code was added:
```
per_school_summary_df.loc[['Thomas High School'], ['% Overall Passing']] = ThomasHS_overallpassing_mathreading_percentage
per_school_summary_df
```
The updated school summary data for Thomas High School is highlighted in the blue box as shown below:
![per_school_summary_new ](per_school_summary_new.png)

* How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance relative to the other schools?
The average scores with the new calculation were not significantly affected by the removal of the 9th grade scores. In fact, Thomas High School remained in second place of the Top 5 list of the Highest Performing Schools based on the overall percentage of passing students. To show the top five schools based on the overall passing rate the following code was used:
```
top_schools = per_school_summary_df.sort_values(["% Overall Passing"], ascending=False)
top_schools.head(5)
```
![ThomasHS_High_Performing_updatedmetrics](ThomasHS_High_Performing_updatedmetrics.png)

* How does replacing the ninth-grade scores affect the following:

•	Math and reading scores by grade
•	Scores by school spending
•	Scores by school size
•	Scores by school type
