# 🤖 LLM & Agent-Based Automation Project

This project demonstrates different ways of using **Large Language Models (LLMs)** and **LangChain agents** for automation, search, and business analytics.

---

## 1. 📌 Calling an LLM with a Basic Prompt

We start by calling OpenAI and HuggingFace (Mistral) models with a simple request:

**Prompt**:  
*"Explain briefly what quantum computing is, its advantages and current research. Answer ≤200 characters."*

- **OpenAI Response** → More general, high-level explanation.  
- **Mistral Response** → More specific, included examples (Shor’s and Grover’s algorithms).

👉 **Observation**: Mistral produced more detailed, example-driven answers, while OpenAI gave a concise overview.

---

## 2. 📝 Creating a Parameterized Prompt

We used **PromptTemplate** to create a flexible text generation template.

**Topics tested**:
- Bayesian methods in ML  
- Transformers in ML  
- Explainable AI  

### Results
- **OpenAI** → More concise, general summaries.  
- **Mistral** → Richer explanations with examples.  

We then compared responses using **ModelLaboratory** to analyze differences between models systematically.

---

## 3. 🔍 Agent-Based Process Automation

We built a **ReAct agent** with `DuckDuckGoSearchResults` to automate literature search.

**Task**:  
*"Find 5 recent scientific publications about Artificial Intelligence from 2023–2024. Format strictly: 1. Title — Authors — Short summary 2. ..."*

### Results
The agent performed iterative searches and compiled results such as:

1. **Generative AI at Work** — Brynjolfsson, E. et al. — Impact of AI assistants on productivity.  
2. **The Use of AI in Research** — The Guild Task Force — Institutional strategies for integrating AI.  
3. **Artificial Intelligence and Its Applications** — Overview of AI across multiple domains.  
4. **Generative AI: Societal Impact & IS Research** — Trends and opportunities for research.  
5. **AI Ensemble for Gravitational Waves** — Application of AI in astrophysics.  

👉 **Observation**: DuckDuckGo handled the search queries better than SerpAPI in this case.

---

## 4. 📊 Creating a Business Assistant Agent

We designed an **analytics assistant** with two tools:

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

👉 **Final Forecast**: ~236 tons in 2025, with note that external shocks could shift this number significantly.

---

## 📌 Key Takeaways

- **Model differences**: Mistral responses are more detailed, OpenAI more concise.  
- **Parameterized prompts** allow systematic testing of topics.  
- **Agents** enable automation of multi-step tasks (search + reasoning + reporting).  
- **Search instructions matter** → Adding stricter rules improves reliability.  
- **Business case**: Agent-based analytics can combine forecasting with external data sources.  
