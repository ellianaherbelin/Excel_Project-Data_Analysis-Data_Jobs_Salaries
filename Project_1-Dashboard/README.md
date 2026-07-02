# Data Jobs Salary Dashboard  
<img width="2690" height="1250" alt="Excel_Data_Job_Salary_Dashboard_Demo-ezgif com-optimize" src="https://github.com/user-attachments/assets/cebf971f-db26-4350-87f8-47cb85bd68d3" />  

## Introduction  
This Data Science Salary Dashboard was made to assist job seekers in speculating what kind of pay they can expect, depending on their role, region, and schedule. 🔍   
## Dashboard File  
You can checkout the final dashboard in [Project_1-Dashboard](Project_1-Dashboard)  
## Excel Skills Used  
The following Excel skills were utilized in this analysis:  
- Charts
- Formulas and Functions
- Data Validation
## Data Jobs Dataset  
The dataset used is from Luke Barousse's Excel Course on YouTube. It contains real-world information from 2023. The knowledge became my own as I followed the project build with him a first time, and then did it all from scratch a second time, which is what you're about to see now. The dataset contains detailed information on:  
- Job Titles  
- Salaries
- Locations
- Skills
# Dashboard Build  
## Formulas and Functions  
### Median Salary by Job Title  
```
=MEDIAN(
 IF(
  (Data[job_country]=country)*
  (Data[job_title_short]=$A2)*
  (ISNUMBER(SEARCH(type,Data[job_schedule_type])))*
  (Data[salary_year_avg]<>0),
  Data[salary_year_avg]
 )
)
```
- **Filters by Multiple Values:** excluding blank values and data that doesn't meet the criteria for country, job title and schedule type.
- **Array Formula:** `MEDIAN(` formula with a nested `IF(` statement to be uniquely tailored to each value in the array.  
- **Advanced Boolean Value Usage:** `(ISNUMBER(SEARCH(type,Data[job_schedule-type])))` where value of "type" is determined by which value is selected in "schedule type" of the dashboard. `SEARCH(` will return a number given that the data matches data validation, and `ISNUMBER(` will include that row in the formula if it indeed matches.

**Results:** This formula populates the table below with the median salary for each job title while also filtering for country and schedule type:  
<img width="751" height="381" alt="Screenshot 2026-07-02 062910" src="https://github.com/user-attachments/assets/61fea77a-cdec-44e1-86c4-cc4671d6d4d8" />  
## Charts  
# Clustered Bar Chart  
- To be continued/not yet finished! -July 2nd, 2026
