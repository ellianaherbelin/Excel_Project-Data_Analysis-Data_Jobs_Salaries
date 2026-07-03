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
First, I *extract*ed a data table from my resource and then launched the Power Query Editor. I made my first query and the appropriate M language for the first "Source" step appeared in the formula bar as follows:  
```
= Excel.Workbook(File.Contents("C:\Users\[my username]\Documents\Excel\Luke Barousse Excel Project\Excel_Project-Data_Analysis-Data_Jobs_Salaries\data_jobs_salary_dataset.xlsx"), null, true)
```
**Transform**  
Next, I *transform*ed the data, taking steps to remove unneccessary columns, excess wording, and trimming whitespace.  

<img width="398" height="461" alt="Screenshot 2026-07-03 062848(1)" src="https://github.com/user-attachments/assets/f5eff7b5-9b34-4beb-962b-52498ca01625" />  

I made another query that is sourced from the first query, and unpivoted the columns in the second query in order to limit it to one skill per row while still being assigned to the same job listing.  

<img width="525" height="603" alt="Screenshot 2026-07-03 094044(1)" src="https://github.com/user-attachments/assets/61cbaa28-d45c-48fe-ac4e-da00c1556ec8" />

**Load**  
I wrapped it up by saving and *load*ing for utilization in the workbook.  

<img width="1780" height="1029" alt="Screenshot 2026-07-03 094734(1)" src="https://github.com/user-attachments/assets/828dd447-ebde-4cbc-b6cf-47527a2156ab" />  

From that was made a pivot table and corresponding chart:  

<img width="1717" height="778" alt="Screenshot 2026-07-03 095431(1)" src="https://github.com/user-attachments/assets/8faef149-9ba1-42aa-9e36-93f1e416657c" />  

**Insights**  
- A higher skill count is associated with a higher salary; less specialized roles like Data Analyst and Business Analyst receive less pay.
- ML Engineer and Senior Data Scientist have a similar median salary to that of Senior Data Engineer, however they have a lower skill count.
- The same goes for Software Engineer and Data Scientist being similar in pay to Data Engineer while having a lower level of skills.
- Strictly in general, non-engineer data jobs can be said to require less skills and receive a similar pay to their engineering counterparts.  
## 2. What's the salary for data jobs in different regions?  
### Skills: PivotTables and DAX  
**PivotTables**  
I loaded the first of my two queries from earlier into a PivotTable and set the structure and values with PivotTable fields.  

<img width="783" height="767" alt="Screenshot 2026-07-03 101932(1)" src="https://github.com/user-attachments/assets/76e07799-bcea-46ee-a7cf-1f032437a489" />  

**DAX**  
The fields for the Values in the PivotTable are actually measures, as you can see here:  

<img width="349" height="203" alt="Screenshot 2026-07-03 102350(1)" src="https://github.com/user-attachments/assets/8f1889e2-dcfc-4268-969b-59a3a3a03485" />  

DAX formula for the measure "Median Salary (Selected Country)":  
`=MEDIAN(data_jobs_salary[salary_year_avg])`  
where "salary_year_avg" is the name of the column containing the average yearly salary of each job posting.  

This is the DAX formula for the measure "Median Salary US":  
`=CALCULATE([Median Salary],data_jobs_salary[job_country]="United States")`  
where "Median Salary" is the name of a value in the PivotTable for question 1.  

Here's the final result:  
<img width="1984" height="548" alt="Screenshot 2026-07-03 101510(1)" src="https://github.com/user-attachments/assets/583a8d37-898a-4643-bccf-396dfd8ec61b" />  

**Insights**  
- ML Engineer, Business Analyst, Data Scientist, and Software Engineer roles located in the US have a generally greater possibility of a higher salary than other regions.  
- Users can investigate which countries where data roles may have a pay advantage.  
# Not yet finished/README in progress! - July 3, 2026 
## 3. What are the top skills of data professionals?  
### Skill: Power Pivot  
## 4. What's the pay for the top 15 skills?  
### Skill: Pivot Charts (Advanced Charts)  
## Conclusion  
