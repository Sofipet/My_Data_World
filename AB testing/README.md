# A/B Testing

## Overview
This project involves a detailed A/B testing analysis of 2 cases aimed at improving user engagement on a website and while playing the game Cookie Cats respectively. The goal was to determine the effectiveness of a new feature by comparing it to the current version. The analysis includes data preprocessing, statistical testing, and result interpretation to make informed business decisions.

## Project Details

### Case 1: Design Change
**Objective:** To determine if a new version of the product page raises the conversion rate from 13% to 15%.

## Methodology
### 1. Data Collection
- Data was collected from website logs over a period of 30 days.
- Users were randomly assigned to either the control group (current version) or the treatment group (new feature).

### 2. Exploratory Data Analysis
   - Visualized the distribution of key metrics.
   - Identified any significant patterns in the data.

### 3. Test Design
- **Null Hypothesis (H0):** The new design does not significantly improve user engagement.
- **Alternative Hypothesis (H1):** The new design significantly improves user engagement.

### 4. Statistical Analysis
- Used a z-test for calculations since we have a very large sample.
- Calculated p-value to determine the statistical significance as well as confindence intervals.

## Key Insights
- **Conversion Rate:** We couldn't reject the null hypothesis 𝐻0, so the new design is likely to be similar to our baseline rather than the 15% target we were hoping for. So the strategy as for design development should be changed or the design should remain as it is:)

### Case 2: Feature Change
**Objective:** To determine if moving the gate 10 levels later has any effect on users stopping playing the Cookie Cats game sooner or later in terms of their number of days since installing the game.

## Methodology
### 1. Data Collection
- Data was collected from the app over a period of 30 days.
- When each player installed the game, he was randomly assigned to either gate_30 or gate_40.

### 2. Exploratory Data Analysis
   - Visualized the distribution of key metrics.
   - Identified any significant patterns in the data.

### 3. Test Design
- **Null Hypothesis (H0):** The difference between the two versions in player retention is not statistically significant.
- **Alternative Hypothesis (H1):** The difference between the two versions in player retention is statistically significant.

### 4. Statistical Analysis
- Used both z-test and chi quadrat test for calculations.
- Calculated p-value to determine the statistical significance as well as confindence intervals.

## Key Insights
- **Retention Rate:** We rejected the null hypothesis 𝐻0, which means that the difference between user behavior in different versions of the game is statistically significant. So the gate_30 version really gives better retention 7 days after installing the game than the gate_40 version. This is evidence that moving the gate from level 30 to level 40 is a bad idea in the context of keeping users in the game longer.

## Conclusion
This A/B testing project provides a thorough analysis of user behavior changes in response to modifications. The insights gained can guide strategic decisions in web and mobile design to optimize user engagement and retention.
