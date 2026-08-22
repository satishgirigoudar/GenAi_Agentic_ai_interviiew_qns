# Most Repeated / High-Priority Questions — Batch 1 (Files 1–5)
*Questions that appeared across multiple different interviews. Ranked by frequency — prioritize these first.*

## Asked in almost every interview
1. Introduce yourself and explain your projects step by step with use cases.

## Asked very frequently
2. What chunking strategy did you use, and why? (sizes, overlap, sliding window, semantic)
3. What embedding model did you use, and how do dimensions/parameters/token limits work?

## Asked frequently
4. Which vector database(s) have you used (FAISS/PgVector/ChromaDB), and what search algorithm/metric does it use?
5. How do you deploy and run your FastAPI/Flask app — Docker, application server (Uvicorn/Gunicorn)?
6. What is dependency injection in FastAPI?
7. Python fundamentals — list vs. tuple / decorators / data structure trade-offs.
8. How do you reduce/handle hallucinations in a GenAI/RAG application?
9. How do you evaluate a RAG system, and what metrics matter (precision, faithfulness, etc.)?
10. What is OCR, how does it work, and how do you handle tables/images during extraction?

## Asked a couple of times
11. What is the difference between LangChain and LangGraph?
12. Explain the transformer architecture — attention, self-attention, multi-head attention.
13. How do you secure your application and cloud services against data leaks?
14. How do you handle database migrations, especially rolling back a column with existing data?
15. How would you convince a stakeholder your solution is better, without offending them?
16. What is idempotency? Give examples.
17. How do you scale a FastAPI service to handle high request volume (e.g., 100 req/sec) on limited resources?
18. What is Celery/Redis used for, and how do you implement background tasks in FastAPI?

---

## Why these matter
- **Q1** is a certainty in every interview — script and rehearse a tight 90-second version that naturally leads into your RAG/GenAI project.
- **Chunking + embeddings (Q2–3)** are the single most-tested RAG fundamentals — know exact numbers you used (chunk size, overlap %, embedding dimension) rather than generic answers.
- **Vector DB internals (Q4)** — interviewers often push past "which one did you use" into "how does it actually search" (HNSW, IVF, cosine similarity) — go one level deeper than your résumé bullet.
- **FastAPI deployment + DI (Q5–6)** show up as both conceptual and practical questions — have a Docker/Uvicorn/Gunicorn answer memorized with actual worker-count reasoning.
- **Stakeholder persuasion (Q15)** and **migration rollback (Q14)** were each hammered with 5+ follow-up variations in a single interview — these are "won't let go until you nail it" topics, worth over-preparing.

---
*This file will be updated with a combined ranking once Batch 2 (files 6–10) is processed.*


# Most Repeated / Highest-Priority Interview Questions
*Questions that recurred across multiple independent transcripts — prioritize preparing these first.*

## Asked in almost every interview
1. Introduce yourself and walk through your projects step by step, with use cases.
2. Explain your RAG architecture/workflow end-to-end (ingestion → chunking → embeddings → vector store → retrieval → prompt augmentation → generation).
3. Which vector database did you use, and why (FAISS, ChromaDB, etc.)?
4. Were the documents/knowledge base structured or unstructured?
5. What embedding model did you use, and how are embeddings generated?

## Asked very frequently
6. What is the difference between asyncio, multithreading, and multiprocessing — which is faster, and when do you use each? (ThreadPoolExecutor vs. ProcessPoolExecutor)
7. What is connection pooling, and how do you decide pool size? How does it relate to DB locks being held too long by external API calls inside a transaction?
8. Which cloud platform and services did you use? How would you scale for a sudden spike in users/requests?
9. Is your architecture microservices, monolith, or event-driven — and which fits a given use case (e.g., a banking product)?
10. How would you evaluate a RAG system? What metrics matter (precision/recall/F1/faithfulness), and how do you evaluate retrieval without labeled data?
11. How do you reduce/prevent hallucinations?
12. Have you worked with LangChain/LangGraph?
13. How many years of experience do you have? How would you rate yourself in Python, databases, ORMs, cloud, and DevOps?
14. What is your current CTC, and what is your notice period / exit timeline?

## Asked frequently
15. Given a schema, how would you generate a synthetic dataset at scale (100K–200K rows), with dynamic batch prompt variation, intent handling, and deduplication?
16. Design a fault-tolerant, idempotent transaction API with async notifications via a queue (Redis/RabbitMQ).
17. Write a decorator to convert dict keys between camelCase and snake_case, handling nested structures, with and without regex.
18. What chunking strategy did you use, what chunk size/overlap, and how do you avoid losing context across chunks?

## How to Use This
- **Almost every interview**: Rehearse until fluent — these are near-certain regardless of which interviewer you get.
- **Very frequently**: Know the concept plus one concrete example from your own project for each.
- **Frequently**: If your project touches any of these areas, expect the interviewer to go 4–5 questions deep rather than staying surface-level — prepare a full worked example, not just a definition.