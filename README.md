# Hey, I'm Moiz 👋

AI Engineer building production LLM systems — agentic RAG, multi-agent orchestration, and LLMOps pipelines that actually ship.

Currently at **Speridian Technologies** as an LLM/GenAI SME, where I've built conversational AI adopted by 5,000+ loan officers and document extraction pipelines processing 500K+ mortgage documents monthly at ~99% accuracy.

5 years of backend engineering under the hood (CQRS, event sourcing, distributed systems on .NET + Azure/GCP) — so I build AI that holds up in production, not just in demos.

---

## 🤖 AI / LLM Portfolio

Five projects built in sequence — each one solves a real problem that the previous one exposed.

---

### 1 · [RAG Chatbot](https://github.com/themoizqureshi/rag-chatbot-langchain) — LangChain · ChromaDB · Gemini · Streamlit
> *"LLMs hallucinate. RAG is the fix."*

PDF Q&A chatbot grounded entirely in source documents. Built with LangChain 0.3 LCEL, ChromaDB, Google `text-embedding-004`, and LangSmith observability. The system prompt design here — forcing the LLM to only answer from retrieved context — became the baseline that Project 2 rigorously evaluated.

**Key decisions:** chunk size 1000/overlap 200 tuned via downstream RAGAS scores · LCEL pipe operator for composable, traceable chains · `st.session_state` to avoid re-initialising ChromaDB on every message (saves 3–5s per response)

---

### 2 · [RAG Evaluation Pipeline](https://github.com/themoizqureshi/rag-evaluation-pipeline) — RAGAS · Gemini-as-Judge · LangSmith · pandas
> *"It seems to work is not an engineering measurement."*

Automated evaluation pipeline for RAG systems. Hand-crafted Q&A dataset at 3 difficulty levels, RAGAS scoring (faithfulness / answer relevancy / context recall / context precision), delta comparison reports, and LangSmith per-question traces that show exactly *where* your system fails — retrieval or generation.

**Results:** +23.6% faithfulness · +19.1% answer relevancy through prompt iteration alone. Context recall failures required changing the retrieval layer, not the prompt — you'd never know that from aggregate scores.

---

### 3 · [Local LLM RAG + FastAPI](https://github.com/themoizqureshi/local-llm-rag-pinecone) — Llama 3.2 · Ollama · Pinecone · LlamaIndex · Docker
> *"What if you can't send your documents to a cloud API?"*

Same RAG concept — but cloud-agnostic. Llama 3.2 runs locally via Ollama (data never leaves the machine). BAAI/bge-small-en-v1.5 embeddings run locally (MTEB-ranked, no API key). Pinecone handles vector storage. Exposed as a proper FastAPI REST service with Docker support.

**Key decisions:** FastAPI lifespan pattern loads the 130MB model once at startup, not per-request · `request_timeout=120s` on Ollama to handle CPU inference latency · Intentional LlamaIndex usage (vs LangChain in P1) to show framework-agnostic thinking

---

### 4 · [Multi-Agent Research Assistant](https://github.com/themoizqureshi/multi-agent-langgraph) — LangGraph · Gemini · Tavily · Human-in-the-Loop
> *"A single LLM call can't do everything well. Specialise."*

Three agents orchestrated by LangGraph: **Researcher** (Tavily web search) · **Retriever** (ChromaDB local docs) · **Writer** (Gemini synthesis). A human-in-the-loop `interrupt_before` checkpoint pauses the graph before the final report — you approve or add feedback before it completes.

**Key decisions:** `Annotated[List, operator.add]` state accumulation so agents' results merge, not overwrite · routing via `completed_agents` state decouples graph topology from hard-coded order · agents as pure `(state) -> dict` functions for isolated unit testing

---

### 5 · [LLMOps Pipeline](https://github.com/themoizqureshi/llmops-pipeline) — MLflow · RAGAS · GitHub Actions · Prompt Versioning
> *"How do you know when a prompt change breaks your system before users do?"*

The answer: you don't — unless you build this. Prompt versioning as code (files + `registry.json`), MLflow experiment tracking with run comparison UI, A/B testing harness, and a GitHub Actions CI/CD pipeline that runs RAGAS on every push and **fails the build** if any metric drops below threshold.

**Key decisions:** path-based CI trigger (`src/**`, `prompts/**`) — README changes don't burn API quota · 0.07 threshold buffer absorbs LLM-as-judge variance (±0.03) while still catching real regressions (typically >0.10 drop) · `sys.exit(1)` as the CI contract — simplest possible quality gate

---

## 🏭 What I've Shipped at Work

**Enterprise Conversational AI — Vertex AI · Gemini · Microsoft 365**
Agentic RAG chatbot across SharePoint, OneDrive, and Outlook. Tool calling for intent routing, query expansion, session-based enterprise search, chain-of-thought reasoning, Gemini streaming responses. Adopted by **5,000+ loan officers**. Reduced document retrieval time by **70%**.

**Document Validation AI — Google Discovery Engine · Gemini · GCP**
Trained Google Discovery Engine for structured field extraction from mortgage PDFs — model-level document understanding, not OCR. **~99% field-level accuracy**. Eliminated manual verification for **80%+ of documents**. Processes **500K+ documents/month**.

---

## 🛠 Stack

```
LLMs & AI     Vertex AI · Gemini · LangChain · LangGraph · LlamaIndex
              Ollama · Llama 3.2 · RAGAS · MLflow · LangSmith
Retrieval     ChromaDB · Pinecone · Google Discovery Engine · Tavily
              BAAI/bge-small · text-embedding-004
Backend       Python · C# · .NET 8 · FastAPI · TypeScript
Cloud         GCP (Vertex AI, Agent Builder, GCS) · Azure (Functions, App Services, DevOps)
Architecture  Microservices · CQRS · Event Sourcing · Agentic Workflows
Infra         Docker · GitHub Actions · CI/CD · New Relic
```

---

## 📬 Let's Talk

Open to **Applied AI Engineer** and **Senior LLM Engineer** roles — product companies, AI-native startups, and ambitious enterprise AI teams.

[LinkedIn](https://www.linkedin.com/in/themoizqureshi) · [themoizqureshi@gmail.com](mailto:themoizqureshi@gmail.com) · Bangalore (open to remote)
