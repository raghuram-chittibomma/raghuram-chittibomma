# Hi, I'm Raghuram 👋

### AI-Native Developer | Agentic AI Systems | RAG | MCP | Enterprise AI Applications

I build practical AI systems that combine LLMs, deterministic business rules, retrieval, tool use, human review, evals, and production-style engineering to solve real-world business and customer problems.

`Python` `AWS Bedrock` `LangGraph` `FastAPI` `Gradio` `PostgreSQL` `pgvector` `ChromaDB` `MCP` `Docker` `Pydantic`

---

## 🔭 Featured Projects

### ☁️ [supportrouter-aws](https://github.com/raghuram-chittibomma/supportrouter-aws)
**AI customer support agent for a DTC electronics retailer, built on AWS Bedrock**

Classifies support requests, routes each task type to the lowest-viable Bedrock model, answers via RAG + Lambda tools over order/return/refund data, and escalates to a human for refunds over $100 or low-confidence cases — with quality and cost claims backed by versioned eval scorecards, not assumptions.
- API Gateway → LangGraph on Lambda; Bedrock Converse, Guardrails, and Knowledge Bases over S3 Vectors (OpenSearch Serverless avoided on purpose)
- DynamoDB routing table driven by offline scorecards → policy generate/adopt → publish (lowest-viable model per task type)
- Isolated tool Lambdas (order / return / refund) with least-privilege IAM; refunds over $100 require human approval
- Separate eval plane: golden scenarios, live Bedrock candidates, LLM-as-judge, prompt-cache measurement, GitHub-first ADRs/releases
- Delivered via a GitHub-first SDLC with build-time roles (architect, implementation planner, code reviewer) served over MCP by [enterprise-sdlc-mcp](https://github.com/raghuram-chittibomma/enterprise-sdlc-mcp) — kept separate from the runtime agent
- Opt-in Bedrock AgentCore Runtime + Gateway MCP as dual-run stretch (quality/cost explicitly not measured)

`Python` · `AWS` · `Bedrock` · `LangGraph` · `CDK` · `DynamoDB` · `MCP`

### 🎓 [college-admission-app](https://github.com/raghuram-chittibomma/college-admission-app)
**End-to-end college admissions planner with hybrid scoring and grounded AI**

Helps a family organize a high-stress planning process — school research, shortlist, fit/cost cues, applications, and a final decision — in one full-stack workspace instead of spreadsheets and one-off AI chats. AI is a core capability (research, compare, coaching), but admit odds stay on a deterministic scoring floor with labeled estimates, provenance, and confidence rather than vibes-based answers.
- Shared College Knowledge Base (Scorecard + Common Data Set + LLM research) with field provenance; separate student workspaces for shortlists, assessments, and trackers
- Hybrid admit %: rule-table primary estimate + factor breakdown; LLM explains and may offer a secondary opinion without overriding the planning %
- My Colleges hub: batch research / student assessment / compare, sticky decision table, fact matrix + AI narrative grounded in the research package
- Soft journey UI (profile → discover → assess/compare → apply/track → decide) on Next.js + FastAPI + PostgreSQL/pgvector
- GitHub-first delivery with durable docs/ADRs, CI, Playwright smoke, and build-time SDLC agents via [enterprise-sdlc-mcp](https://github.com/raghuram-chittibomma/enterprise-sdlc-mcp)

`Python` · `FastAPI` · `Next.js` · `PostgreSQL` · `pgvector` · `OpenAI` · `MCP`

### 🧰 [enterprise-sdlc-mcp](https://github.com/raghuram-chittibomma/enterprise-sdlc-mcp)
**Reusable build-time SDLC agent catalog, served over MCP**

A shared, versioned definition of *how* AI coding agents deliver software — so every project doesn't reinvent its own agent roles and review bar. One catalog of agents (Product Analyst, Solution Architect, Code Reviewer, etc.) and checklists is installed per-project and served consistently across repos and teams via MCP, instead of copy-pasted or drifting between projects.
- 9 agent roles + 29 skills — generic SDLC checklists (PR review, architecture review, application security, dependency/supply-chain, CI/CD pipeline, incident postmortems) plus stack-specific technical checklists (CDK, IAM least privilege, Bedrock Guardrails, DynamoDB data modeling, API contracts)
- Every skill is tagged with *when* it applies (always vs. stack-specific like AWS/FastAPI/LLM-backed) and every agent declares a machine-readable code-modify permission and file-path allowlist, not just prose a human has to trust
- Deterministic `{{project.*}}` placeholder resolution from each consuming repo's own manifest, with a `validate_manifest` check so a missing key surfaces before it leaks into a live prompt
- Installed editable into each consuming project's own venv; no cross-repo path coupling, so it scales to many independent projects
- The core PR review checklist enforces a Blocker/Major/Minor severity model with cited file+line evidence, not a pass/fail vibe check

`Python` · `MCP` · `SDLC Tooling`

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
- **Cost is a design constraint** — route each task to the lowest-viable model, not the biggest one, and default cloud infrastructure to a near-zero-cost idle state when not in active use.

---

## 📫 Connect

- GitHub: [raghuram-chittibomma](https://github.com/raghuram-chittibomma)
- LinkedIn: https://www.linkedin.com/in/raghuram-chittibomma-3312252/
- Email: raghuram.chittibomma@gmail.com
