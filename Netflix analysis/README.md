# Netflix Data Analysis

## Introduction
Netflix, a leading streaming service provider, offers a plethora of content ranging from movies, TV shows, documentaries, and more. This project aims to uncover patterns and insights from the Netflix dataset using data science techniques. The analysis highlights genre distributions, content by country, and the most prolific directors on the platform.

## Objectives

- Analyze the Netflix dataset to uncover trends and insights.
- Identify key statistics and patterns within the dataset.
- Present findings in a clear and understandable manner.

## Dataset Structure
The dataset used in this analysis includes a wide range of attributes that provide a rich basis for analysis and visualization.

<img width="334" alt="Снимок экрана 2024-07-24 в 23 32 03" src="https://github.com/user-attachments/assets/5bc215e5-dffd-4e7a-9e96-59ebd7932782">


## Methodology

1. **Data Cleaning and Preparation:**

- **Handling Missing Values:** Filled missing values in director, cast, and country with 'NA'. Converted date_added to a datetime format.
- **Duplicate Checks:** Ensured there were no duplicate entries in the dataset.

2. **Data Exploration:**

- **Content Distribution:** Analyzed the distribution of movies vs TV shows.
- **Country-wise Analysis:** Examined the number of shows produced by different countries.
- **Temporal Analysis:** Investigated trends in content addition over the years.

3. **Visualizations:**

- **Content by Type:** Bar charts showing the number of movies and TV shows.
- **Top Countries by Content:** Bar charts highlighting the top content-producing countries.
- **Yearly Additions:** Line graphs depicting the number of shows added to Netflix each year.

## Key Insights:

- There is strong focus on Dramas and Comedies, which could be due to their popularity among viewers or a strategic content acquisition approach.
- The United States is the top content producer with 2,734 titles.
- New content is most actively added in December.
- The year 2019 saw the highest number of content additions.
- 21% of all countries has minimal presence on Netflix.
- TV shows have an average duration of about 1.78 minutes per episode, which seems unusually low and may indicate a data inconsistency.
- The top ten directors featured in Netflix titles predominantly work in the Stand-Up genre and originate from Mexico or the United States.

## Recommendations

- **Content Acquisition**: Focus on acquiring content in popular genres to attract a larger audience.
- **International Content**: Increase the variety of international content to cater to a global audience.
- **Content Production**: Invest in producing original content in genres and regions showing growth potential.

## Conclusion
The analysis of the Netflix dataset has provided valuable insights into the platform's content library. Key findings include the dominance of certain genres, trends in content production, and the contribution of top directors and actors. These insights can help Netflix in strategic decision-making regarding content acquisition, production, and marketing.

## Future Work
Future analyses could delve deeper into:

- Trends over time, examining how content genres and types have evolved.
- User ratings and reviews to gauge content reception.
- Predictive analytics to forecast future content trends.

## Dashboard
The dashboard can be found in Tableau Public [here](https://public.tableau.com/app/profile/sofia.petrova/viz/NetflixContentDistributionDashboard_17117495835710/Dashboard1). It focuses on the distribution of Netflix content across various categories. The dashboard provides a detailed analysis of the types of content available on Netflix, including genre distribution, release years, and the geographical origin of the content.

<img width="1264" alt="Снимок экрана 2024-07-24 в 23 55 10" src="https://github.com/user-attachments/assets/09b366cd-d243-413b-aa81-10a0239681e4">
