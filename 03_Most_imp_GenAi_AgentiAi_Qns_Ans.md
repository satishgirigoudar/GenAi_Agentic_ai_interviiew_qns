# Interview Q&A — Ready Answers (Satish Girigoudar)

---

## SECTION 1: Asked in Almost Every Interview

### 1. Introduce yourself and walk through your projects

"I'm Satish Girigoudar, a Senior Software Engineer with 4.1 years of experience, currently at Coforge. My core strength is full-stack development with React.js, Redux, TypeScript, and Next.js, and over the last phase of my career I've moved deeply into Generative AI and Agentic AI — building LLM-powered applications using Python, LangChain, RAG, and vector databases.

My flagship project is an AI-Powered Load Planning and Logistics Optimization Platform for Walmart. The problem was that logistics planners had to manually dig through shipment, truck, route, and capacity data spread across multiple systems to decide how to load trucks efficiently. I built a React.js and TypeScript frontend with dashboards and CRUD workflows, and integrated an LLM-powered planning assistant that let planners ask natural-language questions like 'which trucks have capacity for Route 12 tomorrow?' and get context-aware answers. Under the hood, this used RAG — we retrieved relevant shipment and route data using vector embeddings and semantic search, then augmented the LLM prompt with that context before generation. I also used GitHub Copilot, OpenAI Codex, and Claude AI to speed up development, testing, and documentation.

Before that, I worked on Walmart Seller Center, a portal for third-party sellers to manage listings, inventory, pricing, and orders — where I focused on Redux Toolkit state management, REST API integration, and performance optimization.

And earlier, at MUFG, I built CRM dashboard and tracker modules for meetings, actions, and risks, with role-based access control and CRUD operations, in a team of 28 engineers.

Across all of these, my focus has been connecting a solid frontend architecture with intelligent, AI-driven backend capabilities to solve real business problems."

---

### 2. Explain your RAG architecture/workflow end-to-end

"In the Load Planning platform, the RAG pipeline worked like this:

1. **Ingestion** — Logistics data (shipment records, truck capacity, route info, WMS data) was pulled from the Warehouse Management System and internal REST APIs, then converted into text documents suitable for embedding.
2. **Chunking** — I split larger documents (like route manifests or shipment logs) into smaller, semantically meaningful chunks — small enough to fit embedding model limits but large enough to preserve context, with slight overlap between chunks so we didn't lose information at chunk boundaries.
3. **Embeddings** — Each chunk was passed through an embedding model to convert it into a vector representation capturing its semantic meaning.
4. **Vector Store** — These vectors were stored in a vector database — we used ChromaDB and FAISS depending on the use case — indexed for fast similarity search.
5. **Retrieval** — When a planner asked a question in natural language, we embedded the query the same way, then did a similarity search (cosine similarity / nearest neighbor) against the vector store to pull the top-k most relevant chunks.
6. **Prompt Augmentation** — Those retrieved chunks were inserted into the LLM prompt as context, along with the user's original question and some system instructions.
7. **Generation** — The LLM (GPT-4 class model) then generated a grounded, context-aware answer — for example, recommending which truck to use for a shipment based on actual capacity data rather than hallucinating an answer.

This let planners get accurate, real-time answers without me having to fine-tune a model — the knowledge stayed in the vector store, and we could refresh it as data changed."

---

### 3. Which vector database did you use, and why (FAISS, ChromaDB, PgVector, etc.)?

"I worked with both **FAISS** and **ChromaDB**.

- **FAISS** (Facebook AI Similarity Search) — I used this where I needed very fast, in-memory similarity search over large embedding sets, especially during prototyping and for read-heavy workloads where the dataset was relatively static. It's lightweight, has excellent performance for approximate nearest neighbor search, but doesn't have built-in persistence or metadata filtering out of the box — you have to build that yourself.

- **ChromaDB** — I preferred this for the production-facing part of the platform because it gives you persistence, metadata filtering (so I could filter by route ID or date before doing similarity search), and a simpler developer experience — it's built specifically for RAG use cases and integrates cleanly with LangChain.

My decision criteria: if I need quick, in-memory search without complex metadata needs → FAISS. If I need persistence, metadata filtering, and easier integration into an application with LangChain → ChromaDB. For very large-scale production systems with existing SQL infrastructure, PgVector is also attractive because it keeps everything inside Postgres, avoiding a separate database to manage — I'd consider that if the team already had a strong Postgres-based stack."

---

### 4. Were the documents/knowledge base structured or unstructured?

"It was a mix, which is common in real enterprise systems. Shipment and truck capacity records coming from the WMS were largely **structured** — rows with fields like shipment ID, weight, destination, truck ID, capacity. Route notes, planner comments, and operational guidelines were **unstructured** text.

For the structured data, I converted rows into natural-language-like text templates before embedding — for example, turning a row into a sentence like 'Truck T-102 has 4,000 lbs capacity available for Route 12 departing at 6 AM' — because embedding raw JSON or tabular data directly doesn't capture semantic meaning well. For unstructured text (notes, manifests), I chunked and embedded it directly. Keeping both types in the same vector store, tagged with metadata about their source, let the retrieval step pull relevant context regardless of which format it originally came from."

---

### 5. What embedding model did you use, and how are embeddings generated?

"We used embedding models from the GPT-4 / OpenAI-compatible family, accessed in some cases through Azure OpenAI. In practice, an embedding model takes a piece of text and converts it into a fixed-length dense vector — typically in the range of 1,536 dimensions for OpenAI's text-embedding models — where semantically similar pieces of text end up close to each other in vector space, measured usually by cosine similarity.

On token limits: embedding models have a maximum input length (for OpenAI's ada/embedding-3 models it's around 8,191 tokens), so that's one of the reasons chunking matters — you need each chunk to comfortably fit within that limit while still being small enough to be a meaningful, singular unit of context. I kept chunks well under the limit — typically a few hundred tokens — because smaller, focused chunks generally give more precise retrieval than large chunks that mix multiple topics."

---

### 6. What chunking strategy did you use, and why?

"I used a **fixed-size chunking strategy with overlap**, generally around 500–1000 characters (roughly 150–250 tokens) per chunk, with a 10–20% overlap between consecutive chunks. The reasoning:

- **Size** — Small enough that each chunk stays focused on one topic so the embedding accurately represents its meaning, but large enough to retain useful context (a single sentence often loses meaning without surrounding context).
- **Overlap** — Without overlap, a critical fact can get split right at a chunk boundary and lose meaning in both halves. A 10–20% overlap ensures continuity.
- **Semantic chunking** — Where the content had a natural structure (e.g., route manifests with clear sections), I used semantic/structure-aware chunking — splitting on paragraph or section boundaries rather than a strict character count — because it kept logically related information together.

If I were doing this again on a more complex, highly structured document set, I'd lean more heavily into semantic chunking using something like recursive character splitting that respects headers and structure, since it consistently gives better retrieval quality than blind fixed-size splitting."

---

## SECTION 2: Asked Very Frequently

### 7. How do you reduce/prevent hallucinations?

"A few concrete techniques I used:

1. **Grounding with RAG** — Always retrieve real data first and force the model to answer only from the retrieved context, rather than relying on its parametric knowledge.
2. **Prompt instructions** — Explicit system instructions like 'If the answer isn't in the provided context, say you don't know' rather than guessing.
3. **Citing sources** — Having the model reference which shipment/route record it used, which makes it easier to verify and also discourages fabrication.
4. **Lower temperature** — Using a lower temperature setting for factual/operational queries (like load planning recommendations) instead of a creative-writing-style setting.
5. **Retrieval quality** — A lot of hallucination actually comes from bad retrieval, not the LLM itself — so improving chunking, using better embeddings, and re-ranking retrieved results (retrieving more candidates, then re-ranking with a cross-encoder) reduced hallucinations significantly in practice.
6. **Human-in-the-loop / validation** — For high-stakes recommendations (like committing a truck to a route), the system presented the recommendation with supporting data for the planner to confirm rather than auto-executing."

---

### 8. How would you evaluate a RAG system? What metrics matter?

"I look at it in two layers — retrieval quality and generation quality.

**Retrieval evaluation:**
- **Precision@k** — of the top-k chunks retrieved, how many are actually relevant.
- **Recall@k** — of all relevant chunks that exist, how many did we retrieve in the top-k.
- **MRR (Mean Reciprocal Rank)** — how high up the first relevant result appears.

**Generation evaluation:**
- **Faithfulness/groundedness** — does the generated answer actually match what's in the retrieved context, or did the model add unsupported claims?
- **Answer relevance** — does the answer actually address the user's question?

**Evaluating without labeled data:** This is common in practice. My approach:
- Use an **LLM-as-judge** — have a strong model score faithfulness and relevance against the retrieved context, since you don't need ground-truth labels, just the context and the answer.
- **Human spot-checking** — sample a subset of real queries and have domain experts (planners, in our case) rate the answers.
- **Synthetic QA generation** — generate question-answer pairs from your own documents (using an LLM) to create a pseudo-labeled test set, then measure retrieval accuracy against that.
- **A/B / shadow testing** — run the RAG system in parallel with the existing manual process and compare outcomes before fully trusting it."

---

### 9. LangChain vs LangGraph — have you used them, what's the difference?

"Yes, I used LangChain extensively for the RAG pipeline — document loaders, text splitters, embedding integrations, vector store wrappers (ChromaDB/FAISS), and chains that tie retrieval + prompt + LLM call together.

The core difference:
- **LangChain** is built around **chains** — largely linear or simple branching sequences of steps (retrieve → prompt → generate). It's great for straightforward pipelines.
- **LangGraph** is built for **stateful, cyclical, multi-agent workflows** — modeled as a graph of nodes and edges, where you can have loops, conditional branching, retries, and multiple agents collaborating with shared state. It's the right choice when your workflow isn't a straight line — for example, an agent that needs to retrieve, evaluate whether the answer is good enough, and loop back to retrieve again with a refined query.

For my load-planning assistant, LangChain's chain-based approach was sufficient because the flow was largely linear. If I were building a more complex agentic system — for example, one that plans multi-step actions, calls multiple tools, and self-corrects — I'd reach for LangGraph."

---

### 10. asyncio vs multithreading vs multiprocessing — which is faster, when to use each?

"They solve different problems:

- **asyncio (async/await)** — Single-threaded, cooperative concurrency using an event loop. Best for **I/O-bound** work — network calls, database queries, API calls to LLMs — where the program spends most of its time waiting, not computing. It's very lightweight (no thread/process overhead) and can handle thousands of concurrent I/O operations efficiently.
- **Multithreading** — Multiple threads within one process, sharing memory. In Python, due to the **GIL (Global Interpreter Lock)**, only one thread executes Python bytecode at a time, so multithreading doesn't give true parallelism for CPU-bound work — but it still helps for I/O-bound tasks where threads can release the GIL while waiting (e.g., blocking I/O calls in libraries that aren't async-native).
- **Multiprocessing** — Multiple separate processes, each with its own Python interpreter and memory space, so the GIL isn't a bottleneck. Best for **CPU-bound** work — heavy computation, data processing, generating embeddings for a huge batch of documents.

**Which is faster depends on the workload:**
- I/O-bound (API calls, DB calls) → asyncio is generally fastest and most resource-efficient.
- CPU-bound (embedding generation, numeric computation) → multiprocessing wins because it achieves true parallelism.
- Mixed workloads → often a combination — asyncio for I/O concurrency, with CPU-heavy chunks offloaded to a process pool.

In my FastAPI backend, I used asyncio for handling concurrent API/LLM calls, since most of the latency was waiting on external LLM responses, not local computation."

---

### 11. What is connection pooling, and how do you decide pool size?

"Connection pooling means maintaining a reusable set of open database (or HTTP) connections rather than opening and closing a new connection for every request. Establishing a connection has real overhead (TCP handshake, authentication, TLS negotiation), so reusing connections from a pool drastically reduces latency and resource usage under load.

**Deciding pool size** depends on:
- **Expected concurrent requests** — if you expect ~100 concurrent requests hitting the DB, you don't necessarily need 100 connections; many requests can be short-lived, so pool size is about steady-state concurrent DB operations, not total traffic.
- **Database connection limits** — Postgres/MySQL have a max_connections setting; pool size across all app instances must stay under that.
- **Number of app instances** — if you're running 5 replicas of your service, each with a pool of 20, that's 100 total connections hitting the DB — so pool size must be planned in coordination with how many instances you're scaling to.
- **Rule of thumb starting point** — a common formula is something like `pool_size = ((core_count * 2) + effective_spindle_count)` for the DB server, but in practice I'd start with a moderate size (e.g., 10–20 per instance), load test, and tune based on observed wait times and DB CPU/connection usage."

---

### 12. How do you deploy and run your FastAPI/Flask app — Docker, Uvicorn vs Gunicorn?

"I containerize the app with **Docker** — a Dockerfile that installs dependencies, copies the app code, and defines the run command. For running FastAPI:

- **Uvicorn** is an ASGI server — required for FastAPI since FastAPI is async-native. It's fast and lightweight but by default runs a single process.
- **Gunicorn** is a mature, battle-tested process manager traditionally used for WSGI apps (like Flask), but it can be used as a process manager **for** Uvicorn workers — i.e., `gunicorn -k uvicorn.workers.UvicornWorker`. This gives you Gunicorn's process management (worker restarts, graceful reloads, pre-fork model) combined with Uvicorn's ASGI/async support.

**In practice:** for production FastAPI, I run Gunicorn as the process manager with multiple Uvicorn worker processes — this gives multi-core utilization (each worker is a separate process, sidestepping the GIL) plus resilience (if one worker crashes, Gunicorn restarts it). The whole thing runs inside a Docker container, deployed behind a load balancer, so it can scale horizontally by adding container replicas."

---

### 13. What is dependency injection in FastAPI?

"Dependency Injection in FastAPI is a system where you declare dependencies — things a route needs, like a database session, current authenticated user, or shared configuration — as function parameters using `Depends()`, and FastAPI automatically resolves and injects them when the route is called.

For example, instead of manually opening a DB session inside every endpoint, you write a `get_db()` function once, and then any route just declares `db: Session = Depends(get_db)` as a parameter. FastAPI handles calling `get_db()`, passing the session in, and cleaning it up afterward.

**Why it matters:**
- **Reusability** — write common logic (auth checks, DB sessions, rate limiting) once and reuse it across many endpoints.
- **Testability** — in tests, you can override a dependency (e.g., swap a real DB session for a mock/test database) using `app.dependency_overrides`, without touching route code.
- **Separation of concerns** — routes stay clean and focused on business logic rather than boilerplate setup.

I used this pattern for things like validating JWT tokens for authenticated users and injecting shared service clients (like an LLM client) into route handlers."

---

### 14. Which cloud platform and services did you use? How would you scale for a sudden spike?

"I've worked with both **AWS** and **Azure**. On AWS, I used **AWS Bedrock** (for managed access to foundation models without managing infrastructure) and **AWS Lambda** for serverless functions, along with Docker for containerized services. On Azure, I used **Azure OpenAI** and Azure AI Services for LLM access in enterprise environments requiring Azure's compliance/data-residency guarantees.

**Scaling for a sudden traffic spike:**
1. **Horizontal auto-scaling** — configure the container service (ECS/EKS or Azure App Service) to auto-scale based on CPU/memory or request queue depth, so more instances spin up automatically.
2. **Load balancing** — an ALB/API Gateway in front distributes traffic evenly across instances.
3. **Serverless for bursty workloads** — AWS Lambda is naturally suited for sudden spikes since it scales per-request without needing pre-provisioned servers — I'd move latency-tolerant, event-driven pieces of the workload there.
4. **Caching** — cache frequent LLM responses or embedding lookups (e.g., with Redis) to reduce load on the LLM/vector store for repeated queries.
5. **Async/queue-based decoupling** — for spikes, put incoming requests on a queue (SQS/RabbitMQ) and process them with workers that can scale independently, rather than handling everything synchronously — this prevents the system from falling over under sudden load and instead gracefully queues work.
6. **Rate limiting / backpressure** — protect downstream services (like the LLM provider, which has its own rate limits) by throttling gracefully rather than failing outright."

---

### 15. Is your architecture microservices, monolith, or event-driven — and which fits a banking product?

"The Load Planning platform was built with a **service-oriented / microservices-leaning** architecture — the React frontend talked to a set of backend REST APIs, with the AI/LLM capability built as a distinct service that could be called independently from core business logic (WMS integration, order management), rather than embedding LLM logic directly into a monolith.

**Choosing architecture depends on the use case:**
- **Monolith** — good for smaller teams, simpler domains, faster initial development, and when you don't yet have clear service boundaries. Lower operational overhead (one deployment, one codebase).
- **Microservices** — good when different parts of the system have very different scaling needs, different teams own different domains, or you need independent deployability (e.g., updating the AI service without redeploying the whole platform).
- **Event-driven** — good when you need loose coupling and asynchronous processing — for example, in banking, when a transaction event needs to trigger multiple downstream actions (fraud check, notification, ledger update) without those systems being tightly coupled or blocking each other.

**For a banking product specifically**, I'd lean toward a **hybrid: microservices for core domains (accounts, transactions, compliance) combined with event-driven communication (via Kafka/RabbitMQ) between them.** Banking needs strong auditability, strict consistency for money movement, and the ability to independently scale/secure sensitive services (like fraud detection) — a pure monolith makes that harder, while event-driven decoupling lets you add downstream consumers (audit logging, notifications, fraud analysis) without touching the core transaction service, which is critical for a domain where reliability and traceability matter as much as speed."

---

### 16. Python fundamentals — list vs tuple, decorators, data structure trade-offs

"**List vs Tuple:**
- Lists are **mutable** — you can add, remove, or modify elements after creation. Tuples are **immutable** — once created, they can't be changed.
- Because tuples are immutable, they're slightly more memory-efficient and faster to iterate over, and they're **hashable** (can be used as dictionary keys or set elements), whereas lists cannot be.
- Use lists when the collection will change over time (e.g., accumulating results); use tuples for fixed collections, like coordinates `(x, y)` or function return values that represent a fixed structure.

**Decorators:**
A decorator is a function that wraps another function to extend its behavior without modifying its source code. For example, `@app.get('/route')` in FastAPI, or a custom `@timer` decorator that logs how long a function takes to execute. Under the hood, a decorator takes a function as input, defines a wrapper function that adds behavior before/after calling the original, and returns that wrapper — commonly using `functools.wraps` to preserve the original function's metadata.

**Data structure trade-offs (quick reference):**
- **List** — ordered, mutable, O(1) append, O(n) search.
- **Dict** — key-value, O(1) average lookup, unordered before Python 3.7 (now insertion-ordered).
- **Set** — unordered unique elements, O(1) average membership check — great for deduplication.
- **Tuple** — immutable, hashable, slightly faster than lists for fixed data."

---

### 17. What is OCR, how does it work, and how do you handle tables/images during extraction?

"OCR (Optical Character Recognition) is the process of converting images of text — scanned documents, photos, PDFs with non-selectable text — into machine-readable text. It generally works by:
1. **Preprocessing** the image — deskewing, binarization (converting to black/white), noise removal to improve accuracy.
2. **Text detection** — locating regions in the image that contain text.
3. **Character recognition** — using a trained model (traditional OCR engines like Tesseract, or modern deep-learning-based models) to recognize characters/words from those regions.
4. **Post-processing** — spell-checking/correction based on language models to fix recognition errors.

**Handling tables/images during extraction:** Tables are the trickiest part because plain OCR just extracts raw text and loses row/column structure. My approach:
- Use table-detection-aware tools (like `pdfplumber`, `camelot`, or layout-aware models such as LayoutLM/Azure Document Intelligence) that detect table boundaries and preserve row/column structure rather than flattening everything into unstructured text.
- For embedded images (charts, diagrams) within a document, extract them separately and either run them through image captioning/description before embedding, or store them as reference-linked assets, and add a text description to the vector store rather than trying to embed raw image bytes directly (unless using a multimodal embedding model)."

---

### 18. How many years of experience, and self-rating in Python, databases, ORMs, cloud, DevOps?

"I have 4.1 years of overall software engineering experience, with strong depth in React/TypeScript full-stack development and around 1.5–2 years of hands-on focus specifically on Python and GenAI/RAG development.

Self-rating (out of 10):
- **Python** — 7.5/10 — strong in application logic, FastAPI, async programming, and AI/LLM integration; still growing in low-level performance tuning and very large-scale distributed Python systems.
- **Databases** — 7/10 — comfortable with relational DB design, queries, indexing, and now vector databases (ChromaDB/FAISS); less deep on advanced DBA-level tuning.
- **ORMs** — 6.5/10 — practical experience integrating ORMs with FastAPI backends; comfortable but not an expert in every ORM's internals.
- **Cloud** — 7/10 — solid hands-on with AWS (Bedrock, Lambda) and Azure (OpenAI, AI Services); still building deeper expertise in advanced networking/IAM configurations.
- **DevOps** — 6/10 — comfortable with Docker, CI/CD via Jenkins, Git workflows; less hands-on with advanced Kubernetes/infra-as-code, which is an area I'm actively growing in."

*(Adjust these numbers honestly to match your real comfort level before the interview — interviewers often probe follow-up questions on whatever number you give.)*

---

### 19. What is your current CTC, and notice period / exit timeline?

"My current CTC is [state your actual number] and I'm looking for [state your expected hike/number] based on the market rate for this role and my GenAI/full-stack skill set. My notice period is [state your actual notice period, e.g., 60/90 days], though I can check on the possibility of a shorter buyout/early release if needed for the right opportunity."

*(This is personal/confidential info I can't know — fill in your real numbers. Keep it simple, direct, and don't over-explain.)*

---

## SECTION 3: Asked Frequently

### 20. Explain the transformer architecture — attention, self-attention, multi-head attention

"The Transformer is the architecture behind modern LLMs (GPT, LLaMA, etc.), introduced in the 'Attention is All You Need' paper. Key ideas:

- **Self-attention** — for each word (token) in a sequence, the model computes how much attention it should pay to every other token in the same sequence, to build a context-aware representation. It does this using three learned vectors per token: **Query (Q), Key (K), and Value (V)**. The attention score between two tokens is computed as the dot product of one token's Query with another's Key, scaled and passed through softmax to get weights, which are then used to compute a weighted sum of Value vectors.
- **Multi-head attention** — instead of doing this once, the model does it multiple times in parallel ('heads'), each learning to focus on different types of relationships (e.g., one head might capture syntactic relationships, another semantic ones). The outputs from all heads are concatenated and projected back to the original dimension.
- **Why it matters** — unlike RNNs, which process tokens sequentially and struggle with long-range dependencies, self-attention lets every token directly relate to every other token in a single step, enabling much better parallelization and long-context understanding — which is exactly why Transformers scale so well to large models and long context windows.

The full architecture also includes positional encodings (since attention itself has no sense of order), feed-forward layers, layer normalization, and residual connections stacked into multiple layers (encoder and/or decoder blocks depending on the model)."

---

### 21. How do you secure your application and cloud services against data leaks?

"Layered approach:

1. **Authentication & Authorization** — proper JWT/OAuth-based auth, and RBAC (role-based access control) — I implemented this at MUFG for controlling which users could view/edit customer records.
2. **Least privilege** — IAM roles and policies scoped to exactly what a service needs (e.g., a Lambda function only gets read access to the specific S3 bucket/table it needs), never broad admin access.
3. **Encryption** — data encrypted at rest (DB/storage encryption) and in transit (TLS/HTTPS everywhere).
4. **Secrets management** — never hardcode API keys/credentials; use a secrets manager (AWS Secrets Manager, Azure Key Vault) and environment-based config.
5. **Input validation & sanitization** — prevent injection attacks (SQL injection, prompt injection for LLM-facing endpoints).
6. **Network isolation** — VPCs, private subnets for databases, security groups limiting inbound/outbound traffic.
7. **Audit logging & monitoring** — log access to sensitive data and set up alerts for anomalous access patterns.
8. **For LLM-specific systems** — sanitize/guard against prompt injection, and avoid sending sensitive PII to third-party LLM APIs unless the provider offers contractual data-handling guarantees (which is one reason enterprise banking work often prefers Azure OpenAI with its compliance certifications)."

---

### 22. How do you handle database migrations, especially rolling back a column with existing data?

"For migrations, I use a migration tool (Alembic for SQLAlchemy/FastAPI, or similar) that tracks schema versions and generates up/down migration scripts.

**Rolling back a column that already has data** is the tricky part because a naive rollback (just dropping the column) loses data permanently. My approach:
1. **Never do destructive rollback directly in production** — first, back up the data, e.g., copy the column's data into a separate archive table or export it, before running the down-migration.
2. **Additive-first strategy** — when adding a new column, I prefer expanding first (add column, backfill data, deploy code using it) and only later contracting (dropping the old column) once you're confident the new column is stable — this is the 'expand-contract' pattern, which makes rollback safe at every stage because the old state is preserved until you're sure you don't need it.
3. **Test rollback in staging** — always run the down-migration against a staging copy of production data first to confirm no unexpected data loss or constraint violations.
4. **Versioned migrations with clear down_revision** — so if something goes wrong, you can precisely step back one version at a time rather than guessing."

---

### 23. How would you convince a stakeholder your solution is better, without offending them?

"I'd focus on data and shared goals rather than saying their approach is wrong. My approach:
1. **Understand their reasoning first** — ask why they proposed their approach; often there's a constraint or context I'm missing.
2. **Frame around shared objectives** — 'We both want this to scale reliably under load' rather than 'my way is better.'
3. **Show, don't just tell** — where possible, build a small proof-of-concept or benchmark comparing both approaches on a concrete metric (performance, cost, maintainability) so the conversation is grounded in evidence, not opinion.
4. **Acknowledge trade-offs honestly** — no solution is perfect; acknowledging where their approach has advantages builds trust and makes my recommendation more credible.
5. **Let them keep ownership** — present it as 'here's what I found, what do you think?' rather than mandating a decision — people are far more receptive when they feel part of the decision rather than overridden."

---

### 24. What is idempotency? Give examples.

"Idempotency means performing the same operation multiple times produces the same result as performing it once — repeated calls don't cause additional side effects.

**Examples:**
- **HTTP methods** — `GET`, `PUT`, and `DELETE` are idempotent by design (calling DELETE on the same resource twice has the same end state as calling it once — resource is gone). `POST` is typically **not** idempotent (calling it twice can create two records).
- **Payment processing** — if a client retries a payment request due to a network timeout, without idempotency you might charge the customer twice. The fix is an **idempotency key** — the client sends a unique key with the request, and the server checks if it has already processed that key; if so, it returns the original result instead of processing again.
- **Database updates** — `UPDATE users SET status = 'active' WHERE id = 5` is idempotent (running it 10 times leaves the same end state), whereas `UPDATE users SET login_count = login_count + 1` is **not** idempotent (each execution changes the result).

In the fault-tolerant transaction API design I've thought through, idempotency keys are essential precisely because network retries are common and you can't risk double-processing a financial transaction."

---

### 25. How would you configure FastAPI to handle high request volume (e.g., 100 req/sec) on limited resources?

"A few levers:

1. **Async everywhere** — make sure all I/O-bound operations (DB calls, external API/LLM calls) use `async def` and non-blocking libraries (e.g., `asyncpg`, `httpx.AsyncClient`) so a single worker can handle many concurrent requests instead of blocking on each one.
2. **Multiple Uvicorn workers via Gunicorn** — run several worker processes to use multiple CPU cores, since a single async process is still limited by one core for CPU-bound work.
3. **Connection pooling** — reuse DB connections rather than opening new ones per request (as discussed earlier).
4. **Caching** — cache frequent/expensive responses (e.g., with Redis) so repeated identical queries don't hit the DB or LLM every time.
5. **Rate limiting / backpressure** — protect the service from being overwhelmed by shedding excess load gracefully (429 responses) rather than crashing.
6. **Horizontal scaling** — behind a load balancer, run multiple container replicas so 100 req/sec is spread across instances rather than one process handling everything.
7. **Profiling** — actually measure where the bottleneck is (DB, external API, CPU-bound logic) before optimizing blindly — often it's the external LLM call latency that dominates, in which case background processing/queuing might help more than tuning the web server itself."

---

### 26. What is Celery/Redis used for, and how do you implement background tasks in FastAPI?

"**Redis** is an in-memory data store, commonly used as a cache, a message broker, or for fast key-value lookups (session storage, rate-limiting counters).

**Celery** is a distributed task queue — it lets you offload long-running or resource-intensive work (sending emails, generating reports, processing large batches of embeddings) to background workers instead of blocking the main web request. Celery typically uses Redis or RabbitMQ as the message broker to pass tasks from the web app to worker processes.

**Implementing background tasks in FastAPI:**
- For **simple, lightweight background work**, FastAPI has a built-in `BackgroundTasks` parameter — you can pass a function to run after returning the response, useful for things like sending a notification without making the user wait.
- For **heavier, longer-running, or distributed work** (e.g., generating embeddings for thousands of documents), I'd use Celery with Redis as the broker: the FastAPI endpoint just enqueues a task (`task.delay(...)`) and immediately returns a task ID; a separate Celery worker process picks up the task from the Redis queue and processes it asynchronously; the client can poll a status endpoint or get notified via websocket/webhook when it's done.
- This decouples the web server (which should stay responsive) from long-running work, and lets you scale workers independently of web servers."

---

### 27. Given a schema, how would you generate a synthetic dataset at scale (100K–200K rows) with dynamic batch prompt variation and deduplication?

"My approach:

1. **Define the schema/template** — a structured prompt template with placeholders for each field, and a set of value ranges/categories for each field to ensure diversity (e.g., varying customer types, transaction amounts, regions).
2. **Batch generation with prompt variation** — rather than sending one generation request per row (too slow/expensive at 100K+ scale), I'd generate in batches — e.g., ask the LLM to generate 50–100 rows per API call, varying the prompt each batch by rotating through different seed examples, categories, or constraints, to avoid the model producing repetitive patterns.
3. **Parallelization** — run multiple batches concurrently (using asyncio or multiprocessing) against the LLM API, respecting rate limits, to make the ~100K-200K row generation tractable in reasonable time.
4. **Deduplication** — after generation:
   - **Exact dedup** — hash each generated row (e.g., a hash of the concatenated field values) and drop exact duplicates using a set of seen hashes.
   - **Near-duplicate dedup** — for semantic duplicates (rows that differ slightly in wording but represent the same data), use embedding-based similarity — embed each row, and drop rows whose embedding is above a similarity threshold to an already-kept row (using something like FAISS for efficient nearest-neighbor dedup at scale rather than pairwise O(n²) comparison).
5. **Validation** — validate generated rows against the schema (data types, required fields, valid ranges) and reject/regenerate invalid rows.
6. **Iterative refill** — since some generated/deduplicated batches will be dropped, keep generating additional batches until you hit the target row count after dedup and validation."

---

### 28. Design a fault-tolerant, idempotent transaction API with async notifications via a queue

"High-level design:

1. **API layer (FastAPI)** — client submits a transaction request with a **client-generated idempotency key**. The endpoint first checks a fast lookup (Redis or a DB table) for that key:
   - If it exists and the transaction was already processed → return the stored result immediately (no reprocessing).
   - If not → proceed.
2. **Transactional write** — process the transaction inside a **database transaction** (ACID) — deduct/credit balances, insert a transaction record, and store the idempotency key with the result, all atomically, so a partial failure can't leave inconsistent state.
3. **Fault tolerance** — wrap the core transaction logic with retry-safe design: since the idempotency key check happens before any state change, safe retries are possible if the client times out and resends the same request.
4. **Async notification via queue** — after the transaction commits successfully, publish an event (e.g., 'transaction.completed') to a message queue (Redis Streams/RabbitMQ/SQS) rather than sending notifications synchronously within the request — this keeps the API response fast and decouples notification delivery (email/SMS/webhook) from the core transaction path.
5. **Consumer workers** — separate worker processes subscribe to the queue and handle notification delivery, with their own retry logic (e.g., exponential backoff) if the notification channel fails, without affecting the already-committed transaction.
6. **Idempotency for consumers too** — since queues can occasionally deliver a message more than once (at-least-once delivery), the notification worker should also dedupe using the transaction ID, so a user doesn't get two emails for the same transaction.
7. **Observability** — log each stage (received → validated → committed → queued → notified) with the transaction/idempotency key so any stuck or failed transaction can be traced end-to-end."

---

### 29. Write a decorator to convert dict keys between camelCase and snake_case (nested), with and without regex

**Without regex:**
```python
import functools

def to_snake_case(name: str) -> str:
    result = []
    for char in name:
        if char.isupper():
            result.append('_')
            result.append(char.lower())
        else:
            result.append(char)
    return ''.join(result)

def to_camel_case(name: str) -> str:
    parts = name.split('_')
    return parts[0] + ''.join(p.title() for p in parts[1:])

def convert_keys(data, converter):
    if isinstance(data, dict):
        return {converter(k): convert_keys(v, converter) for k, v in data.items()}
    elif isinstance(data, list):
        return [convert_keys(item, converter) for item in data]
    else:
        return data

def snake_case_response(func):
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        result = func(*args, **kwargs)
        return convert_keys(result, to_snake_case)
    return wrapper
```

**With regex:**
```python
import re
import functools

def to_snake_case(name: str) -> str:
    s1 = re.sub(r'(.)([A-Z][a-z]+)', r'\1_\2', name)
    return re.sub(r'([a-z0-9])([A-Z])', r'\1_\2', s1).lower()

def to_camel_case(name: str) -> str:
    parts = re.split(r'_', name)
    return parts[0] + ''.join(word.title() for word in parts[1:])

def convert_keys(data, converter):
    if isinstance(data, dict):
        return {converter(k): convert_keys(v, converter) for k, v in data.items()}
    elif isinstance(data, list):
        return [convert_keys(item, converter) for item in data]
    return data

def camel_case_response(func):
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        result = func(*args, **kwargs)
        return convert_keys(result, to_camel_case)
    return wrapper
```

**Explanation to give verbally:** "This decorator wraps an API response function. After the function returns its dict (potentially nested with lists of dicts inside), the decorator recursively walks the structure and converts every key from camelCase to snake_case (or vice versa), which is a common need when your Python backend uses snake_case convention internally but the frontend/JS client expects camelCase in the JSON response. The regex version uses two substitution passes to correctly handle both single-capital transitions and consecutive-capital sequences (like 'HTTPServer' → 'http_server'); the non-regex version does it character-by-character, which is easier to read but slightly more verbose."

---

## Quick Prep Checklist
- [ ] Rehearse Q1–Q6 out loud until fluent (near-certain in every interview)
- [ ] Have one concrete example ready per Q7–Q19
- [ ] Be ready to go deeper (4-5 follow-ups) on any Q20–Q29 relevant to your resume
- [ ] Fill in your real CTC/notice period for Q19 before the interview
- [ ] Practice the coding question (Q29) by actually typing it out, not just reading it