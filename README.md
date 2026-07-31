# Hi, I'm Raghuram ðŸ‘‹

### AI-Native Developer | Agentic AI Systems | RAG | MCP | Enterprise AI Applications

I build practical AI systems that combine LLMs, deterministic business rules, retrieval, tool use, human review, evals, and production-style engineering to solve real-world business and customer problems.

`Python` `LangGraph` `FastAPI` `Gradio` `PostgreSQL` `pgvector` `ChromaDB` `MCP` `Docker` `Pydantic`

---

## ðŸ”­ Featured Projects

### â˜ï¸ [supportrouter-aws](https://github.com/raghuram-chittibomma/supportrouter-aws)
**AI customer support agent for a DTC electronics retailer, built on AWS Bedrock**

Classifies support requests, routes each task type to the lowest-viable Bedrock model, answers via RAG + Lambda tools over order/return/refund data, and escalates to a human for refunds over $100 or low-confidence cases â€” with quality and cost claims backed by versioned eval scorecards, not assumptions.
- API Gateway â†’ LangGraph on Lambda; Bedrock Converse, Guardrails, and Knowledge Bases over S3 Vectors (OpenSearch Serverless avoided on purpose)
- DynamoDB routing table driven by offline scorecards â†’ policy generate/adopt â†’ publish (lowest-viable model per task type)
- Isolated tool Lambdas (order / return / refund) with least-privilege IAM; refunds over $100 require human approval
- Separate eval plane: golden scenarios, live Bedrock candidates, LLM-as-judge, prompt-cache measurement, GitHub-first ADRs/releases
- Delivered via a GitHub-first SDLC with build-time roles (architect, implementation planner, code reviewer) served over MCP by [enterprise-sdlc-mcp](https://github.com/raghuram-chittibomma/enterprise-sdlc-mcp) â€” kept separate from the runtime agent
- Opt-in Bedrock AgentCore Runtime + Gateway MCP as dual-run stretch (quality/cost explicitly not measured)

`Python` Â· `AWS` Â· `Bedrock` Â· `LangGraph` Â· `CDK` Â· `DynamoDB` Â· `MCP`

### ðŸ“¦ [csr-order-exception-assistant](https://github.com/raghuram-chittibomma/csr-order-exception-assistant)
**Agentic assistant for customer service order investigation and resolution**

Investigates delayed, backordered, and exception-based orders by combining deterministic evidence gathering, policy-grounded RAG, and bounded agentic reasoning â€” with human approval required before any customer-facing recommendation.
- LangGraph investigation workflow over synthetic ERP data (Postgres)
- pgvector retrieval for policies and similar past cases
- Deterministic feasibility engine + human-in-the-loop review gate
- MCP tools for order/customer/inventory/policy lookup, shared across FastAPI + Gradio
- Golden eval cases for root cause, citation validity, and action acceptability

`Python` Â· `LangGraph` Â· `pgvector` Â· `MCP` Â· `FastAPI`

### ðŸ©º [clinical-decision-support](https://github.com/raghuram-chittibomma/clinical-decision-support)
**Multi-agent clinical workflow demonstrator (synthetic data only)**

Specialist agents debate a diagnosis under LangGraph orchestration; deterministic risk gates flag high-stakes cases and route them to a human reviewer before any conclusion stands.
- Multi-agent routing with bounded debate cycles
- Citation-backed RAG over guideline-style documents
- Deterministic safety/risk checks independent of the LLM
- Postgres + ChromaDB architecture, MCP tools shared across layers
- Labeled evaluation scenarios + automated tests

`Python` Â· `LangGraph` Â· `Postgres` Â· `Chroma` Â· `MCP`

### ðŸ—‚ï¸ [data-catalog-assistant](https://github.com/raghuram-chittibomma/data-catalog-assistant)
**Enterprise RAG-based data catalog and lineage assistant**

Semantic table discovery, lineage exploration, change-impact analysis, and validated natural-language-to-SQL â€” served from one core service through three interfaces.
- Dual-store architecture: Postgres (structured) + ChromaDB (semantic)
- RAG-scoped SQL generation with validation before execution
- Exposed via Gradio UI, FastAPI REST API, and a protocol-compliant MCP server
- Automated test coverage + GitHub Actions CI

`Python` Â· `RAG` Â· `MCP` Â· `FastAPI` Â· `Gradio`

### ðŸŽ« [support-ticket-triage-assistant](https://github.com/raghuram-chittibomma/support-ticket-triage-assistant)
**AI-assisted SDLC and support triage case study**

A GitHub-first record of building a support-ticket triage workflow end-to-end â€” requirements, agent-assisted implementation, testing, and review â€” documenting the AI-assisted development process itself, not just the output.
- Triage classification and routing logic
- Requirements â†’ issues â†’ PR-style development flow
- Test and evaluation baseline with a visible artifact trail

`Python` Â· `Agentic SDLC`

### ðŸ¥ [mn-dhs-encounter-toolkit](https://github.com/raghuram-chittibomma/mn-dhs-encounter-toolkit)
**Healthcare EDI validation and synthetic encounter data toolkit**

A Python toolkit for validating healthcare encounter files and generating realistic synthetic claims data inspired by payer/provider workflows.
- Synthetic claims, provider, and member data generation
- 837 encounter validation, 999/835-style response concepts
- Rule-based validation layers with traceable output

`Python` Â· `EDI` Â· `Healthcare Data`

---

## ðŸ§  AI-Native Engineering Principles  

- **Deterministic floor, agentic ceiling** â€” business-critical facts and constraints come from deterministic systems; agents reason *within* those boundaries, not around them.
- **Evidence before recommendation** â€” every AI output is grounded in retrieved policies, structured records, or traceable source documents.
- **Human review for consequential actions** â€” for customer, clinical, or financial decisions, AI assists; it doesn't silently execute.
- **Evals are part of the product** â€” golden cases, citation checks, and action-validity checks ship alongside the feature, not after it.
- **Tools reusable across interfaces** â€” the same capability is callable from UI, API, and MCP clients, not locked inside one demo screen.
- **Local-first demos, production-patterned architecture** â€” even synthetic-data projects get real tests, CI, and documented operating assumptions.

---

## ðŸ“« Connect

- GitHub: [raghuram-chittibomma](https://github.com/raghuram-chittibomma)
- LinkedIn: https://www.linkedin.com/in/raghuram-chittibomma-3312252/
- Email: raghuram.chittibomma@gmail.com
