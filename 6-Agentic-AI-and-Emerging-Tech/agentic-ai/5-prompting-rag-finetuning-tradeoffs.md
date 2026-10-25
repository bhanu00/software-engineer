# Prompting, RAG, Fine-Tuning, and Traditional Software

## Scope

Choose between prompting, RAG, fine-tuning, traditional ML, and deterministic software.

## Decision guide

- Use prompting for behavior, instructions, formatting, and small changes.
- Use RAG for changing, private, or source-grounded knowledge.
- Use fine-tuning for repeatable behavior, style, or domain adaptation when data and evaluation justify it.
- Use traditional software for rules, calculations, authorization, and deterministic workflows.
- Use traditional ML when prediction, classification, or ranking is better served by labeled data.

## Architect questions

- Is the problem knowledge, behavior, prediction, or business logic?
- What data is available and how will it be evaluated?
- What are the update, rollback, privacy, and cost implications?
