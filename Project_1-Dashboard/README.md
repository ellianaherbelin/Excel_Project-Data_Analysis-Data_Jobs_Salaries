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
### Bar Chart - Job Role Median Salaries  
<img width="754" height="536" alt="Screenshot 2026-07-02 061733" src="https://github.com/user-attachments/assets/b2e7731d-1ec0-48c8-9d99-3a99632a3c20" />  

- **Readability:** horizontal arrangement chosen for larger labeling and simplicity prioritized for straight-forward practicality.
- **Mindful Design:** value that is selected in data validation will appear highlighted, while the list will organize automatically in descending order (highest to lowest median salary)
- **Formatting:** numerical values converted into a custom shortened accounting format for further ease.
- **Insights:** allows for interpretation of what kind of salary to expect from each role. In general, senior roles have an advantage and can be expected at the top of the list along with ML Engineer and Data Scientist.
### Map Chart - Salary by Region  
<img width="756" height="533" alt="Screenshot 2026-07-02 061740" src="https://github.com/user-attachments/assets/cf3c701b-d273-47bf-ae95-55c6ca90144f" />  

- **Visual Enhancement:** color-coded display of the distribution of median salary amounts across regions.
- **Data Representation:** every coloured country has available data that can be viewed by hovering the mouse over it.
- **Insights:** vests the reader with an immediate sense of global salary trends while assisting in identifying high/low salary countries.  
## Data Validation  
### (a.k.a. Filtered Lists)  
<img width="582" height="408" alt="Screenshot 2026-07-02 061944" src="https://github.com/user-attachments/assets/e1ca831c-a8f3-4f49-880b-8808298cebac" />  

- **Secure Dropdown List:** given that this feature includes manual keyboard input, a dropdown list establishes the rules for what input is acceptable and eliminates the guesswork.
- **Functionality:** this feature equips the user to be able to try out different scenarios. Give it a try! Make a hypothesis and test your knowledge.
## Conclusion  
I created this dashboard to expand the understanding of working professionals in the data science field in regards to their demand, their median salary, and variations by region. Thank you for reading!  
## Analysis File  
You can checkout the other part of this project in [Project_2-Analysis](Project_2-Analysis)
