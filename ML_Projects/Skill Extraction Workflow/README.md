# 🔍 Skill Extraction Workflow  

This project analyzes Data Science job vacancies collected from DOU.ua to identify the most in-demand skills on the Ukrainian job market. To ensure accuracy and eliminate noise, the analysis follows a three-stage workflow.


## Raw WordCloud (Baseline Visualization)  
A WordCloud generated directly from vacancy text provides a general impression of the vocabulary used in job descriptions.  
However, this approach mixes technical terms with irrelevant narrative words such as *“experience,” “team,” “company,”* and *“responsibilities.”*

Result: **Visually appealing but analytically noisy.**



## GPT-Based Skill Extraction 
To obtain a cleaner signal, each job description is processed using an LLM prompt. The cleaned text is used to generate a refined WordCloud focused on Data Science terminology.

Result: **Clearer skill representation (Python, SQL, ML, NLP, Deep Learning).**  

## N-gram Analysis  
To identify skill phrases, the text is further analyzed using **N-grams**. This reveals the most frequently mentioned multi-word skills across vacancies.

Result: **A precise, data-driven view of the most demanded skill combinations.**

## Final Conclusion

- Raw WordClouds provide only a high-level view and are strongly affected by non-technical vocabulary.  
- GPT extraction improves quality by retaining only relevant information.  
- N-grams unlock the real structure of employer demands by identifying multi-word skills.  

## Tools & Technologies
- **Selenium**, **BeautifulSoup**, **Requests** — scraping vacancies  
- **NLTK**, **N-grams**, **WordCloud** — text analysis and feature extraction  
- **OpenAI API** — skill extraction with GPT  

