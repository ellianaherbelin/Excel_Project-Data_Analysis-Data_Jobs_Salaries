# Salary & Skills Analysis  
## Introduction  
This analysis reflects how important it is to be informed about what skills have the most leverage in the world of data. Especially if you're a newcomer to the field of Data Science, you'll want to know which skills to become familiar with first so that you can perform at your best for your target employer avatar AND receive adequate compensation.  
### Questions to Analyze  
I established the goals of this analysis by asking these questions:  
1. Do more skills get you better pay?
2. What's the salary for data jobs in different regions?
3. What are the top skills of data professionals?
4. What's the pay for the top 15 skills?  
### Excel Skills Used  
The following Excel skills were utilized in this analysis:  
- Pivot Tables
- Pivot Charts
- DAX (Data Analysis Expressions)
- Power Query  
- Power Pivot  
### Data Jobs Dataset  
The dataset used is from Luke Barousse's Excel Course on YouTube. It contains real-world information from 2023. The knowledge became my own as I followed the project build with him a first time, and then did it all from scratch a second time, which is what you're about to see now. The dataset contains detailed information on:  
- Job Titles
- Salaries
- Locations
- Skills
## 1. Do more skills get you better pay?  
### Skill: Power Query (ETL)  
**Extract**  
First, I **extract**ed a data table from my resource and then launched the Power Query Editor. I made my first query and the appropriate M language for the first "Source" step appeared in the formula bar as follows:  
```
= Excel.Workbook(File.Contents("C:\Users\[my username]\Documents\Excel\Luke Barousse Excel Project\Excel_Project-Data_Analysis-Data_Jobs_Salaries\data_jobs_salary_dataset.xlsx"), null, true)
```  
Next, I **transform**ed the data, taking steps to remove unneccessary columns, excess wording, and trimming whitespace.  

<img width="531" height="615" alt="Screenshot 2026-07-03 062848" src="https://github.com/user-attachments/assets/612ec3fc-42b3-4315-b83f-d137a7fe2291" />  

# Not yet finished/README in progress! - July 3, 2026  
## 2. What's the salary for data jobs in different regions?  
### Skills: PivotTables and DAX  
## 3. What are the top skills of data professionals?  
### Skill: Power Pivot  
## 4. What's the pay for the top 15 skills?  
### Skill: Pivot Charts (Advanced Charts)  
## Conclusion  
