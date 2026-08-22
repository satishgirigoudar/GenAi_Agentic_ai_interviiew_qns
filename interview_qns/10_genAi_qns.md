# Python / Gen AI Interview — Practice Questions
*Source: Interview transcript, 30-07-2026 (session 2)*

## Introduction
1. Self-introduction and step-by-step explanation of projects with real-world use cases.

## Live Coding
2. Find all pairs in an array whose sum equals a given value (sum=9).
3. Find the second largest number in the list [5,5,6,3,6,2,6,3,2,5,3,2,1] without using any predefined functions or data structures like set.

## Healthcare AI Project (Donor Matching)
4. Can you explain the healthcare AI project you mentioned earlier?
5. Explain the healthcare AI project in detail: problem statement, brainstorming, design, and deployment.
6. Which country is the client based out of?
7. Why use AI and semantic search for donor matching instead of just basic database filters?

## Embeddings & LLM Parameters
8. If you use model A for embeddings during ingestion, but a different model for retrieval/query, what issues can arise?
9. What happens if you use different embedding models for ingestion and retrieval? Will performance and quality improve or worsen, and why?
10. Can you explain temperature, top-p, and top-k in the context of language models?

---
*Total: 10 questions*

# Python / Gen AI Interview — Practice Questions
*Source: Interview transcript, 31-07-2026 (session 2)*

## Introduction & Background
1. Introduce yourself and explain your projects step by step with use cases.
2. Which Python frameworks, tools, or technologies have you used?

## RAG for Scanned PDFs (Images + Diagrams)
3. How would you design an end-to-end RAG pipeline for a 100-page scanned PDF (images only), so that when a user asks a question about a process, the system extracts relevant text and diagrams from the images and returns both the answer and the related image?
4. How will you associate the answer with the relevant image and display both together in a RAG pipeline for scanned PDFs?
5. How did you extract the images (not just text) from the scanned PDF for use in your pipeline?
6. Where will you keep/store the extracted image after pulling it from the PDF?
7. Have you used graph (graph databases or graph structures)?

## LangGraph — Checkpointing & Execution
8. What is checkpointing?
9. Write a program which uses a checkpointer in LangGraph.
10. What will happen after compiling the graph with a checkpointer in LangGraph?
11. Do we need a thread ID or similar concept to invoke the checkpoint when running the graph, or is it configurable?
12. How do we invoke the graph execution with the checkpointer and thread/session ID?
13. Can you write the code statement to invoke the graph with a thread/session ID for checkpointing?
14. What happens if we use app.invoke instead of graph.invoke?
15. What does the statement `result = graph.invoke(input_data, thread_id="item_3234")` do in the context of LangGraph with a checkpointer?
16. How do we resume a workflow execution using the thread ID in LangGraph?
17. What are some interrupts that we have in the graph?
18. Why do we use a read anchor in LangGraph?

## RAG Evaluation & Monitoring
19. What is reranking in the pipeline?
20. Have you worked on any evaluation framework? How will you evaluate that the pipeline you have built is effective?
21. How do you evaluate if your GenAI pipeline is working fine?
22. What is the purpose of using LangSmith in your GenAI pipeline?
23. What is the difference between invoke and stream?

## Concurrency in Python
24. What is the difference between multithreading and asyncio in Python?
25. When should we use asyncio, multithreading, and multiprocessing in Python?

## FastAPI at Scale
26. How would you design a FastAPI REST API to handle 100,000 requests per second?
27. Is simply creating a FastAPI endpoint enough to handle 100,000 requests per second, or do you need to do more?
28. What is the difference between Uvicorn and Gunicorn?
29. What are the design considerations for building a high-performance FastAPI application? Is it enough to just create endpoints, or what else should be done?
30. How would you implement rate limiting in FastAPI, for example, to restrict a user to 50 API calls per hour? What are the possible ways to do this?

## Design Principles & Dependency Injection
31. Are you aware of SOLID principles in software design?
32. What is dependency injection in Python?
33. What is dependency injection in FastAPI, especially?
34. Why do we use `yield` instead of `return` when making a DB connection dependency in FastAPI?

## Connection Pooling & Workers
35. What is connection pooling?
36. What are some design considerations for connection pooling? How many connections should be in a pool, and what scenarios affect this?
37. If there are 100,000 requests per second, should the connection pool have 100,000 connections?
38. What is a concurrent worker?
39. What is the difference between ThreadPoolExecutor and ProcessPoolExecutor?

## Career / HR
40. Why did you resign without having another offer in hand?

---
*Total: 40 questions*