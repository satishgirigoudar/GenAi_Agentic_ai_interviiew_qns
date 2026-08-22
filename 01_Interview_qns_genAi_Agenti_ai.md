# GenAI / RAG / Python / Agentic AI — Master Interview Question Bank

---

## 1. Introduction, Background & Experience
1. Introduce yourself and walk through your projects/recent work step by step, with use cases.
2. Tell me about your work experience and what you're currently doing.
3. What was your last/most recent project, and your role in it?
4. What are your roles and responsibilities in your project(s)?
5. Can you share other AI projects you've built or contributed to?
6. What is your overall experience, and how much of it is specifically in Generative AI?
7. Is your experience only in Generative AI, or also in Data Science/ML?
8. In which companies have you worked?
9. Why have you changed jobs frequently, or is there a gap you can explain?
10. How comfortable are you with Python (self-rate)?
11. Are you presently working somewhere, or have you taken a break?
12. What are your top 3 technical skills you're most comfortable with?
13. Which Python frameworks, tools, or technologies have you used?
14. At a high level, how have you used AI in previous projects — assistant tool, part of SDLC, or otherwise?
15. Should I use print statements mid-code during interviews to check my answers? *(interview-mechanics question)*

## 2. Project & Team Context / Deep-Dive
16. Explain your project end-to-end: objective, methodology, business problem it solves, and your role.
17. Describe the tech stack used, deployment details, and current project status.
18. Which UI components and services did you use?
19. Is your RAG pipeline currently deployed in production, or still a POC?
20. What was the file size/document upload limit — did users upload documents, or use a centralized repository?
21. What was the unique value of your solution compared to just using Copilot/ChatGPT for document Q&A?
22. Did you provide citations and grounding in your chatbot responses?
23. Who was the customer for your last project? Does the product have customers yet?
24. How big was your team? What was your specific module, and how many people were on it?
25. Which of your projects was the largest-scale, enterprise-level project shipped to production?
26. What was the real business purpose of your enterprise AI assistant / document intelligence platform?

## 3. RAG Fundamentals & Architecture
27. What is RAG (Retrieval-Augmented Generation)?
28. Explain the complete RAG architecture/workflow (ingestion → chunking → embedding → vector storage → retrieval → augmentation → generation → API integration).
29. Can you explain the ingestion pipeline — is data pulled automatically, and is it event-driven or batch?
30. How do you reduce/handle hallucinations in a RAG pipeline?
31. What is reranking, and when do you apply it?
32. How do you improve response accuracy in your RAG system?
33. Was your solution a simple RAG or a hybrid RAG architecture?
34. What is the difference between RAG and Agentic AI?

## 4. Generative AI, LLM & Transformer Fundamentals
35. What is Generative AI? What is your experience in it?
36. What do you understand by an LLM (Large Language Model)?
37. What is the difference between traditional ML and LLMs?
38. Can you explain an end-to-end LLM pipeline?
39. What is the difference between Generative AI and Agentic AI, and between an AI model and an AI Agent?
40. Can you explain temperature, top-p, and top-k in the context of LLMs?
41. What is the difference between MCP and API?
42. Can you explain the transformer architecture (draw/describe the block diagram)?
43. What is the attention mechanism, self-attention, and multi-head attention?
44. What is a context window, and what is perplexity/temperature in language models?
45. What is an encoder, decoder, and encoder-decoder model? Name examples of each.
46. Why do higher-dimensional embeddings provide better semantic accuracy (transformer analogy)?

## 5. Document Ingestion, Processing & OCR
47. What kind of enterprise data / documents are you ingesting — structured or unstructured?
48. What format is the data in (Word, PDF, images, scanned files), and how often do you receive updates?
49. What is the size/volume of documents, and how many do you process per hour?
50. Is ingestion event-driven or batch? Why did you choose that approach?
51. Walk through the step-by-step process: receiving documents, pulling from cloud storage, integrating into the RAG pipeline.
52. How do you handle corrupted files or files that fail during extraction?
53. How do you handle large document volumes at scale?
54. Did you use the same extraction technique for all document types, or adapt based on content (text vs. images/tables)?
55. Which libraries/OCR service did you use for extracting text, tables, and images from PDFs?
56. How does OCR work internally, and how do you verify extraction accuracy?
57. What extra precautions do you take when extracting PII (e.g., phone numbers) via OCR?
58. How do you store and maintain document structure/context (text, images, tables) after extraction?

## 6. Chunking Strategies
59. How many/what types of chunking strategies are there?
60. Which chunking strategy did you use, and why (fixed-size, recursive, sliding window, semantic, paragraph)?
61. What chunk size and overlap percentage did you use, and how did you decide?
62. Can you explain the sliding window chunking strategy in detail?
63. How did you decide what metadata to include in your chunks?
64. How do you decide chunking strategy for a PDF when structure alone isn't enough?
65. How do you avoid losing context / splitting related content across multiple documents when using smaller chunks?

## 7. Embeddings
66. What embedding model(s) did you use, and why?
67. What does "parameter," "dimension," and "token limit" mean for an embedding model, and how do they relate to chunking?
68. What is the embedding dimension of common models (e.g., 1536 vs. 3072), and what are the pros/cons of each?
69. How do you handle embedding generation for long text — chunk first, or pass the whole text?
70. Did you generate embeddings via a cloud endpoint, or locally? How did you manage this?
71. What happens if you use different embedding models for ingestion vs. retrieval — will quality improve or degrade?
72. How did you generate embeddings — via an LLM call, or does the vector DB/library (e.g., FAISS) handle it automatically?

## 8. Vector Databases & Search
73. Which vector database(s) have you worked with (FAISS, PgVector, Pinecone, ChromaDB, etc.)?
74. What is the difference between a normal database and a vector database?
75. What algorithm does PgVector/FAISS use internally for vector search?
76. What is the difference between exact search and similarity (nearest-neighbor) search?
77. What distance metrics are used in similarity search, and how do you choose between them?
78. Do you know about BM25? Is it used for keyword search, and how does it compare to embedding/semantic search?
79. Why might you use two different vector databases (e.g., FAISS and ChromaDB) in one project?
80. Where was your FAISS vector database hosted — self-hosted, cloud, or managed?
81. How does your vector search capability compare to a managed offering like Azure's vector search?
82. What challenges did you face getting documents searchable via embeddings/FAISS?

## 9. Prompting & Guardrails
83. What prompting techniques are you familiar with?
84. How did you implement guardrails and orchestrate LLMs in your solution?
85. How did you keep the LLM within boundaries and prevent off-topic/erratic outputs?
86. How do you prevent the AI from mixing up contexts and ensure it only uses relevant information?

## 10. LangChain / LangGraph & Agent Workflows
87. What is the difference between LangChain and LangGraph? Why choose one over the other?
88. What is the difference between LangChain and Microsoft Foundry? Have you used Microsoft Foundry or Azure?
89. What are nodes, edges, start/end nodes, and conditionals in LangGraph/agent workflows?
90. Why implement a wrapper around a chain when solving a problem?
91. What is checkpointing in LangGraph? Write a program that uses a checkpointer.
92. What happens after compiling the graph with a checkpointer? What happens if you use `app.invoke` instead of `graph.invoke`?
93. Do you need a thread/session ID to invoke a checkpointed graph? Write the invocation statement (e.g., `graph.invoke(input_data, thread_id="item_3234")`), and explain how to resume a workflow using it.
94. What interrupts exist in the graph? Why use a "read anchor" in LangGraph?
95. What is the difference between `invoke` and `stream`?
96. Which framework did you use to build agents, and how did you evaluate the agent?
97. How do you monitor a LangGraph agent (and hallucinations) in production?
98. What protocol (HTTP/WebSocket, streaming vs. request-response) did you use for agent deployment/communication?

## 11. Agents & Tool Calling
99. Have you worked with AI agents (LangChain/LangGraph)?
100. Scenario: an agent has Addition and Multiplication tools. For "What is 2 + 3 × 5?", how does it arrive at the answer?
101. How would you evaluate the performance of such an agent?
102. If an agent's API call fails mid-workflow, how would you design it to handle the failure?
103. When the API becomes available again, do you restart from the beginning or resume from the last successful step? How would you implement that recovery mechanism?

## 12. Synthetic Data Generation (Scenario)
104. Given a schema (column names, descriptions, data types), how would you generate a synthetic dataset?
105. How would you generate 100K–200K rows efficiently, and scale the design using LangChain/LangGraph?
106. How do you ensure diversity in generated data and avoid duplicates across batches?
107. How would you implement parallel batch generation?
108. Would you reuse the same prompt for every batch? If not, how do you add variations — statically or dynamically — as batch counts change (e.g., 100K → 200K rows)?
109. How would you handle different *intents* per batch (rather than random seeds), and who provides/fills those intent values at runtime?

## 13. RAG Evaluation & Monitoring
110. How would you evaluate a RAG system end-to-end?
111. What KPIs would you use for the retrieval component specifically?
112. Explain Precision using a concrete retrieval example (not just the definition).
113. How do you determine whether retrieved documents are actually relevant?
114. If you don't have labeled data, how would you evaluate retrieval — what alternative approaches exist?
115. Did you prioritize precision, recall, F1, or faithfulness? How do you trade off accuracy vs. latency (retrieval time)?
116. Have you used an evaluation framework, or tools like LangSmith? How do you monitor a deployed GenAI app?

## 14. Chatbot Memory & Caching
117. What kind of caching would you implement in a chatbot, and why?
118. If a chatbot supports multiple conversations, why might it fail to recall something from Day 1 when asked on Day 60?
119. How would you solve long-term memory retention in a chatbot?

## 15. Multimodal / Scanned-Document RAG
120. How would you design an end-to-end RAG pipeline for a 100-page scanned PDF (images only), so the system returns both a text answer and the relevant diagram/image?
121. How do you extract images (not just text) from a scanned PDF, and where do you store the extracted images?
122. How do you associate the generated answer with the correct extracted image and display both together?
123. Have you worked with graph databases or graph structures?

## 16. Azure / Cloud Services & Deployment
124. What Azure services (App Services, VMs, AI services, etc.) did you use in your project?
125. What is the difference between Azure App Services and Virtual Machines?
126. How do you secure Azure services and your application to prevent data leaks?
127. Which cloud platform did you deploy on, and why? Which are you most comfortable with, and what specific services (AWS/Azure) have you used?
128. Which LLMs did you connect with, including inside Azure OpenAI?
129. How did you manage authentication and access to Azure Blob Storage (all users vs. service account)?
130. How do you generate a signed URL so users can open a cited PDF when only the backend has Blob Storage access?
131. How do you deploy your AI application and expose its APIs? Did you personally handle deployment, or was there a separate team?
132. What post-deployment challenges did you face, and how did you resolve them?
133. How many users currently use your application, and how would you scale it for a sudden spike (e.g., 1,000 → 2,000 users, 500+ concurrent requests)?
134. Is your system microservices, monolith, or event-driven? Which is best for a given use case (e.g., a banking product)?
135. What was the infrastructure setup, and which CI/CD pipeline do you use?
136. Did you use Kubernetes / container orchestration — which service specifically?
137. How would you make an open-source LLM efficient enough to support many concurrent users?
138. How do you process data in parallel, and how do you scale your overall AI pipeline? How do you manage API rate limits?

## 17. API Security & Authentication
139. How do you secure API calls between a frontend (React/Next.js) and backend (FastAPI), preventing privilege escalation or unauthorized access?
140. How do you ensure an API call is genuinely coming from your UI and not an attacker?
141. How do you prevent someone from forging/manipulating a JWT to impersonate a user or add roles (e.g., via Postman)?
142. Is the FastAPI backend a separate service/container, and how does the frontend interact with it? Is there a BFF layer, or one big application?
143. What is CORS, and how did you implement CORSMiddleware in FastAPI?

## 18. Backend / Data Architecture Deep-Dive
144. Walk through the architecture and implementation patterns for your project — what would I see in your code at each step, and why?
145. Was the backend connecting directly to the database, or through a service layer? Where does the ORM fit — is the UI ever talking directly to the DB?
146. Was your backend a single FastAPI service or a microservices setup?

## 19. FastAPI — Core Concepts
147. What is dependency injection in FastAPI (and in Python generally)? Why use `yield` instead of `return` for a DB-connection dependency?
148. What are path parameters vs. query parameters?
149. How did you use Pydantic in FastAPI (validation, serialization)?
150. What is the key difference between Django and FastAPI, and how do you choose?
151. Is FastAPI synchronous or asynchronous? What is the difference between ASGI and WSGI?

## 20. FastAPI — Background Tasks, Caching & Async
152. Have you heard of Celery and Redis? What is Celery used for?
153. How do you implement background tasks in FastAPI?
154. Have you implemented in-memory or Redis caching in a FastAPI application?
155. Have you implemented startup/shutdown events in FastAPI?

## 21. FastAPI — Deployment, Scaling & Rate Limiting
156. How have you deployed your FastAPI application (Docker, application server)? Which server runs inside the image (Uvicorn/Gunicorn)?
157. What is the difference between Gunicorn and Uvicorn, and how do you decide the number of workers?
158. How would you configure FastAPI to handle 100 requests/second on a 1 CPU, 1 GB machine? How do you determine the worker limit in production?
159. How would you design a FastAPI REST API to handle 100,000 requests/second? Is simply creating an endpoint enough, or what else is required?
160. How would you implement rate limiting (e.g., 50 calls/hour/user) in FastAPI?

## 22. Database & Migrations
161. Have you worked with SQL or NoSQL databases? Which ORM have you used?
162. How do you handle migrations in FastAPI models (Alembic)?
163. If you add a column and data, then roll back the migration, is the data also rolled back? Will Alembic allow dropping a column that still has data — what are the safe rollback steps?
164. How do you resolve Alembic migration conflicts when two developers modify the same table on different branches?

## 23. Deep Learning
165. Can you describe your deep learning project experience? In which project, and why was DL (vs. plain ML) necessary there?

## 24. Healthcare AI / Domain Project Example
166. Explain your healthcare AI (donor-matching) project: problem statement, brainstorming, design, and deployment. Which country was the client based in?
167. Why use AI/semantic search for donor matching instead of basic database filters?

## 25. AI-Accelerated Delivery (Scenario)
168. How would you set up a framework to deliver a production-ready, AI-heavy banking product from scratch in 1 year instead of the usual 4 — without cutting features, quality, or compliance?
169. How do you avoid hallucination and "junk code" while aggressively fast-tracking delivery with AI?
170. What percentage of effort savings / code generation have you achieved using AI tools in real projects?
171. What's your approach to choosing architecture (event-driven, microservices, monolithic) for AI-heavy systems, and specifically for a banking product?

## 26. Python Fundamentals
172. What are decorators in Python, and can you give a practical example?
173. What is the difference between a list and a tuple (and other data structures: set, dict)? What are the trade-offs?
174. Do you know about call by reference vs. call by value in Python?
175. What is the type of user input in Python, and why is it always a string?
176. What is idempotency? Can you give examples of idempotent vs. non-idempotent operations?
177. How do you handle memory allocation issues in complex Python code?
178. Rate yourself (1–5) in Python, databases, ORMs, and DevOps. Which SQL databases, ORMs (e.g., SQLAlchemy — how many years?), and migration tools have you used?
179. Do you have experience with authentication/authorization?
180. What does it mean that tuples can be dictionary keys? Which objects are hashable? Can a tuple ever be unhashable — give an example.
181. Are you aware of SOLID principles?

## 27. Live Coding Exercises
182. Write pseudocode/code to detect if user input is a mathematical or general query, and route it accordingly.
183. Write code to fetch prime numbers between 1 and 10.
184. Write Python code to calculate a cumulative total of sales for the last three months.
185. Write a SQL query to delete duplicates from a table using window functions.
186. Write a Python function to find all unique contiguous subarrays where total cost doesn't exceed a budget.
187. Extract and count unique 'ORG' entities from a dataset using spaCy.
188. Given a string, count character frequency (ignoring special characters/spaces) and sort ascending — with and without `Counter`.
189. Write pseudocode/code for a RAG application, including selective log retrieval with metadata filtering.
190. Write a simple Flask API (pseudocode and real code) that accepts two values via POST and returns their sum.
191. Write the Dockerfile to containerize a Flask/FastAPI app.
192. Write a FastAPI signup endpoint that collects and saves user details (name, email, phone, password).
193. Create a custom exception for age-based voting eligibility (raise if age < 18); verify it's correctly raised/displayed.
194. Find all pairs in an array whose values sum to a target (e.g., sum = 9).
195. Find the second-largest number in a list without built-in functions or sets.
196. Write a reusable decorator to convert dict keys between snake_case and camelCase (both directions), handling nested structures, without modifying the original dict — first with, then without, regex.

## 28. Concurrency in Python
197. Have you used asyncio? What's the difference between asyncio, multithreading, and multiprocessing — which is faster, and when should each be used?
198. Have you used `ThreadPoolExecutor`? Can you safely run tasks in parallel without it? Why is a thread pool recommended?
199. What's the difference between `ThreadPoolExecutor` and `ProcessPoolExecutor`? What is a "concurrent worker"?

## 29. Testing
200. Which unit-testing frameworks have you used? What are fixtures (in simple terms)? Are they only for databases?
201. What is `conftest.py` in pytest, and how do you use/run tests that rely on it, or use a fixture from it in a test function?

## 30. Connection Pooling
202. What is connection pooling, and what design considerations affect pool size (e.g., should 100,000 req/sec mean 100,000 connections)?

## 31. System Design — Transaction / Fintech API
203. Design a fault-tolerant, idempotent, scalable transaction API that deducts from Account A, credits Account B, updates balances, and notifies both parties.
204. The notification step uses an expensive third-party API — how do you handle it asynchronously? What role does a queue (Redis/RabbitMQ) play, where is it triggered, and what worker consumes it?
205. Write pseudocode for the transaction API covering idempotency, exception handling, and notifications. What status/response does the notification step return?

## 32. System Design — Broader ML/AI Scenarios
206. How would you design a real-time anomaly detection system for financial transactions?
207. How would you design and deploy a recommendation system for a large e-commerce platform?
208. How would you design an end-to-end QA system over a large corpus of legal documents?
209. How would you diagnose and improve an existing translation system that's fluent but inaccurate?
210. How would you architect a feature engineering pipeline for enterprise tabular data (Pandas/NumPy/scikit-learn)?
211. How would you implement automated release gates to block deployment if toxicity/hallucination exceeds a threshold?
212. How do you ensure architectural consistency during a technical handover of a GenAI platform from a vendor to in-house?
213. How would you troubleshoot a production chatbot generating duplicate reports, quality issues, and rising latency after weeks of uptime?
214. How would you approach model versioning?

## 33. Production Performance, Latency & Incident Debugging
215. How can you check and reduce latency/timeout issues in production (e.g., chatbot latency going from ms to seconds)?
216. How do you optimize cost for a high-volume GenAI application?
217. How do you monitor and log LLM latency and tokenization?
218. How do you design backend scalability for sudden usage spikes?
219. All API requests in production suddenly start returning 500 errors with no recent deployments/config changes — how do you investigate?
220. What database-side issues could cause this? Why is it a problem to call an external API in the middle of a DB transaction (long-held locks), and how do you mitigate it?

## 34. Scenario-Based / Behavioral
221. How do you convince a stakeholder when your solution is more optimized than theirs, without offending them?
222. How do you convince a stakeholder to give you more time when a deadline isn't feasible due to R&D/complexity?
223. What would you do if your data pipeline/ingestion isn't working properly, or a native connection is no longer available?
224. As a senior, how do you handle a situation where a junior team member can't understand stakeholder requirements, risking escalation?
225. How would you structure communication to address a project setback in an all-hands meeting?
226. What will you do if a stakeholder asks for pipeline changes outside your working hours?

## 35. Git
227. How do you update your feature branch with the latest changes from main?
228. What's the difference between `git pull` (merge) and `git pull --rebase`?

## 36. Compensation, Notice Period & Closing
229. What is your current CTC / salary at your present or last company?
230. How long will it take you to exit your current company?
231. Do you know anything about our organization? Did you get context from a referrer?
232. Why did you resign without another offer in hand?
233. Do you have any questions for us?

---
*Total unique consolidated questions: 233 (merged and deduplicated across all 18 source transcripts).*