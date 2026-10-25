# RAG Architecture

## Scope

RAG architecture, citations, abstention, access-aware retrieval, and data ingestion.

## Topics

- Document ingestion, parsing, normalization, chunking, and metadata.
- Embedding, indexing, retrieval, reranking, and context assembly.
- Citations, evidence provenance, answer grounding, and abstention.
- Tenant and document-level access control during retrieval.
- Ingestion versioning, freshness, deletion, re-indexing, and backfills.

## Architect questions

- What is the source of truth and how is freshness measured?
- How are unauthorized documents excluded before generation?
- What happens when evidence is missing or contradictory?
- Which retrieval and answer-quality metrics are release gates?
