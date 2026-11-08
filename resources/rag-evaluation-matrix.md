# RAG Evaluation Matrix

Evaluate retrieval and answer generation as separate components. A fluent answer can still be wrong when retrieval supplied irrelevant or incomplete context.

## Evaluation Setup

- **Dataset / version:**
- **Corpus snapshot:**
- **Embedding model:**
- **Vector store and configuration:**
- **Chunking configuration:**
- **Retriever and top-k:**
- **Reranker, if any:**
- **Generation model:**
- **Prompt version:**
- **Evaluator and date:**

## Test Cases

| Case ID | Query | Expected source / evidence | Required answer points | Abstain when unsupported? |
|---|---|---|---|---|
| R01 | | | | |
| R02 | | | | |
| R03 | | | | |

Include direct questions, paraphrases, multi-hop questions, ambiguous queries, no-answer questions, stale-document questions, and questions with conflicting source material.

## Retrieval Evaluation

| Metric / check | Definition | Result | Notes |
|---|---|---:|---|
| Recall@k | Relevant evidence retrieved within top k | | |
| Precision@k | Retrieved items that are relevant | | |
| MRR / ranking | Position of the first relevant result | | |
| Metadata filters | Correct source / tenant / permission filtering | | |
| Empty-result handling | Appropriate result when evidence is absent | | |

## Answer Evaluation

| Criterion | Pass condition | Result | Evidence |
|---|---|---|---|
| Correctness | Claims supported by evidence | | |
| Groundedness | No unsupported claims | | |
| Completeness | Required answer points are covered | | |
| Citation quality | Sources actually support the claims | | |
| Abstention | Unsupported questions are handled honestly | | |
| Privacy | No unauthorized source content is exposed | | |

## Failure Analysis

- **Retrieval failure:** relevant evidence missing or ranked too low.
- **Parsing failure:** source text or structure was lost during ingestion.
- **Chunking failure:** supporting context split or truncated.
- **Metadata failure:** source identity or access attributes missing.
- **Generation failure:** retrieved evidence ignored or misrepresented.
- **Evaluation failure:** expected answer or rubric is ambiguous.

For each failure, capture the query, retrieved documents, generated answer, root cause, and remediation.

## Release Gate

- [ ] Evaluation includes answerable and unanswerable questions.
- [ ] Retrieval and generation are scored separately.
- [ ] Tenant and document permissions are tested.
- [ ] Citations and source references are checked.
- [ ] Index freshness and deletion behavior are tested.
- [ ] Known limitations and dataset coverage gaps are documented.
