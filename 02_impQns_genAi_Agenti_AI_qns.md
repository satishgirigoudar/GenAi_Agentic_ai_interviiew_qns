# Most Repeated / Highest-Priority Interview Questions
*Combined ranking across all 18 transcripts (Batch 1 + Batch 2) — prioritize preparing these first.*

## Asked in almost every interview
1. Introduce yourself and walk through your projects step by step, with use cases.
2. Explain your RAG architecture/workflow end-to-end (ingestion → chunking → embeddings → vector store → retrieval → prompt augmentation → generation).
3. Which vector database did you use, and why (FAISS, ChromaDB, PgVector, etc.)?
4. Were the documents/knowledge base structured or unstructured?
5. What embedding model did you use, and how are embeddings generated (dimensions, parameters, token limits)?
6. What chunking strategy did you use, and why (size, overlap, sliding window, semantic)?

## Asked very frequently
7. How do you reduce/prevent hallucinations?
8. How would you evaluate a RAG system? What metrics matter (precision/recall/F1/faithfulness), and how do you evaluate retrieval without labeled data?
9. Have you worked with LangChain/LangGraph? What's the difference between them?
10. What is the difference between asyncio, multithreading, and multiprocessing — which is faster, and when do you use each?
11. What is connection pooling, and how do you decide pool size?
12. How do you deploy and run your FastAPI/Flask app — Docker, application server (Uvicorn vs. Gunicorn)?
13. What is dependency injection in FastAPI?
14. Which cloud platform and services did you use? How would you scale for a sudden spike in users/requests?
15. Is your architecture microservices, monolith, or event-driven — and which fits a given use case (e.g., a banking product)?
16. Python fundamentals — list vs. tuple, decorators, data structure trade-offs.
17. What is OCR, how does it work, and how do you handle tables/images during extraction?
18. How many years of experience do you have? How would you rate yourself in Python, databases, ORMs, cloud, and DevOps?
19. What is your current CTC, and what is your notice period / exit timeline?

## Asked frequently
20. Explain the transformer architecture — attention, self-attention, multi-head attention.
21. How do you secure your application and cloud services against data leaks?
22. How do you handle database migrations, especially rolling back a column with existing data?
23. How would you convince a stakeholder your solution is better, without offending them?
24. What is idempotency? Give examples.
25. How would you configure FastAPI to handle high request volume (e.g., 100 req/sec) on limited resources?
26. What is Celery/Redis used for, and how do you implement background tasks in FastAPI?
27. Given a schema, how would you generate a synthetic dataset at scale (100K–200K rows), with dynamic batch prompt variation and deduplication?
28. Design a fault-tolerant, idempotent transaction API with async notifications via a queue (Redis/RabbitMQ).
29. Write a decorator to convert dict keys between camelCase and snake_case, handling nested structures, with and without regex.

## How to Use This
- **Almost every interview**: Rehearse until fluent — these are near-certain regardless of which interviewer you get.
- **Very frequently**: Know the concept plus one concrete example from your own project for each.
- **Frequently**: If your project touches any of these areas, expect the interviewer to go 4–5 questions deep rather than staying surface-level — prepare a full worked example, not just a definition.