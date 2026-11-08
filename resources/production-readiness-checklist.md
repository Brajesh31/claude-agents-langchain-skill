# LangChain Application Production Readiness Checklist

Use this checklist before releasing an agent or RAG application to users.

## Architecture

- [ ] The architecture uses the simplest sufficient abstraction.
- [ ] Agent autonomy is justified by actual tool-selection needs.
- [ ] Inputs, outputs, and state transitions are explicit.
- [ ] Tool contracts and failure behaviors are documented.
- [ ] Model and integration versions are pinned or tracked.

## Security and Privacy

- [ ] API keys are stored outside source code.
- [ ] Tool permissions follow least privilege.
- [ ] User input and tool parameters are validated.
- [ ] Unrestricted dynamic code or shell execution is not exposed.
- [ ] Retrieved documents are filtered by access permissions before use.
- [ ] Sensitive data is not unnecessarily included in prompts or traces.
- [ ] External side effects require the right authorization.

## RAG Quality

- [ ] Source coverage is documented.
- [ ] Parsing and chunking have been tested on representative documents.
- [ ] Metadata and source identifiers are preserved.
- [ ] Retrieval relevance is measured independently.
- [ ] Answer groundedness and citation quality are evaluated.
- [ ] Empty and low-confidence retrieval is handled.
- [ ] Index updates, deletions, and versioning are defined.

## Reliability and Performance

- [ ] Timeouts and bounded retries are configured.
- [ ] Rate limits and concurrency are controlled.
- [ ] Streaming and async paths are tested if used.
- [ ] Tool and provider failures are handled.
- [ ] Latency, token usage, and cost are measured.
- [ ] Caching does not serve stale or unauthorized data.
- [ ] Fallback and escalation behavior is clear.

## Observability

- [ ] Model, prompt, and tool versions are recorded.
- [ ] Traces identify the request, tool calls, and retrieval sources.
- [ ] Secrets and sensitive values are redacted.
- [ ] Errors and failed tool calls are observable.
- [ ] Alerts and operational ownership are defined.

## Release Decision

- **Application version:**
- **Model / provider:**
- **Reviewer:**
- **Known limitations:**
- **Decision:** approve / conditional / reject
- **Review date:**
