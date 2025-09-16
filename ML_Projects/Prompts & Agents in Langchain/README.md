# 🤖 LLM & Agent-Based Automation Project

This project demonstrates different ways of using **Large Language Models (LLMs)** and **LangChain agents** for automation, search, and business analytics.


## Calling an LLM with a Basic Prompt

We start by calling OpenAI and HuggingFace (Mistral) models with a simple request:

**Prompt**:  
*"Explain briefly what quantum computing is, its advantages and current research. Answer ≤200 characters."*

**Observation**: Mistral produced more detailed, example-driven answers, while OpenAI gave a concise overview.


## Creating a Parameterized Prompt

Used **PromptTemplate** to create a flexible text generation template.

**Topics tested**:
- Bayesian methods in ML  
- Transformers in ML  
- Explainable AI  

### Results
- **OpenAI** → More concise, general summaries.  
- **Mistral** → Richer explanations with examples.  

Compared responses using **ModelLaboratory** to analyze differences between models systematically.



## Agent-Based Process Automation

Built a **ReAct agent** with `DuckDuckGoSearchResults` to automate literature search.

**Task**:  
*"Find 5 recent scientific publications about Artificial Intelligence from 2023–2024. Format strictly: 1. Title — Authors — Short summary 2. ..."*

**Observation**: DuckDuckGo handled the search queries better than SerpAPI in this case.



## Creating a Business Assistant Agent

Designed an **analytics assistant** with two tools:

- **Python REPL** → for calculations & forecasting.  
- **DuckDuckGo Search** → for live economic and weather data.  

**Task**:  
*"Estimate Brazil orange exports for 2025, considering weather, inflation, and global demand."*

### Results
- **Trend-based estimate** → ≈ 236 tons (based on ~7.65% average growth).  

**External factors**:
- **Weather**: mixed (drought in some regions, better in the South).  
- **Inflation**: moderate (~4.9% in Nov 2024).  
- **Demand**: increasing globally despite lower export values.  


## Key Takeaways

- **Model differences**: Mistral responses are more detailed, OpenAI more concise.  
- **Parameterized prompts** allow systematic testing of topics.  
- **Agents** enable automation of multi-step tasks (search + reasoning + reporting).  
- **Search instructions matter** → Adding stricter rules improves reliability.  
- **Business case**: Agent-based analytics can combine forecasting with external data sources.  
