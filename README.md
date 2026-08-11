# Hi, I'm Moiz Qureshi 👋

**Senior GenAI Engineer · RAG Systems · Agentic Pipelines · LLMOps**

Bangalore, India | [Email](mailto:themoizqureshi@gmail.com) | [LinkedIn](https://linkedin.com/in/themoizqureshi) | [GitHub](https://github.com/themoizqureshi)

---

## 🚀 About Me

I am a Senior GenAI / AI Engineer with 6+ years of software engineering experience spanning production LLM systems, full-stack development (.NET/React), and cloud architecture. 

As a founding engineer for an enterprise AI platform at **New American Funding** (a top-10 U.S. mortgage lender, via Speridian Technologies), I own production AI systems end-to-end — from multi-query RAG architectures and Python ADK agent fleets to RAGAS evaluation harnesses and reliability engineering.

* 🤖 **Scale**: Built conversational AI serving **5,000+ loan officers daily** and document-intelligence extraction pipelines processing **500,000+ mortgage documents per month**.
* 🛡️ **Resilience**: Engineered custom concurrency throttling (400 → 10 requests) that resolved production outages, and designed .NET gateways with Server-Sent Events (SSE) streaming.
* 🎯 **Evaluation**: Designed disaggregated RAGAS metrics (faithfulness, answer relevancy, context recall/precision) to isolate retrieval vs generation failures.

---

## 🛠️ Featured Open-Source Projects

Below are 5 hands-on portfolio repositories demonstrating production patterns across **LangChain 0.3 LCEL**, **LangGraph**, **LlamaIndex**, **RAGAS**, and **LLMOps**:

| Project | Stack | Highlights |
|---|---|---|
| 🔀 **[rag-chatbot-langchain](https://github.com/themoizqureshi/rag-chatbot-langchain)** | LangChain 0.3 · ChromaDB · BM25 · FastAPI · SSE | **Hybrid Search & SSE Streaming**: Custom `HybridRetriever` fusing sparse BM25 keyword search with dense ChromaDB similarity via Reciprocal Rank Fusion (RRF, $K=60$). Features 2-layer guardrails (heuristic + LLM relevance & grounding check) and token cost callbacks. |
| 🕸️ **[multi-agent-langgraph](https://github.com/themoizqureshi/multi-agent-langgraph)** | LangGraph · Tavily · ChromaDB · MemorySaver | **Multi-Agent Orchestration**: Sequential 3-agent graph (Researcher, Retriever, Writer) with Tenacity exponential backoff retries, a module circuit breaker, `operator.add` state reducers, and a stateful human-in-the-loop review checkpoint (`interrupt_before`). |
| 📊 **[rag-evaluation-pipeline](https://github.com/themoizqureshi/rag-evaluation-pipeline)** | RAGAS 0.2.6 · Gemini 2.0 Flash · HuggingFace | **Automated RAG Evaluation**: Dual-mode harness (local chain vs live REST API) scoring responses with Gemini 2.0 Flash (via OpenRouter) as judge and local `bge-small-en-v1.5` embeddings. Includes automated delta reporting and matplotlib charts. |
| 🔒 **[local-llm-rag-pinecone](https://github.com/themoizqureshi/local-llm-rag-pinecone)** | LlamaIndex 0.10+ · Ollama · Llama 3.2 · Pinecone | **Privacy-First Local RAG**: On-prem RAG API running local Llama 3.2 (3B) inference via Ollama and local PyTorch embeddings (`bge-small-en-v1.5`), paired with Pinecone serverless vector storage and FastAPI lifespan hooks. |
| ⚙️ **[llmops-pipeline](https://github.com/themoizqureshi/llmops-pipeline)** | MLflow · RAGAS · GitHub Actions · Python | **CI/CD Quality Gate**: GitHub Actions quality gate script failing builds (`sys.exit(1)`) on RAGAS metric regression. Features MLflow experiment tracking, prompt version registry (`prompts/registry.json`), and an A/B test harness. |

---

## 🧰 Technical Skills

* **LLMs & GenAI**: RAG, Hybrid Search (BM25 + Dense RRF), Multi-Query Retrieval, Intent Routing, Agent Fleets, Tool Calling / Function Calling, Structured Outputs, LangChain 0.3 LCEL, LangGraph, LlamaIndex, Google Vertex AI (Agent Engine / ReasoningEngine), Google ADK, Discovery Engine / Agentspace, Gemini (2.5 Pro/Flash), Anthropic Claude (Sonnet 4.6).
* **LLMOps & Quality**: RAGAS, MLflow Experiment Tracking, Prompt Engineering & Registry Versioning, A/B Testing, CI/CD Quality Gates.
* **Full-Stack & Backend**: C# (.NET 8), ASP.NET Core, EF Core, Python, TypeScript, JavaScript, React 18, Server-Sent Events (SSE), RESTful APIs.
* **Cloud & Infrastructure**: GCP (Vertex AI, Cloud Storage), Azure (Key Vault, Entra ID, Functions, Cosmos DB), Docker, GitHub Actions.
* **Engineering Practices**: Polly Resilience (Retries/Circuit Breakers), xUnit, New Relic APM, OWASP Security & PII Suppression.

---

## 📖 Production Case Studies

Detailed engineering deep-dives from production systems I've built and scaled:

* **[Building RAG for 5,000+ Loan Officers](https://themoizqureshi.com/posts/officer-scale-rag)** — Multi-query retrieval, intent routing, and disaggregated RAGAS evaluation on Google Discovery Engine / Agentspace.
* **[Reducing False Positives in Document Review](https://themoizqureshi.com/posts/doc-intel-model-migration)** — Migrating fraud detection from Gemini to Claude Sonnet 4.6 with a canonical fraud-signal taxonomy and category-level benchmarking.
* **[Replacing a Blank Screen with Streaming Chat](https://themoizqureshi.com/posts/streaming-chat-sse)** — Designing a unified .NET gateway for Vertex AI Agent Engine with real-time SSE token streaming and source attribution.
* **[Building a Secure AI Platform Foundation](https://themoizqureshi.com/posts/founding-secure-ai-backend)** — Establishing Clean Architecture .NET 8 backend, Azure Key Vault integration, and Entra ID authentication for 40+ features.

---

## 💼 Work Experience Snapshot

* **Technical Specialist — GenAI** @ *Speridian Technologies (Client: New American Funding)* | *Apr 2026 – Present*
  * Migrated production fraud-detection agent from Gemini to Claude Sonnet 4.6 after structured 4-category testing, cutting false positives.
  * Designed **Doc Intel Scanner** (Python ADK on Vertex AI) combining forensic PDF checks with Claude visual anomaly detection and a canonical fraud-signal taxonomy.
  * Built .NET agent gateway (`VertexAiAgentService`) consolidating multi-format NDJSON/SSE streaming endpoints.
* **Senior Software Engineer — GenAI** @ *Speridian Technologies (Client: New American Funding)* | *May 2025 – Mar 2026*
  * Founding engineer on the client's enterprise AI platform; established Clean Architecture .NET 8 backend, Azure Key Vault integration, and Entra auth used by 40+ features.
  * Designed production RAG on Google Agentspace serving **5,000+ daily loan officers** with multi-query retrieval and intent routing.
  * Shipped real-time token streaming using `fetch()` and `ReadableStream` with a producer-consumer channel pattern.
* **Senior Analyst — Full Stack Developer** @ *NTT Data* | *May 2022 – Apr 2025*
  * Built enterprise HRMS (.NET Core + React) for ~6,000 concurrent APAC users with zero-downtime blue-green deployments.
* **Associate System Engineer** @ *IBM* | *Jun 2021 – Apr 2022*
  * Built C# / ASP.NET MVC modules for American Express financial data processing.

---

## 📫 Connect With Me

* 📧 Email: [themoizqureshi@gmail.com](mailto:themoizqureshi@gmail.com)
* 💼 LinkedIn: [linkedin.com/in/themoizqureshi](https://linkedin.com/in/themoizqureshi)
* 🐙 GitHub: [github.com/themoizqureshi](https://github.com/themoizqureshi)
