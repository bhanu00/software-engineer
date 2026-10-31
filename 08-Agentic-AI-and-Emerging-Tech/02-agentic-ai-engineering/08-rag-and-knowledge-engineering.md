# RAG and Knowledge Engineering

Retrieval-Augmented Generation (RAG) is a data and access-control system around an LLM, not just embeddings plus a prompt. It retrieves source material at request time so an answer can use current, permission-appropriate evidence.

## Ingestion and Query Paths

```text
Ingestion: source -> parse -> classify -> redact/normalize -> chunk
           -> embed -> index with tenant, ACL, version, and provenance metadata

Query: authenticated principal -> permission filters -> retrieve candidates
       -> rerank/select -> build context with source IDs -> generate answer
       -> validate citations and policy -> return answer
```

## Design the Data Pipeline

1. **Source inventory:** Record owner, classification, source URI, version, timestamps, retention, and allowed audiences.
2. **Parsing:** Handle format-specific extraction, encoding, OCR, tables, and malformed input. Preserve page, section, and source offsets when possible.
3. **Chunking:** Choose boundaries that preserve meaning and citations. Measure chunk size and overlap against retrieval tasks rather than using a universal fixed value.
4. **Metadata:** Attach tenant/ACL labels, document version, source, effective date, and deletion key to every derived chunk.
5. **Embedding and indexing:** Version the embedding model and preprocessing pipeline. Re-index deliberately when either changes.
6. **Deletion and correction:** Propagate source updates and deletes to vector indexes, caches, summaries, and derived artifacts.

## Query-Time Retrieval

- Apply authorization filters **before** results can enter model context; do not rely on the model to ignore unauthorized content.
- Consider lexical, vector, and hybrid search, followed by reranking when it measurably improves relevance.
- Deduplicate overlapping chunks and keep a bounded context budget.
- Return source identifiers and spans so the application can validate citations.
- Provide a no-evidence or abstention path when relevance is below a calibrated threshold.
- Keep retrieval evaluation separate from answer-generation evaluation.

## Threats and Failure Cases

Retrieved documents are untrusted input. A document can contain prompt injection, stale instructions, or misleading content. Delimit content as data, constrain the model's tools, detect suspicious instructions where useful, and enforce policy outside the prompt. Also test ACL filter omissions, stale indexes, duplicate chunks, embedding drift, and poisoned source content.

## Evaluation Dataset

For each query, store expected source documents or spans, access principal/tenant, and expected answer properties. Measure recall@k or another retrieval metric, citation correctness, groundedness, abstention, and unauthorized-result rate. A strong answer from an unauthorized document is a security failure, not a quality success.

## Exercise

Build a small index from versioned technical documents. Compare fixed-size and section-aware chunking; lexical, vector, and hybrid retrieval; and retrieval with and without metadata ACL filters. Include a cross-tenant negative test and a delete/re-index test.

Related references: [retrieval concepts](../01-agentic-ai/3-retrival-concepts.md), [RAG architecture](../01-agentic-ai/4-rag-architecture.md), and [prompting/RAG/fine-tuning trade-offs](../01-agentic-ai/5-prompting-rag-finetuning-tradeoffs.md).