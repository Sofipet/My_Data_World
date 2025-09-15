# Employees SQL Analysis

## Introduction
This project involves analyzing employee data using Python and SQL. The main objectives of the analysis were to extract meaningful insights from the employee database, visualize key metrics, and make data-driven decisions. The project utilizes various Python libraries such as `mysql.connector`, `pandas`, and `matplotlib`.

## Objectives

- Analyze employee data using Python and SQL to gain insights into various aspects of the workforce.
- Identify patterns and trends in employee positions, duration of employment, and other relevant metrics.
- Present findings through visualizations and statistical analysis.

## Methodology

### Data Collection
- **SQL Queries**: Retrieved employee data from a SQL database using specific queries.
- **Data Loading**: Loaded the retrieved data into a pandas DataFrame for analysis.

### Data Analysis
- **Exploratory Data Analysis (EDA)**: Conducted EDA to understand the distribution and characteristics of the dataset.
- **Visualization**: Created various visualizations using matplotlib to illustrate the findings.

## Key Insights

1. **Duration of Employment**: Most engineers tend to stay with the company for about 5 years, as indicated by the histogram.
2. **Position Analysis**: The dataset provided insights into the duration employees hold specific positions and their distribution across different roles.
3. **Salary Distribution**: The average salary is 70000$, the lowest is 40000$ and the highest is about 120000$-140000$, but the number of employees getting such salary is extremely small.
4. **Hiring Process**: According to the lineplot the hiring peak in the company was in 1986 and by 2000 they almost stopped hiring new employees. So there's a correlation between the hiring year and the number of employees hired this year.

## Recommendations

Based on the analysis, the following recommendations are made:
1. **Employee Retention Strategies**: Focus on strategies to retain engineers beyond the 5-year mark, as this appears to be a common duration of employment.
2. **Targeted Training Programs**: Implement training and development programs to help employees transition to new roles or advance in their current positions.
3. **Hiring Process Optimization**: Streamline interview stages and improve candidate sourcing by investing in employee referral programs to attract high-quality candidates.

## Conclusion

The analysis of the employee data reveals patterns and trends that can significantly influence the company's HR strategies. These insights can assist in strategic decision-making regarding employee retention and development.

## Future Work

For future analysis, the following steps are recommended:
1. **Detailed Role Analysis**: Conduct a more detailed analysis of other roles and their durations within the company.
2. **Expanded Dataset**: Incorporate additional datasets, such as employee performance and satisfaction scores, to gain a more comprehensive understanding.
3. **Interactive Dashboards**: Create interactive dashboards using tools like Tableau to better visualize and communicate findings.
