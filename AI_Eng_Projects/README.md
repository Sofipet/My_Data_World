# AI Engineering Projects

This collection highlights practical AI systems I’ve built, with a focus on end-to-end product design: from structured pipelines and LLM integration to evaluation, deployment, and user-facing applications.

## Tools & Libraries

- **Python**: Pandas, NumPy, Pydantic
- **LLM / AI Engineering**: OpenAI API, LangChain, prompt engineering, structured outputs
- **Retrieval-Augmented Generation (RAG)**: Chroma, embeddings, reranking, evidence-grounded generation
- **Agentic Workflows**: bounded tool-based agents, lightweight orchestration, analytical question answering
- **APIs & Backend**: FastAPI
- **Deployment**: Docker, Render, Streamlit, Hugging Face Spaces
- **Evaluation & Observability**: LangSmith, structured evaluation pipelines, manual review frameworks
- **Frontend / Product UI**: HTML, CSS, JavaScript

## Contents

- [📌 Customer Escalation Resolution Copilot](https://github.com/Sofipet/customer-escalation-copilot):  

  A retrieval-augmented support copilot for quote-approval escalations. The system retrieves internal guidance, identifies likely issues, surfaces conflicts or stale documentation, and recommends the next operational step in a structured format. Built as a **decision-support product**, it includes a custom FastAPI app, structured evaluation, protected live mode, and Dockerized deployment. 

- [🎥 YouTube EmotionScope](https://github.com/Sofipet/youtube-emotionscope):  

  An LLM-first analytics app for exploring the emotional structure of YouTube comment sections. Given a video link, the system analyzes comments, classifies emotions, aggregates them into dashboard-ready outputs, generates a short contextual summary, and supports a bounded insight layer for follow-up analytical questions. Built as a **compact analytics product** with a deterministic core pipeline, lightweight tool-based agent layer, evaluation artifacts, and Dockerized deployment.
## Focus

- turning LLM capabilities into usable product workflows
- combining deterministic pipelines with bounded model-based reasoning
- evaluating AI systems beyond surface-level output quality
- building apps that are not only functional, but also interpretable and deployable
