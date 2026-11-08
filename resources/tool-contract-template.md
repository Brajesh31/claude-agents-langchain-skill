# LangChain Tool Contract and Safety Template

Define each tool before exposing it to an agent. A tool description is part of the agent's decision interface, so it must be precise and must not promise capabilities the implementation does not provide.

## Tool Identity

- **Tool name:**
- **Purpose:**
- **Owning service / system:**
- **Maintainer:**
- **Read-only or state-changing:**

## Input Contract

| Input | Type | Required? | Validation | Bounds |
|---|---|---|---|---|
| | | | | |
| | | | | |

- **Schema validation:**
- **Default behavior:**
- **Invalid input response:**
- **Rate limits:**

## Output Contract

- **Return type / schema:**
- **Success fields:**
- **Error representation:**
- **Maximum output size:**
- **Sensitive fields to redact:**
- **Provenance or source references:**

## Permissions and Side Effects

- **Permissions required:**
- **Resources accessible:**
- **External side effects:**
- **Human approval required for:**
- **Idempotency behavior:**
- **Audit trail:**

## Reliability

- **Timeout:**
- **Retry policy:**
- **Maximum retries:**
- **Fallback behavior:**
- **Observability / trace fields:**

## Test Cases

- [ ] Valid input returns the documented output.
- [ ] Missing required input is rejected.
- [ ] Malformed input is rejected safely.
- [ ] Unauthorized access is denied.
- [ ] External service errors are handled.
- [ ] Timeouts and retries are bounded.
- [ ] Side effects are not repeated unexpectedly.
- [ ] Secrets and sensitive data are not exposed.

## Agent-Facing Description

Write a concise description that states what the tool does, when it should be used, required inputs, and important limitations.

**Description:**
