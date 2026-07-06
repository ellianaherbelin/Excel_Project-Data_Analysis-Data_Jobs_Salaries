# 🔎 Salary & Skills Analysis  
## Introduction  
This analysis reflects how important it is to be informed about what skills have the most leverage in the world of data. Especially if you're a newcomer to the field of Data Science, you'll want to know which skills to become familiar with first so that you can perform at your best for your target employer avatar AND receive adequate compensation.  
## 🔗 Analysis File  
You can check out the final analysis in [Project_2-Analysis](Project_2-Analysis).  
### 💭 Questions to Analyze  
I established the goals of this analysis by asking these questions:  
1. Do more skills get you better pay?
2. What's the salary for data jobs in different regions?
3. What are the top skills of data professionals?
4. What's the pay for the top 15 skills?  
### Excel Skills Used  
The following Excel skills were utilized in this analysis:  
- 🔢 Pivot Tables
- 📊 Pivot Charts
- 🟰 DAX (Data Analysis Expressions)
- 💪 Power Query  
- 📑 Power Pivot  
### Data Jobs Dataset  
The dataset used is from Luke Barousse's Excel Course on YouTube. It contains real-world information from 2023. The knowledge became my own as I followed the project build with him a first time, and then did it all from scratch a second time, which is what you're about to see now. The dataset contains detailed information on:  
- 🧑‍💼 Job Titles
- 💰 Salaries
- 🗺️ Locations
- 🛠️ Skills
## 1️⃣ Do more skills get you better pay?  
### Skill: 💪 Power Query (ETL)  
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

From that was made a PivotTable and PivotChart:  
<img width="1717" height="778" alt="Screenshot 2026-07-03 095431(1)" src="https://github.com/user-attachments/assets/8faef149-9ba1-42aa-9e36-93f1e416657c" />   

💡 **Insights**  
- A higher skill count is associated with a higher salary; less specialized roles like Data Analyst and Business Analyst receive less pay.
- ML Engineer and Senior Data Scientist have a similar median salary to that of Senior Data Engineer, however they have a lower skill count.
- The same goes for Software Engineer and Data Scientist being similar in pay to Data Engineer while having a lower level of skills.
- Strictly in general, non-engineer data jobs can be said to require less skills and receive a similar pay to their engineering counterparts.  
## 2️⃣ What's the salary for data jobs in different regions?  
### Skills: 🔢 PivotTables and 🟰 DAX  
**PivotTables**  
I loaded the first of my two queries from earlier into a PivotTable and set the structure and values with PivotTable fields.  
<img width="783" height="767" alt="Screenshot 2026-07-03 101932(1)" src="https://github.com/user-attachments/assets/76e07799-bcea-46ee-a7cf-1f032437a489" />  

**DAX**  
The fields for the Values in the PivotTable are actually measures, as you can see here:  
<img width="349" height="203" alt="Screenshot 2026-07-03 102350(1)" src="https://github.com/user-attachments/assets/8f1889e2-dcfc-4268-969b-59a3a3a03485" />  

DAX formula for the measure "Median Salary (Selected Country)":  
`Median Salary:=MEDIAN(data_jobs_salary[salary_year_avg])`  
where "salary_year_avg" is the name of the column containing the average yearly salary of each job posting.  

This is the DAX formula for the measure "Median Salary US":  
`Median Salary US:=CALCULATE([Median Salary],data_jobs_salary[job_country]="United States")`  

Here's the final result:  
<img width="1984" height="548" alt="Screenshot 2026-07-03 101510(1)" src="https://github.com/user-attachments/assets/583a8d37-898a-4643-bccf-396dfd8ec61b" />  

💡 **Insights**  
- ML Engineer, Business Analyst, Data Scientist, and Software Engineer roles located in the US have a generally greater possibility of a higher salary than other regions.  
- Users can investigate which countries where data roles may have a pay advantage.  
## 3️⃣ What are the top skills of data professionals?  
### Skill: 📑 Power Pivot  
The queries I've built everything upon have been added to the Data Model and are tables in Power Pivot. For my smaller query "data_jobs_skills", now a table, I created some measures with more DAX:  
`Skill Count:=COUNT([job_skills_clean])`  

`Skill Likelihood:=DIVIDE([Skill Count],[Count of job_title_short])`  
where "Skill Likelihood" is a field utilized in the PivotTable for this section of the analysis and is presented as a percentage.  

I also made a relationship between the two tables via the columns from both named "job_id"  
<img width="793" height="720" alt="Screenshot 2026-07-03 111010(1)" src="https://github.com/user-attachments/assets/62572e9c-e176-4ced-bb09-7a44c3731d65" />  

Thus I came up with this PivotTable:  
<img width="254" height="456" alt="Screenshot 2026-07-06 095047" src="https://github.com/user-attachments/assets/699bcb39-da37-4499-b4ef-c649a673e898" />  

💡 **Insights**  
- SQL, Excel, Tableau, and Python are the most largely used skills by the Data Analyst in the US, with SAS, Power BI, R, Word, and Powerpoint expressing moderate popularity.
- The user is enabled a quick perception at what skills different jobs are likely to entail.
- Skill popularity varies a bit by region. (Becomes apparent upon using the slicers of this worksheet.)   
## 4️⃣ What's the pay for the top 15 skills?  
### Skill: 📊 Pivot Charts (Advanced Charts)  
Due to the relationship between the two tables in my Data Model, I was able to use fields and measures from both to construct a PivotChart. I decided to customize a combination chart of columns and a line with markers that I arranged on a secondary axis for a more practical design. After formatting the axis and colourizing the visuals, it was ready:  
<img width="1271" height="775" alt="Screenshot 2026-07-06 100657(1)" src="https://github.com/user-attachments/assets/76481437-cee1-4416-a588-f31fdd05f291" />  

💡 **Insights**  
- Python has a high median salary while being high in demand, with others, namely Tableau and SQL, following this pattern.  
- SAS, Power BI, R, and Excel also remain at the top of the list of skills with the highest ROI.
- Skills with higher pay yet lower likelihood are more niched, and may require more specific situations to bring value back to you.
- Therefore, it would benefit the aspiring Data Analyst to pick up on the more popular, higher paying skills first, and then niche down their repertoire with the less likely but more valuable skills.  
## Conclusion  
From this analysis I hope to aid those that wish to understand the trends of the Data Science job market and are either currently learning skills to land their first job, or are interested in finding ways to increase the leverage of their current skillset after they've already been in the field. Thank you for reading and stay informed!  
## 🔗 Dashboard File  
If you haven't already, you can checkout part 1 of this project in [Project_1-Dashboard](https://github.com/ellianaherbelin/Excel_Project-Data_Analysis-Data_Jobs_Salaries/tree/main/Project_1-Dashboard).
