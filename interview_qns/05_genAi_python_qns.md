# HCLTech — Python / Gen AI Interview — Practice Questions
*Source: Interview transcript, 27-07-2026*

## Introduction
1. Introduce yourself and explain your projects step by step with use cases.

## Vector Databases & Search Algorithms
2. Which vector database(s) have you worked with in your RAG pipelines?
3. What algorithm does PgVector use for vector search?
4. What algorithms are available for vector databases right now?
5. Which algorithm does PgVector use for vector search? (follow-up)
6. What specific algorithm does PgVector use for vector search, and how does it work internally?

## Document Scale, Embedding Choice & Chunking
7. What is the size or volume of documents you have worked with in your projects?
8. How do you process and validate 10,000 PDF documents for vector search — specifically, how do you choose the embedding model, embedding dimension, and chunk size?

## Embedding Model Concepts — Parameters, Dimensions, Token Limits
9. What does "parameter" mean in the context of an embedding model (e.g., 1 million or 3 million parameters)?
10. What is the token limit for AWS Text Embedding 3 Small and Large models?
11. Which provider and model are you referring to with "3 million parameter" text embedding model — AWS or Azure?
12. Clarify the difference between "parameters," "dimensions," and "token limits" in embedding models, and explain how chunking relates to these concepts.
13. What is the embedding dimension of the Azure text embedding model?
14. Is there a larger Azure embedding model with a dimension around 3000?
15. What is the difference between having an embedding dimension of 1500 (1536) and 3000 (3072)?
16. Give one advantage (pro) of using a 1536-dimensional embedding and one advantage of using a 3072-dimensional embedding.
17. What is the con (disadvantage) of using lower-dimensional (1536) and higher-dimensional (3072) embeddings?
18. What are the disadvantages (cons) of using lower-dimensional (e.g., 1536) and higher-dimensional (e.g., 3072) embeddings? (follow-up)
19. Explain, using a transformer analogy, why higher-dimensional embeddings provide higher semantic accuracy in search compared to lower-dimensional ones.

## Transformer Architecture Deep Dive
20. Can you draw or explain the block diagram of a transformer architecture right now?
21. Can you draw or visually explain the block diagram of a transformer architecture (using notepad or similar), and walk through its main components?
22. What is multi-head attention in the transformer architecture?
23. How does the multi-head attention layer affect the size of the dimension?
24. What does a self-attention layer do, and how is multi-head attention different from single-head (self-)attention?
25. How does the higher-dimensional representation in attention models (like transformers) compare to lower-dimensional embedding models (like word2vec), especially regarding capturing multiple properties or relationships?

## RAG Evaluation
26. How do you evaluate your RAG (Retrieval-Augmented Generation) system?
27. What are the key parameters for evaluating a RAG (Retrieval-Augmented Generation) system?

## Frameworks, Agents & Orchestration
28. Which framework did you use to build your RAG (Retrieval-Augmented Generation) pipeline?
29. Which frameworks did you use to develop agents and orchestrate your RAG pipeline?
30. How did you evaluate your LangGraph agent?

## Production Monitoring & Deployment
31. How are you monitoring your LangGraph agent in production?
32. How are you monitoring hallucinations in your GenAI agent?
33. Can you describe your deployment process for the LangGraph agent, and what protocol it used for communication?
34. What protocol did you use for communication (HTTP, HTTPS, WebSocket)? Were you streaming outputs or using standard request/response? How did it work?

## Live Coding — Character Frequency
35. Given a string, count the frequency of each alphabet (ignore special characters and spaces), and print the alphabets in ascending order of their frequency.
36. Can you directly show the sorted frequency list instead of printing it with a loop?
37. Can you implement the character frequency logic without using `Counter`?
38. Why am I getting "AttributeError: 'NoneType' object has no attribute 'items'" on line 16?

---
*Total: 38 questions*

## TechM

# Tech Mahindra — Python / Gen AI Interview — Practice Questions
*Source: Interview transcript, 23-07-2026*

## Introduction & Background
1. Introduce yourself and explain your projects step by step with use cases.
2. What was your last assignment you worked on?
3. What was your specific implementation and technical contribution in your last project?

## Career History Questions
4. Why have you changed jobs frequently? Any specific reason for the frequent job changes?
5. I don't see a long commitment to any company — can you explain?
6. Clarifying total years of experience, including a gap year.
7. There is a gap in your experience — can you explain the reason for this gap?

## FastAPI — APIs, Validation & Serialization
8. Have you worked with FastAPI? What kind of APIs did you build, and how many APIs did you expose using FastAPI?
9. How many APIs have you developed using FastAPI?
10. Have you ever implemented custom request validation and serialization in FastAPI (not using Pydantic)?
11. Have you handled inter-service communication?

## FastAPI — Caching
12. Have you ever done caching in your FastAPI application?
13. Can you explain how you did in-memory caching and Redis caching in your FastAPI projects?

## FastAPI — Deployment & Application Server
14. How have you deployed your FastAPI applications?
15. Have you created any Dockerfile for your FastAPI applications?
16. Which server was being used as an application server for your FastAPI deployment?
17. Which server did you use to run your FastAPI application inside your Docker image? What was your application server?
18. Have you implemented startup and shutdown events in FastAPI?

## FastAPI — Core Concepts
19. What are the benefits of using FastAPI?
20. What is dependency injection in FastAPI?
21. What are path parameters and query parameters?
22. What is cross-origin resource sharing (CORS)?
23. Have you implemented CORS in your projects?
24. Which library do you import in FastAPI to handle CORS?
25. How did you make use of CORSMiddleware in FastAPI?
26. How did you use Pydantic in FastAPI?
27. What elements have you accessed using Pydantic in FastAPI?

## LLM Connectivity
28. What all LLMs have you connected with?
29. Which LLMs did you access or connect with inside Azure OpenAI?

## Transformer Architecture & LLM Fundamentals
30. Do you know what a transformer is?
31. Explain the transformer architecture.
32. What is the attention mechanism in transformers?
33. What is self-attention and multi-head attention?
34. What is a context window in language models?
35. What is an encoder model? Can you name one encoder?
36. What is a decoder model? Can you name one decoder?
37. What is an encoder-decoder model? Can you name one?
38. What is perplexity in language models?
39. What is temperature in language models?

## Agents & LangGraph
40. Have you worked with agents?
41. Which framework did you use to build AI agents?
42. Why did you choose LangGraph for building agents?
43. Apart from handling complex agent workflows, why else did you choose LangGraph?
44. What are the different components in LangGraph?
45. What are nodes and what are edges in LangGraph?

## Agentic AI Concepts
46. What problem does agentic AI solve?
47. What problem does agentic AI solve that a regular LLM cannot?
48. What problem does agentic AI solve that a regular LLM can't solve? (follow-up)
49. What are the primary components of an agent?
50. How many types of memory does an agent have?
51. What are short-term and long-term memory in agents?

## Closing
52. Do you have any questions for us?

---
*Total: 52 questions*

# Apexon — Python / Gen AI Interview — Practice Questions
*Source: Interview transcript, 22-07-2026*

## Introduction & Project Deep-Dive
1. Introduce yourself and explain your projects step by step with use cases.
2. Tell me about yourself and explain your projects, especially those using Python and RAG, in detail.
3. Explain a Python RAG project in detail — what was the project, what issues did you face, how did you overcome them, what did you learn, and how did it help stakeholders?

## Python Technical
4. How do you handle memory allocation issues in complex Python code?

## Stakeholder Conflict & Persuasion (Scenario)
5. What do you do when your solution and the stakeholder's solution are different or there's a conflict?
6. What do you do if your solution is more optimized than the stakeholder's, but they prefer their own approach?
7. How do you convince a stakeholder when your solution is more optimized than theirs?
8. How do you handle a situation where a stakeholder proposes a solution, but you and your team believe it needs to be optimized or reworked? How do you convince the stakeholder?
9. How do you communicate to the stakeholder that their solution needs rework, without offending them, and ensure the work moves forward smoothly?
10. How do you convince a stakeholder to give you more time when their requested deadline isn't possible due to required R&D or complexity?

## Live Coding — Prime Numbers
11. Write code to fetch prime numbers between 1 and 10.
12. Write code to fetch prime numbers between 1 and 10. (retry)
13. Why does your code only return [1] instead of all prime numbers between 1 and 10?

## Live Coding — Cumulative Sales
14. How do you calculate the cumulative total of sales for the last three months, given a month and sales column?
15. Write Python code to fetch the cumulative total of sales for the last three months, given month and sales columns.
16. Write Python code to calculate the cumulative total of sales for the last three months, given a month and sales column. (retry)

## Live Coding — SQL Window Functions
17. Write a SQL query to delete duplicates from a table using window functions.
18. How do you use a window function to delete duplicates from a table?
19. Can you copy-paste the entire SQL code for deleting duplicates using a window function?

## Data Pipeline Troubleshooting (Scenario)
20. What would you do if your data pipeline is having issues with data injection not working properly?
21. How would you resolve a data ingestion pipeline issue when the injection is not working properly?
22. How can you resolve a data ingestion issue using FastAPI when a native connection is not available?
23. What would you do if the native data connection in a data ingestion pipeline is no longer available due to company changes?

## Team & Escalation Management (Scenario)
24. How do you handle a situation where a new team member can't understand the stakeholder's requirements, and escalation or performance issues could impact you as a senior? What if the fault is with your resource, or with the stakeholder's requirements?
25. As a senior, how do you handle a situation where a new team member can't understand stakeholder requirements, and escalation is possible — whether the fault is with your resource or the stakeholder?
26. How do you handle unclear or changing stakeholder requirements in a project?
27. What will you do if a stakeholder asks for pipeline changes outside your working hours?

---
*Total: 27 questions*