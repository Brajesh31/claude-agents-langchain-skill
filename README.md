# LangChain Agents and RAG Skill

A Claude Code skill for building LLM-powered applications with LangChain. It covers agents, tool calling, model-provider integrations, retrieval-augmented generation (RAG), conversation context, vector stores, evaluation, and observability.

LangChain APIs and package boundaries evolve quickly. Use the examples in the skill and references as starting points, then verify imports and configuration against the official documentation for the versions installed in your project.

## What This Skill Covers

- Build LLM-powered application workflows.
- Create tool-using agents and define tool contracts.
- Connect model providers and external integrations.
- Load, split, embed, index, and retrieve documents.
- Build RAG applications with source metadata.
- Manage conversation context and memory patterns.
- Use vector stores, retrievers, and query patterns.
- Evaluate retrieval quality separately from answer quality.
- Trace, debug, and monitor application behavior.
- Handle tool errors, latency, and cost.

## When to Use It

Use this skill when building chatbots, question-answering applications, tool-using assistants, RAG pipelines, or workflows that connect language models with external data and services.

Do not use an agent loop by default. A direct model call, deterministic chain, or retriever can be simpler, faster, and easier to test. Add agent autonomy when dynamic tool selection or multi-step decisions are actually required.

## Installation

The package set depends on the model provider and integrations. The skill documents the core library and common provider packages:

~~~bash
python -m pip install -U langchain
python -m pip install langchain-openai
python -m pip install langchain-anthropic
~~~

Additional packages may be required for specific integrations, vector stores, or community loaders. Install only the providers and integrations your application uses.

Install the skill into Claude Code:

~~~bash
git clone https://github.com/Brajesh31/claude-agents-langchain-skill.git ~/.claude/skills/agents-langchain
~~~

## Usage

Invoke the skill:

~~~text
/agents-langchain
~~~

Provide the model provider, user interaction, data sources, expected tools, retrieval requirements, privacy constraints, and deployment environment.

## Architecture Choices

| Requirement | Starting point |
|---|---|
| One prompt and one model response | Direct model call |
| Deterministic sequence of steps | Runnable / deterministic chain |
| Search over a knowledge base | Retriever and RAG pipeline |
| Dynamic selection among tools | Agent |
| Stateful workflow with branching and cycles | Consider LangGraph |
| Document-centric ingestion and retrieval | Consider LlamaIndex when its abstractions fit better |

Choose the simplest architecture that meets the requirements. More abstractions do not automatically improve quality.

## Recommended Development Workflow

1. Define the user outcome and measurable acceptance criteria.
2. Choose direct model call, deterministic chain, retriever, or agent.
3. Select the model provider and required packages.
4. Define typed inputs, outputs, and tool contracts.
5. Restrict tool permissions and validate parameters.
6. For RAG, define source access, parsing, metadata, chunking, embeddings, and index lifecycle.
7. Evaluate retrieval relevance before evaluating generated answers.
8. Require answers to distinguish supported evidence from missing information.
9. Test tool errors, timeouts, invalid inputs, and empty retrieval.
10. Add tracing and cost monitoring.
11. Run realistic end-to-end tests before deployment.
12. Record versions, prompt revisions, evaluation results, and known limitations.

## RAG Pipeline

A typical RAG workflow has separate stages:

1. **Ingestion:** connect to approved data sources and load documents.
2. **Parsing:** extract text and structured content without losing useful context.
3. **Chunking:** split documents into retrievable units appropriate to the source.
4. **Metadata:** preserve source identifiers, permissions, timestamps, and other relevant attributes.
5. **Embedding and indexing:** create and store vectors using a compatible embedding model and vector store.
6. **Retrieval:** choose similarity, keyword, hybrid, filtering, and reranking strategies as appropriate.
7. **Generation:** answer using retrieved evidence, with clear handling for missing support.
8. **Evaluation:** measure retrieval relevance, answer correctness, citation quality, and refusal behavior separately.
9. **Maintenance:** update, delete, and version indexed content as source data changes.

## References Already Included

| File | Focus |
|---|---|
| [Agents guide](references/agents.md) | Agent creation, tools, execution patterns, and memory |
| [Integration guide](references/integration.md) | Providers, vector stores, integrations, and observability |
| [RAG guide](references/rag.md) | Document loading, chunking, embeddings, retrieval, and evaluation |

## Included Resources

- [Tool contract and safety template](resources/tool-contract-template.md): define inputs, outputs, permissions, validation, and side effects for each tool.
- [RAG evaluation matrix](resources/rag-evaluation-matrix.md): test retrieval and generated answers independently.
- [Production readiness checklist](resources/production-readiness-checklist.md): review secrets, access control, observability, reliability, and index maintenance.

## Security and Reliability

- Store provider API keys in environment variables or an approved secret manager.
- Never hard-code credentials or commit them to Git.
- Give tools the minimum permissions required.
- Validate and constrain tool inputs before external actions.
- Do not use unrestricted `eval` or shell execution on model-generated or user-supplied input.
- Add timeouts, retries, and bounded execution limits.
- Treat retrieved documents and tool outputs as untrusted content.
- Enforce source-level access controls before retrieval, not just in the prompt.
- Preserve source metadata so answers can be traced to evidence.
- Handle empty or low-confidence retrieval without inventing answers.
- Avoid logging secrets or unnecessary personal data.

## Repository Structure

~~~text
claude-agents-langchain-skill/
├── SKILL.md
├── README.md
├── LICENSE
├── references/
│   ├── agents.md
│   ├── integration.md
│   └── rag.md
└── resources/
    ├── production-readiness-checklist.md
    ├── rag-evaluation-matrix.md
    └── tool-contract-template.md
~~~

## External Resources

- [LangChain documentation](https://docs.langchain.com/)
- [Python API reference](https://reference.langchain.com/python/)
- [LangChain GitHub repository](https://github.com/langchain-ai/langchain)
- [LangSmith](https://smith.langchain.com/)

## License

Released under the MIT License. Copyright (c) 2026 Brajesh Kumar. See the root LICENSE file for the complete terms.
