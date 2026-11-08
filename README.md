# LangChain Agents Skill

A Claude skill for developing LLM applications and agent workflows with LangChain. It covers agent construction, tool use, integrations, and retrieval-augmented generation (RAG), supported by focused reference guides.

## What This Skill Covers

- Understanding the building blocks used to create LangChain agents.
- Designing agent behaviour and connecting tools.
- Integrating models and external services into an application.
- Building retrieval-augmented generation pipelines.
- Connecting data sources and retrieving relevant context.
- Reviewing common implementation patterns before expanding an agent workflow.

## Repository Structure

- `SKILL.md`: Main skill instructions and framework overview.
- `references/agents.md`: Additional guidance on agent concepts and patterns.
- `references/integration.md`: Reference material for integrations.
- `references/rag.md`: Guidance for retrieval-augmented generation workflows.
- `LICENSE`: MIT License for this repository.

## When to Use It

Use this skill when planning or implementing an LLM application with LangChain, connecting tools to an agent, integrating model providers or services, or building a RAG workflow over external data. It can also help compare the responsibilities of agents, integrations, and retrieval components before implementation.

## Getting Started

1. Review `SKILL.md` to understand the framework concepts and intended workflow.
2. Identify whether the application needs an agent, a retrieval pipeline, or both.
3. Choose the required model and integrations.
4. Define tools and data access boundaries clearly.
5. Build a small end-to-end flow and test it with representative inputs.
6. Consult the relevant reference file for agents, integrations, or RAG details.

## Implementation Guidance

Keep each component focused. Avoid introducing an agent when a deterministic chain or direct function call is sufficient. For RAG systems, evaluate retrieval quality separately from answer generation so that poor context selection is not mistaken for a model-quality issue.

## License

Released under the MIT License. See [LICENSE](LICENSE) for details.
