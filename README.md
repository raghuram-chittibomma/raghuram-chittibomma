# Hi, I'm Raghuram 👋

### AI-Native Developer | Agentic AI Systems | RAG | MCP | Enterprise AI Applications

I build practical AI systems that combine LLMs, deterministic business rules, retrieval, tool use, human review, evals, and production-style engineering to solve real-world business and customer problems.

`Python` `LangGraph` `FastAPI` `Gradio` `PostgreSQL` `pgvector` `ChromaDB` `MCP` `Docker` `Pydantic`

---

## 🔭 Featured Projects

### 📦 [csr-order-exception-assistant](https://github.com/raghuram-chittibomma/csr-order-exception-assistant)
**Agentic assistant for customer service order investigation and resolution**

Investigates delayed, backordered, and exception-based orders by combining deterministic evidence gathering, policy-grounded RAG, and bounded agentic reasoning — with human approval required before any customer-facing recommendation.
- LangGraph investigation workflow over synthetic ERP data (Postgres)
- pgvector retrieval for policies and similar past cases
- Deterministic feasibility engine + human-in-the-loop review gate
- MCP tools for order/customer/inventory/policy lookup, shared across FastAPI + Gradio
- Golden eval cases for root cause, citation validity, and action acceptability

`Python` · `LangGraph` · `pgvector` · `MCP` · `FastAPI`

### 🩺 [clinical-decision-support](https://github.com/raghuram-chittibomma/clinical-decision-support)
**Multi-agent clinical workflow demonstrator (synthetic data only)**

Specialist agents debate a diagnosis under LangGraph orchestration; deterministic risk gates flag high-stakes cases and route them to a human reviewer before any conclusion stands.
- Multi-agent routing with bounded debate cycles
- Citation-backed RAG over guideline-style documents
- Deterministic safety/risk checks independent of the LLM
- Postgres + ChromaDB architecture, MCP tools shared across layers
- Labeled evaluation scenarios + automated tests

`Python` · `LangGraph` · `Postgres` · `Chroma` · `MCP`

### 🗂️ [data-catalog-assistant](https://github.com/raghuram-chittibomma/data-catalog-assistant)
**Enterprise RAG-based data catalog and lineage assistant**

Semantic table discovery, lineage exploration, change-impact analysis, and validated natural-language-to-SQL — served from one core service through three interfaces.
- Dual-store architecture: Postgres (structured) + ChromaDB (semantic)
- RAG-scoped SQL generation with validation before execution
- Exposed via Gradio UI, FastAPI REST API, and a protocol-compliant MCP server
- Automated test coverage + GitHub Actions CI

`Python` · `RAG` · `MCP` · `FastAPI` · `Gradio`

### 🎫 [support-ticket-triage-assistant](https://github.com/raghuram-chittibomma/support-ticket-triage-assistant)
**AI-assisted SDLC and support triage case study**

A GitHub-first record of building a support-ticket triage workflow end-to-end — requirements, agent-assisted implementation, testing, and review — documenting the AI-assisted development process itself, not just the output.
- Triage classification and routing logic
- Requirements → issues → PR-style development flow
- Test and evaluation baseline with a visible artifact trail

`Python` · `Agentic SDLC`

### 🏥 [mn-dhs-encounter-toolkit](https://github.com/raghuram-chittibomma/mn-dhs-encounter-toolkit)
**Healthcare EDI validation and synthetic encounter data toolkit**

A Python toolkit for validating healthcare encounter files and generating realistic synthetic claims data inspired by payer/provider workflows.
- Synthetic claims, provider, and member data generation
- 837 encounter validation, 999/835-style response concepts
- Rule-based validation layers with traceable output

`Python` · `EDI` · `Healthcare Data`

---

## 🧠 AI-Native Engineering Principles  

- **Deterministic floor, agentic ceiling** — business-critical facts and constraints come from deterministic systems; agents reason *within* those boundaries, not around them.
- **Evidence before recommendation** — every AI output is grounded in retrieved policies, structured records, or traceable source documents.
- **Human review for consequential actions** — for customer, clinical, or financial decisions, AI assists; it doesn't silently execute.
- **Evals are part of the product** — golden cases, citation checks, and action-validity checks ship alongside the feature, not after it.
- **Tools reusable across interfaces** — the same capability is callable from UI, API, and MCP clients, not locked inside one demo screen.
- **Local-first demos, production-patterned architecture** — even synthetic-data projects get real tests, CI, and documented operating assumptions.

---

## 📫 Connect

- GitHub: [raghuram-chittibomma](https://github.com/raghuram-chittibomma)
- LinkedIn: https://www.linkedin.com/in/raghuram-chittibomma-3312252/
- Email: raghuram.chittibomma@gmail.com
