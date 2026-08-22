# GenAI / RAG / Python / Agentic AI — Master Interview Q&A (233 Questions)
*Ready-made, practical answers tailored to Satish Girigoudar's background (React/GenAI Full Stack Developer, Walmart Load Planning RAG platform, Walmart Seller Center, MUFG CRM).*

> Fill-in-the-blank items (CTC, notice period, company names, referrer info) are marked clearly — put your real details in before the interview.

---

## 1. Introduction, Background & Experience

**1. Introduce yourself and walk through your projects/recent work step by step, with use cases.**
"I'm Satish Girigoudar, a Senior Software Engineer with 4.1 years of experience, currently at Coforge. I started as a React/frontend developer and over the last 1.5–2 years moved deeply into GenAI and Agentic AI. My main project is an AI-powered Load Planning and Logistics Optimization Platform for Walmart — planners needed to query shipment, truck, and route data in natural language instead of digging through multiple systems, so I built a React/TypeScript frontend plus an LLM-powered assistant using RAG — retrieving relevant logistics data via vector search and feeding it to the LLM for grounded answers. Before that, I worked on Walmart Seller Center (React/Redux Toolkit portal for third-party sellers) and at MUFG building CRM dashboards with RBAC. Across all of them, my focus has been connecting solid frontend architecture with AI-driven backend intelligence."

**2. Tell me about your work experience and what you're currently doing.**
"I have 4.1 years of experience, currently at Coforge as a Senior Software Engineer. Right now I'm working on the Walmart Load Planning platform, building both the React frontend and the GenAI/RAG layer that lets planners ask natural-language questions about logistics data and get context-aware answers instead of manually searching multiple systems."

**3. What was your last/most recent project, and your role in it?**
"My most recent project is the Walmart AI-Powered Load Planning and Logistics Optimization Platform. My role was Full Stack React & GenAI Developer — I built the frontend (dashboards, CRUD workflows, forms) in React/TypeScript, and also built the LLM-powered planning assistant: the RAG pipeline, prompt engineering, and integration with backend REST APIs and the Warehouse Management System."

**4. What are your roles and responsibilities in your project(s)?**
"On the frontend side: building reusable React components, dynamic dashboards, CRUD workflows, forms with validation, and performance optimization (memoization, lazy loading). On the AI side: designing the RAG pipeline (chunking, embeddings, vector store, retrieval), prompt engineering, integrating the LLM with REST APIs and business rules, and writing unit/integration tests with Jest and React Testing Library. I also used AI coding tools (Copilot, Codex, Claude) to speed up development and code review."

**5. Can you share other AI projects you've built or contributed to?**
"Beyond the Load Planning platform, I've applied AI-assisted development practices (Copilot, Codex, Claude AI) across projects at MUFG for documentation and code review acceleration. My core hands-on AI/GenAI project work has been concentrated on the Walmart Load Planning platform, where I built the full RAG pipeline, vector search, and LLM integration end-to-end — that's the project I'd want to go deep on."

**6. What is your overall experience, and how much of it is specifically in Generative AI?**
"4.1 years total. Roughly the last 1.5 to 2 years have had a strong GenAI/RAG focus, layered on top of my React/full-stack foundation — so I'd describe myself as a full-stack engineer who has specialized into GenAI application development, not a data scientist who later learned web dev."

**7. Is your experience only in Generative AI, or also in Data Science/ML?**
"My strength is applying GenAI — LLMs, RAG, prompt engineering, vector search — inside real application architecture, not classical ML/data science (model training, feature engineering for predictive models). I understand ML fundamentals, but I'd position myself as a GenAI application/full-stack engineer rather than an ML/data scientist."

**8. In which companies have you worked?**
"I'm currently at Coforge, working on the Walmart account (Load Planning platform and Walmart Seller Center). Before that, I worked on the MUFG CRM project."

**9. Why have you changed jobs frequently, or is there a gap you can explain?**
*(Only answer if applicable to your actual history — keep it short and forward-looking.)* "[Adjust to your real situation] My moves have been driven by wanting to grow into more advanced technical work — each move gave me more ownership, from frontend development into full RAG/GenAI system design."

**10. How comfortable are you with Python (self-rate)?**
"I'd rate myself 7 to 7.5 out of 10. I'm strong in building FastAPI backends, async programming, LangChain-based RAG pipelines, and integrating LLMs and vector databases. I'm still deepening my knowledge of very large-scale distributed Python systems and low-level performance tuning."

**11. Are you presently working somewhere, or have you taken a break?**
"I'm currently employed at Coforge, actively working on the Walmart Load Planning platform."

**12. What are your top 3 technical skills you're most comfortable with?**
"React.js/TypeScript for building complex, performant frontends; RAG architecture and LangChain for GenAI application development; and Python/FastAPI for backend and AI service integration."

**13. Which Python frameworks, tools, or technologies have you used?**
"FastAPI for backend APIs, LangChain for RAG/LLM orchestration, ChromaDB and FAISS as vector stores, Pydantic for data validation, and Jest/React Testing Library on the frontend side. I've also used AWS Bedrock and Azure OpenAI for LLM access, and Docker for containerization."

**14. At a high level, how have you used AI in previous projects — assistant tool, part of SDLC, or otherwise?**
"Two ways: first, AI as a core product feature — the LLM-powered planning assistant embedded in the Load Planning platform itself, answering user queries via RAG. Second, AI as part of my own SDLC — using GitHub Copilot, OpenAI Codex, and Claude AI for code generation, debugging, refactoring, documentation, and test scaffolding to move faster."

**15. Should I use print statements mid-code during interviews to check my answers?**
"Yes, in a live coding round it's completely fine to add print/debug statements to verify intermediate values as you go — it shows a methodical approach. Just clean them up or mention you'd remove them before final submission, and narrate what you're checking so the interviewer can follow your reasoning."

---

## 2. Project & Team Context / Deep-Dive

**16. Explain your project end-to-end: objective, methodology, business problem it solves, and your role.**
"Objective: give Walmart logistics planners a natural-language interface to shipment, truck, and route data so they can make faster, better load-planning decisions instead of manually cross-referencing multiple systems. Methodology: I built a React/TypeScript frontend for dashboards and workflows, connected to REST APIs and the WMS, with an LLM-powered assistant layered on top using RAG — data is chunked, embedded, stored in a vector DB, retrieved on query, and used to ground the LLM's response. Business problem solved: reduces planning time, improves load/route efficiency, and lowers reliance on planners memorizing or manually searching operational data. My role: full-stack + GenAI developer, owning both the UI and the RAG/LLM integration."

**17. Describe the tech stack used, deployment details, and current project status.**
"Frontend: React.js, TypeScript, Material UI. Backend/AI: Python, FastAPI-style services, LangChain, ChromaDB/FAISS, LLMs via cloud AI services. Testing: Jest, React Testing Library. Deployment: containerized with Docker, CI/CD via Jenkins. Status: actively in use/being enhanced — it's a live internal platform, not just a POC."

**18. Which UI components and services did you use?**
"Reusable dashboard components, dynamic data tables, CRUD forms with validation, a chat-style query interface for the LLM assistant, and Material UI components for consistent styling. On the services side, REST API clients for WMS integration, and a dedicated AI service handling the RAG/LLM logic."

**19. Is your RAG pipeline currently deployed in production, or still a POC?**
"It's deployed and actively used by planners — not just a POC. It went through iterations: we started with a smaller-scale proof of concept to validate retrieval quality and usefulness, then hardened it (better chunking, evaluation, error handling) before rolling it out more broadly."

**20. What was the file size/document upload limit — did users upload documents, or use a centralized repository?**
"Users didn't upload ad hoc documents — the knowledge base was built from a centralized repository (WMS exports, shipment/route data, operational documents), ingested and refreshed on a schedule rather than per-user upload. This kept the vector store consistent and avoided managing arbitrary user-uploaded file sizes."

**21. What was the unique value of your solution compared to just using Copilot/ChatGPT for document Q&A?**
"Generic tools like ChatGPT don't have access to our private, real-time logistics data — shipment IDs, truck capacities, live route status. Our RAG system grounded answers in that private, constantly-changing operational data, integrated into the existing planning workflow with role-based access and audit trails, which a generic chatbot simply can't provide."

**22. Did you provide citations and grounding in your chatbot responses?**
"Yes — responses referenced the specific shipment/route/truck records used to generate the recommendation, so planners could verify the data behind the answer rather than trusting it blindly. This was also key to reducing hallucination risk and building planner trust in the tool."

**23. Who was the customer for your last project? Does the product have customers yet?**
"The customer was internal — Walmart's logistics planning team, using the platform to manage load planning and shipment routing. It has active internal users (planners) today, not just a pilot group."

**24. How big was your team? What was your specific module, and how many people were on it?**
"On the Load Planning project, I worked within a cross-functional team handling frontend, backend, and AI integration. My specific ownership was the planning assistant module — the RAG pipeline and its integration into the React frontend. On the MUFG CRM project, the overall team size was 28, and I focused on the dashboard/tracker modules (meetings, actions, risks) with RBAC."

**25. Which of your projects was the largest-scale, enterprise-level project shipped to production?**
"The Walmart Load Planning and Logistics Optimization Platform — it's an enterprise-scale, production system integrated with WMS and real operational data, used daily by planners, which makes it the most significant project on my resume in terms of scale and AI complexity."

**26. What was the real business purpose of your enterprise AI assistant / document intelligence platform?**
"To cut down the time and cognitive load planners spent manually querying multiple systems for shipment, truck, and route information — replacing that with a natural-language interface that returns accurate, grounded, context-aware recommendations, ultimately improving load efficiency and planning speed."

---

## 3. RAG Fundamentals & Architecture

**27. What is RAG (Retrieval-Augmented Generation)?**
"RAG is a technique that combines an LLM with an external knowledge retrieval step. Instead of relying only on what the model learned during training, the system retrieves relevant, up-to-date information from a vector database at query time and feeds it into the prompt, so the model generates answers grounded in real data rather than hallucinating or relying on stale training knowledge."

**28. Explain the complete RAG architecture/workflow.**
"Ingestion — pull source data (documents, DB records). Chunking — split into smaller semantically meaningful pieces with overlap. Embedding — convert each chunk into a vector using an embedding model. Vector storage — store vectors in a vector DB (ChromaDB/FAISS) with metadata. Retrieval — embed the incoming query, do similarity search to get top-k relevant chunks. Augmentation — insert those chunks into the LLM prompt as context. Generation — the LLM produces an answer grounded in that context. API integration — wrap this whole flow behind a REST endpoint the frontend calls."

**29. Can you explain the ingestion pipeline — is data pulled automatically, and is it event-driven or batch?**
"In my project it was primarily scheduled/batch — logistics and WMS data was refreshed on a regular interval (e.g., periodically throughout the day) since near-real-time freshness mattered but sub-second updates weren't required. For fast-changing data, I'd lean event-driven (triggered on a DB update or message from the source system) instead, to keep the vector store from going stale between batch runs."

**30. How do you reduce/handle hallucinations in a RAG pipeline?**
"Ground every answer strictly in retrieved context via prompt instructions ('answer only from the provided context, say you don't know otherwise'), use lower temperature for factual queries, improve retrieval quality (better chunking/embeddings/reranking) since bad retrieval is often the real cause, and show citations so answers are verifiable rather than blindly trusted."

**31. What is reranking, and when do you apply it?**
"Reranking is a second-pass step after initial retrieval: you retrieve a larger candidate set (e.g., top 20) using fast vector similarity, then use a more precise but slower model (a cross-encoder) to re-score and reorder those candidates for true relevance, keeping only the top few (e.g., top 5) to pass to the LLM. I'd apply it when initial vector search alone isn't precise enough — e.g., when queries are ambiguous or the corpus has many similar-looking chunks."

**32. How do you improve response accuracy in your RAG system?**
"Better chunking (semantic boundaries, right size/overlap), better embeddings, adding metadata filters (route ID, date) to narrow retrieval before similarity search, reranking retrieved candidates, prompt engineering with clear grounding instructions, and continuously evaluating with real query logs to catch and fix retrieval gaps."

**33. Was your solution a simple RAG or a hybrid RAG architecture?**
"It was closer to hybrid — pure vector similarity search alone wasn't always precise enough for structured logistics queries, so I combined metadata filtering (structured filters like route/truck ID) with vector/semantic search, and in some cases combined keyword-based matching with embedding-based retrieval to catch exact identifiers that embeddings alone might miss."

**34. What is the difference between RAG and Agentic AI?**
"RAG is about grounding a single LLM response in retrieved data — it's still a mostly linear retrieve-then-generate flow. Agentic AI goes further: an agent can reason about multiple steps, decide which tools/actions to take (including calling a RAG retrieval tool as one of many), evaluate its own intermediate results, and loop or replan — it's about autonomous multi-step decision-making, not just single-shot grounded generation. RAG is often one building block used inside an agent."

---

## 4. Generative AI, LLM & Transformer Fundamentals

**35. What is Generative AI? What is your experience in it?**
"Generative AI refers to models that can generate new content — text, code, images — rather than just classify or predict a fixed label. My experience is hands-on: building LLM-powered applications, RAG pipelines, prompt engineering, and integrating GenAI (GPT-4 class models) into production web applications for enterprise use cases like logistics planning assistance."

**36. What do you understand by an LLM (Large Language Model)?**
"An LLM is a neural network, typically Transformer-based, trained on massive text corpora to predict the next token in a sequence. Through this training at scale, it learns grammar, facts, reasoning patterns, and coding ability, and can generate coherent, context-aware text given a prompt — models like GPT-4 and LLaMA are examples I've worked with."

**37. What is the difference between traditional ML and LLMs?**
"Traditional ML models are typically trained for one specific task (e.g., classification, regression) on a relatively small labeled dataset, and require retraining for a new task. LLMs are pretrained once on massive, general text data and can then perform many different tasks (Q&A, summarization, code generation) via prompting alone, without task-specific retraining — this generality plus in-context learning is the key distinction."

**38. Can you explain an end-to-end LLM pipeline?**
"Input handling — receive and preprocess the user query. Prompt construction — combine the query with system instructions and (in RAG) retrieved context. Tokenization — convert text to tokens the model understands. Inference — the model generates a response token by token. Post-processing — parse/format the output, apply guardrails/filters. Response delivery — return the final answer to the user, often with logging for monitoring and evaluation."

**39. What is the difference between Generative AI and Agentic AI, and between an AI model and an AI Agent?**
"Generative AI produces content in response to a prompt — a single input/output interaction. Agentic AI adds autonomy: an agent can plan multi-step actions, call tools, observe results, and decide next steps toward a goal, often in a loop. An AI model is just the underlying engine (like an LLM); an AI Agent is a system built around that model, giving it tools, memory, and a decision loop so it can act, not just respond."

**40. Can you explain temperature, top-p, and top-k in the context of LLMs?**
"These control randomness in generation. Temperature scales the probability distribution before sampling — low temperature (e.g., 0.1) makes output more deterministic/focused, high temperature (e.g., 0.9) makes it more creative/random. Top-k restricts sampling to only the k most likely next tokens, ignoring the long tail. Top-p (nucleus sampling) instead selects the smallest set of tokens whose cumulative probability exceeds p, so it adapts dynamically to how confident the model is. In my RAG assistant, I used lower temperature for planning recommendations since accuracy mattered more than creativity."

**41. What is the difference between MCP and API?**
"An API is a general contract for how software components communicate — request/response over HTTP typically, with an OpenAPI spec you have to read and hard-code integration for. MCP (Model Context Protocol) is a standardized protocol specifically designed for LLMs/agents to discover and call external tools and data sources dynamically and uniformly — the model can query what tools/capabilities are available and use them, rather than every integration needing custom, hardcoded API-calling logic. MCP is essentially a higher-level, agent-friendly standardization built on top of the same request/response idea."

**42. Can you explain the transformer architecture (draw/describe the block diagram)?**
"At a high level: Input embeddings + positional encoding → stack of encoder blocks (each with multi-head self-attention + feed-forward layers, with residual connections and layer norm) → (for encoder-decoder models) decoder blocks that also attend to the encoder output → output projection + softmax to predict the next token. GPT-style models use a decoder-only stack; BERT uses an encoder-only stack. The core innovation is self-attention, letting every token directly relate to every other token in parallel, rather than processing sequentially like RNNs."

**43. What is the attention mechanism, self-attention, and multi-head attention?**
"Self-attention lets each token look at every other token in the sequence to build a context-aware representation, using learned Query, Key, and Value vectors — the attention score between two tokens is the scaled dot product of one's Query with another's Key, passed through softmax to weight the Value vectors. Multi-head attention runs several of these attention computations in parallel with different learned projections, so different heads can capture different types of relationships (syntax, semantics, long-range dependencies), then concatenates and projects the results back together."

**44. What is a context window, and what is perplexity/temperature in language models?**
"The context window is the maximum number of tokens (input + output combined) the model can process at once — anything beyond that gets truncated or ignored, which is why chunking and retrieval matter so much in RAG. Perplexity measures how 'surprised' a model is by a sequence of text — lower perplexity means the model finds the text more predictable/fluent, and it's often used to evaluate language model quality. Temperature (as above) controls randomness in generation."

**45. What is an encoder, decoder, and encoder-decoder model? Name examples.**
"Encoder models process the full input at once and produce rich contextual representations — good for understanding tasks like classification or embeddings (e.g., BERT). Decoder models generate text token-by-token, only attending to previous tokens — good for generation tasks (e.g., GPT-4, LLaMA). Encoder-decoder models combine both — the encoder reads the full input, the decoder generates output conditioned on it — good for tasks like translation or summarization (e.g., T5, the original Transformer, BART)."

**46. Why do higher-dimensional embeddings provide better semantic accuracy?**
"A higher-dimensional embedding space gives the model more 'room' to represent fine-grained distinctions in meaning — more independent directions to encode different semantic features (topic, tone, entity type, relationships) without them collapsing into each other. This generally improves the ability to distinguish subtly different concepts during similarity search, though it comes with a cost: more storage, slower search, and diminishing returns past a point — so it's a trade-off between semantic precision and performance/cost, not a free upgrade."

---

## 5. Document Ingestion, Processing & OCR

**47. What kind of enterprise data / documents are you ingesting — structured or unstructured?**
"A mix — structured data (shipment records, truck capacity, route tables from the WMS) and unstructured text (operational notes, manifests, planning guidelines). I converted structured rows into natural-language-style text before embedding, since raw tabular data doesn't embed meaningfully, and chunked/embedded unstructured text directly."

**48. What format is the data in, and how often do you receive updates?**
"Primarily structured exports/API responses from the WMS (JSON/tabular), plus some text-based operational documents. Updates were pulled on a scheduled/periodic basis — frequent enough to keep truck/route/capacity data current for planners without needing full real-time streaming."

**49. What is the size/volume of documents, and how many do you process per hour?**
"[Adjust to real numbers if you know them] The volume was in the range of thousands of records per refresh cycle — shipment and route data across multiple distribution centers — processed in scheduled batches rather than a constant per-hour throughput requirement."

**50. Is ingestion event-driven or batch? Why did you choose that approach?**
"Batch, on a scheduled interval. I chose batch because the underlying WMS data didn't change so fast that sub-minute freshness was required, and batch processing was simpler to build, monitor, and made embedding/re-indexing more efficient (processing in bulk rather than one record at a time). For a use case needing instant updates, I'd switch to event-driven ingestion triggered by a change-data-capture stream or message queue."

**51. Walk through receiving documents, pulling from cloud storage, integrating into the RAG pipeline.**
"Data is pulled from the WMS/cloud storage on schedule → validated and cleaned → converted into text chunks (structured rows into templated sentences, unstructured docs chunked directly) → passed through the embedding model → stored in the vector database with metadata (source, date, route ID) → indexed and ready for retrieval by the RAG query pipeline."

**52. How do you handle corrupted files or files that fail during extraction?**
"Wrap extraction in try/except, log the failure with the file identifier, move the failed file to a 'quarantine' location instead of blocking the whole batch, and alert/flag it for manual review. The rest of the batch continues processing normally so one bad file doesn't stop the whole ingestion run."

**53. How do you handle large document volumes at scale?**
"Process in parallel batches (multiprocessing or async I/O for the API-bound parts), use bulk embedding API calls instead of one-by-one requests, incrementally update the vector index rather than rebuilding it from scratch each time, and monitor throughput/failures with logging and retries."

**54. Did you use the same extraction technique for all document types, or adapt based on content?**
"Adapted based on content — plain text/structured data went through direct parsing, while documents with tables or embedded images used layout-aware extraction tools so table structure and image regions weren't flattened into meaningless raw text."

**55. Which libraries/OCR service did you use for extracting text, tables, and images from PDFs?**
"Depending on the use case: pdfplumber/PyMuPDF for text and layout-aware extraction, camelot/tabula-style tools for table structure, and for scanned documents, an OCR engine (Tesseract or a cloud OCR service like Azure Document Intelligence) for converting image-based text into machine-readable text."

**56. How does OCR work internally, and how do you verify extraction accuracy?**
"OCR preprocesses the image (deskew, binarize, denoise), detects text regions, recognizes characters using a trained model, then post-processes with spellcheck/language-model correction. To verify accuracy, I'd spot-check extracted text against the source visually, look for garbled/low-confidence output (many OCR tools return confidence scores per word), and set a threshold below which a document is flagged for manual review."

**57. What extra precautions do you take when extracting PII (e.g., phone numbers) via OCR?**
"Mask or redact PII fields immediately after extraction before storing or embedding them, restrict access to raw extracted PII to only the necessary services, avoid sending PII to third-party LLM/embedding APIs unless there's a compliant data-handling agreement in place, and log access to any PII data for audit purposes."

**58. How do you store and maintain document structure/context after extraction?**
"Store extracted text with metadata that preserves its origin — page number, section, table vs. paragraph, source document ID — so retrieval can reconstruct context. For tables, keep row/column structure as structured JSON alongside a natural-language summary version for embedding, rather than collapsing everything into flat unstructured text."

---

## 6. Chunking Strategies

**59. How many/what types of chunking strategies are there?**
"The main ones: fixed-size chunking (character/token count), recursive character splitting (falls back through separators — paragraph, sentence, word), sliding window (overlapping fixed windows), semantic chunking (splits based on meaning/topic shifts using embeddings), and structure-aware chunking (splits along document structure like headers/sections)."

**60. Which chunking strategy did you use, and why?**
"I used fixed-size chunking with overlap as the baseline, and structure-aware chunking where documents had clear sections (like route manifests) since it kept logically related information together, which improved retrieval precision over blind character-count splitting."

**61. What chunk size and overlap percentage did you use, and how did you decide?**
"Roughly 500–1000 characters (about 150–250 tokens) per chunk, with 10–20% overlap. I decided this empirically — testing a few sizes and measuring retrieval relevance on sample queries; too small lost context, too large diluted the embedding's focus and hurt precision."

**62. Can you explain the sliding window chunking strategy in detail?**
"You define a fixed window size and a step size smaller than the window, so consecutive chunks overlap by the difference. For example, a 500-character window with a 400-character step gives 100 characters of overlap between consecutive chunks. This ensures information near a chunk boundary appears fully in at least one chunk, preventing loss of context that a non-overlapping split would risk."

**63. How did you decide what metadata to include in your chunks?**
"Based on what retrieval needed to filter or verify: source document/system, timestamp/date, route or truck ID, document type (structured record vs. note), and page/section reference — anything that let me either narrow the search space before similarity search or let the user verify where an answer came from."

**64. How do you decide chunking strategy for a PDF when structure alone isn't enough?**
"I'd combine structure-aware splitting (headers/sections as first pass) with a fallback fixed-size/recursive split within any oversized section, so no single chunk exceeds the embedding model's effective input size, while still respecting logical boundaries wherever the structure gives useful ones."

**65. How do you avoid losing context / splitting related content across multiple documents?**
"Use adequate overlap between chunks, include contextual metadata (like a chunk's parent section title) inside the chunk itself so it doesn't lose meaning in isolation, and when retrieving, pull a window of neighboring chunks (not just the single best match) so related content that got split still comes back together at generation time."

---

## 7. Embeddings

**66. What embedding model(s) did you use, and why?**
"OpenAI/Azure OpenAI embedding models (the text-embedding family) — chosen because they integrate cleanly with LangChain, produce strong semantic quality for enterprise text, and were already available through our Azure OpenAI setup, avoiding the need to self-host a separate embedding model."

**67. What does "parameter," "dimension," and "token limit" mean for an embedding model, and how do they relate to chunking?**
"Parameters are the model's internal learned weights (its size/capacity). Dimension is the length of the output vector (e.g., 1536) — how many numbers represent each piece of text's meaning. Token limit is the max input length the model accepts per call. These relate to chunking because each chunk must fit within the token limit, and the chosen dimension affects both storage size and retrieval precision in the vector store."

**68. What is the embedding dimension of common models (1536 vs 3072), and pros/cons?**
"OpenAI's text-embedding-3-small is 1536 dimensions, text-embedding-3-large can go up to 3072. Higher dimensions (3072) generally give better semantic precision/retrieval accuracy, but cost more storage, slower similarity search at scale, and higher API cost. Lower dimensions (1536 or reduced) are cheaper and faster but slightly less precise — the choice depends on whether retrieval accuracy or cost/latency is the priority for the use case."

**69. How do you handle embedding generation for long text — chunk first, or pass the whole text?**
"Always chunk first. Embedding models have token limits, and even within that limit, embedding a very long text produces a single vector that averages/dilutes many different topics, making retrieval less precise. Chunking into focused, smaller pieces before embedding gives much better retrieval granularity."

**70. Did you generate embeddings via a cloud endpoint, or locally? How did you manage this?**
"Via a cloud endpoint — Azure OpenAI's embedding API — managed through batched API calls to avoid per-request overhead, with retry logic for rate limits/transient failures, and caching so we didn't re-embed unchanged data on every refresh cycle."

**71. What happens if you use different embedding models for ingestion vs. retrieval?**
"Quality degrades significantly, potentially to the point of being unusable — different embedding models produce vectors in different, incompatible vector spaces, so a query embedded with Model B won't meaningfully align with document vectors embedded with Model A, even if the vectors have the same dimension. You must use the exact same embedding model consistently for both ingestion and query-time retrieval."

**72. How did you generate embeddings — via an LLM call, or does the vector DB/library handle it automatically?**
"Embeddings are generated by calling a dedicated embedding model/API (not the LLM itself, and not automatically by FAISS/ChromaDB) — the vector database just stores and indexes vectors you give it; some libraries like LangChain provide a wrapper that calls the embedding API for you as part of the pipeline, but the actual embedding computation happens via the embedding model."

---

## 8. Vector Databases & Search

**73. Which vector database(s) have you worked with?**
"FAISS and ChromaDB primarily. FAISS for fast in-memory similarity search, ChromaDB for persistence and metadata filtering in production. I'm also familiar with PgVector as an option when you want vectors inside an existing Postgres setup rather than a separate system."

**74. What is the difference between a normal database and a vector database?**
"A normal (relational) database stores structured rows and is optimized for exact-match queries and joins using indexes like B-trees. A vector database stores high-dimensional embeddings and is optimized for similarity search — finding the nearest vectors to a query vector by distance metric (cosine/Euclidean), using specialized indexes like HNSW or IVF rather than exact-match indexing."

**75. What algorithm does PgVector/FAISS use internally for vector search?**
"FAISS supports several index types — flat (exact, brute-force), IVF (inverted file index, clusters vectors then searches within relevant clusters), and HNSW (hierarchical navigable small world graphs, a graph-based approximate nearest neighbor method). PgVector supports IVFFlat and HNSW indexes too. HNSW is generally preferred for a good balance of speed and accuracy at scale."

**76. What is the difference between exact search and similarity (nearest-neighbor) search?**
"Exact search finds records that exactly match a query (like a WHERE clause). Similarity/nearest-neighbor search finds the closest vectors by distance in embedding space — there's no 'exact match,' just a ranked list of the most semantically similar items, which is what makes it suited for natural-language queries rather than precise field matching."

**77. What distance metrics are used in similarity search, and how do you choose?**
"Cosine similarity (measures angle between vectors, ignoring magnitude — most common for text embeddings), Euclidean/L2 distance (measures straight-line distance, sensitive to magnitude), and dot product (fast, works well when vectors are normalized). I used cosine similarity by default for text embeddings since it focuses on directional similarity in meaning rather than vector length, which usually correlates better with semantic relevance."

**78. Do you know about BM25? How does it compare to embedding/semantic search?**
"Yes — BM25 is a classic keyword-based ranking algorithm (an improvement on TF-IDF) that scores documents based on term frequency and inverse document frequency, good at exact keyword/lexical matching. Embedding-based semantic search instead matches based on meaning, so it can find relevant results even without exact keyword overlap. In practice, combining both (hybrid search) often outperforms either alone — BM25 catches exact identifiers/codes that embeddings might blur, while embeddings catch semantically related content that keyword search would miss."

**79. Why might you use two different vector databases in one project?**
"Different trade-offs for different needs — e.g., FAISS for fast, in-memory search during a batch/offline scoring step, and ChromaDB for the production-facing, persistent, metadata-filterable store that the live application queries. Using both lets you optimize each part of the pipeline for its specific performance and durability requirements rather than compromising with one tool for everything."

**80. Where was your FAISS vector database hosted?**
"FAISS ran as an in-memory index within our application service (loaded from a periodically rebuilt index file), rather than as a separate managed hosted service, since FAISS itself is a library, not a standalone server — for the persistent/production store, ChromaDB was run as a dedicated service."

**81. How does your vector search capability compare to a managed offering like Azure's vector search?**
"A managed offering like Azure AI Search's vector search gives built-in scaling, high availability, and integrated hybrid (keyword + vector) search without you managing infrastructure — trading some cost and vendor lock-in for reduced operational overhead. Our FAISS/ChromaDB setup gave more control and lower direct cost, at the expense of us owning scaling, backup, and availability ourselves — the right choice depends on team size and how much infra ownership you want."

**82. What challenges did you face getting documents searchable via embeddings/FAISS?**
"Main challenges were: getting chunk size/overlap right so retrieval was both precise and complete, handling structured data that doesn't embed well without first converting it to natural language, keeping the index fresh as underlying data changed without needing a full rebuild every time, and tuning similarity thresholds so irrelevant results didn't get pulled into the LLM's context."

---

## 9. Prompting & Guardrails

**83. What prompting techniques are you familiar with?**
"Zero-shot and few-shot prompting, chain-of-thought prompting (asking the model to reason step by step), role/system prompting (setting the model's persona and constraints), and RAG-style context injection (grounding prompts with retrieved data). I also use structured output prompting — asking for JSON-formatted responses to make outputs easy to parse programmatically."

**84. How did you implement guardrails and orchestrate LLMs in your solution?**
"System-level prompt instructions constraining scope (e.g., 'only answer logistics/planning questions using the provided context'), output validation (checking the response format/content before returning it to the UI), and orchestration via LangChain chains that controlled the sequence: retrieve → validate context → generate → post-process, rather than letting the LLM call be a black box."

**85. How did you keep the LLM within boundaries and prevent off-topic/erratic outputs?**
"Clear system prompts defining scope and refusal behavior for out-of-scope questions, lower temperature for more predictable outputs, retrieval-based grounding so answers are anchored to real data, and post-processing checks that flag or filter unexpected output patterns before showing them to the user."

**86. How do you prevent the AI from mixing up contexts and ensure it only uses relevant information?**
"Metadata filtering before similarity search (e.g., only search within the relevant route/date scope), reranking to prioritize the most relevant retrieved chunks, explicit prompt instructions to ignore irrelevant context, and keeping the number of retrieved chunks focused (not stuffing in excessive, loosely related context that increases the chance of the model blending unrelated information)."

---

## 10. LangChain / LangGraph & Agent Workflows

**87. What is the difference between LangChain and LangGraph? Why choose one over the other?**
"LangChain is built around chains — mostly linear sequences of steps (retrieve → prompt → generate), great for straightforward pipelines. LangGraph models workflows as a graph of nodes and edges, supporting loops, conditionals, and shared state — needed when the workflow isn't linear, e.g., an agent that retrieves, checks if the answer is good enough, and loops back with a refined query, or coordinates multiple agents. I'd choose LangChain for simple RAG pipelines and LangGraph when I need stateful, cyclical, or multi-agent orchestration."

**88. What is the difference between LangChain and Microsoft Foundry? Have you used Azure?**
"LangChain is an open-source orchestration framework you self-manage, giving you flexibility to mix any LLM/vector store/tool. Microsoft/Azure AI Foundry is a managed platform providing model hosting, evaluation, monitoring, and deployment tooling in one integrated environment, trading some flexibility for reduced operational overhead. Yes, I've used Azure — specifically Azure OpenAI and Azure AI Services for LLM access in enterprise-compliant environments."

**89. What are nodes, edges, start/end nodes, and conditionals in LangGraph/agent workflows?**
"Nodes represent individual steps or functions (e.g., 'retrieve documents,' 'call LLM,' 'validate output'). Edges define the flow between nodes — which node runs next. The start node is the entry point of the graph; end nodes mark where execution terminates. Conditional edges let the graph branch dynamically based on some function's output — for example, routing to a 'retry retrieval' node if the first retrieval's confidence score is too low, instead of always following a fixed path."

**90. Why implement a wrapper around a chain when solving a problem?**
"A wrapper lets you add cross-cutting concerns without modifying the chain's core logic — things like logging, error handling, retries, input validation, or caching. It keeps the chain itself focused and reusable while the wrapper handles operational concerns consistently across multiple chains."

**91. What is checkpointing in LangGraph? Write a program that uses a checkpointer.**
"Checkpointing saves the graph's state at each step so execution can be paused and resumed later — critical for long-running or human-in-the-loop workflows, or recovering after a failure without restarting from scratch.
```python
from langgraph.graph import StateGraph, END
from langgraph.checkpoint.memory import MemorySaver

def retrieve_node(state):
    state[\"context\"] = \"retrieved data\"
    return state

def generate_node(state):
    state[\"answer\"] = f\"Answer using {state['context']}\"
    return state

graph = StateGraph(dict)
graph.add_node(\"retrieve\", retrieve_node)
graph.add_node(\"generate\", generate_node)
graph.set_entry_point(\"retrieve\")
graph.add_edge(\"retrieve\", \"generate\")
graph.add_edge(\"generate\", END)

checkpointer = MemorySaver()
app = graph.compile(checkpointer=checkpointer)

result = app.invoke({\"query\": \"plan route\"}, config={\"configurable\": {\"thread_id\": \"item_3234\"}})
print(result)
```"

**92. What happens after compiling the graph with a checkpointer? What if you use app.invoke instead of graph.invoke?**
"Compiling with a checkpointer returns a runnable app object that automatically persists state after every node execution, keyed by a thread ID. You call `.invoke()` on the *compiled app* (what I named `app` above) — there's no separate `graph.invoke`; `graph` is just the builder object before compilation. Calling invoke on the compiled app runs the graph and saves/resumes state via the checkpointer using the given thread ID."

**93. Do you need a thread/session ID to invoke a checkpointed graph? Write the statement, explain resuming.**
"Yes — the thread ID is what the checkpointer uses to know which saved state to load/save.
```python
result = app.invoke({\"query\": \"plan route\"}, config={\"configurable\": {\"thread_id\": \"item_3234\"}})
```
To resume a paused/interrupted workflow, you call `.invoke()` again with the *same* thread_id — the checkpointer loads the last saved state for that thread instead of starting fresh, and execution continues from where it left off."

**94. What interrupts exist in the graph? Why use a "read anchor" in LangGraph?**
"LangGraph supports `interrupt_before` / `interrupt_after` on specific nodes, pausing execution at that point — useful for human-in-the-loop approval before a sensitive action executes. A 'read anchor' (checkpoint reference point) lets you inspect or reload a specific saved state without re-executing prior steps, which is useful for debugging or auditing exactly what state the workflow was in at a given point."

**95. What is the difference between invoke and stream?**
"`invoke` runs the whole graph/chain and returns the final result only once everything completes. `stream` returns intermediate outputs incrementally as they're produced — useful for showing a chatbot's response token-by-token in the UI, or observing intermediate node outputs in a multi-step agent for debugging/monitoring, rather than waiting for the entire run to finish."

**96. Which framework did you use to build agents, and how did you evaluate the agent?**
"I used LangChain for agent/tool-calling logic within the RAG pipeline. Evaluation was based on: whether the agent selected the correct tool for a given query, whether final answers were grounded and accurate against retrieved data, and manual review of a sample of interactions against expected planner queries, since agent behavior is harder to evaluate with pure automated metrics alone."

**97. How do you monitor a LangGraph agent (and hallucinations) in production?**
"Log every node's input/output in the graph run (traceable via tools like LangSmith), track confidence/faithfulness scores on generated answers against retrieved context, set up alerts for anomalous patterns (very long chains, repeated retries, empty retrieval results), and periodically sample real production interactions for human review to catch hallucinations automated metrics might miss."

**98. What protocol did you use for agent deployment/communication?**
"Primarily HTTP/REST request-response for the main query flow, since planners' requests were interactive but not requiring persistent low-latency streaming everywhere. For displaying incremental LLM output in the UI (typing effect), I'd use streaming responses (HTTP streaming or WebSocket) rather than waiting for the full response before showing anything."

---

## 11. Agents & Tool Calling

**99. Have you worked with AI agents (LangChain/LangGraph)?**
"Yes — in the Load Planning assistant, the LLM had access to structured tools (querying shipment data, checking truck capacity) rather than answering purely from static context, giving it some agentic tool-calling behavior on top of the core RAG retrieval."

**100. Scenario: agent has Addition and Multiplication tools. For "2 + 3 × 5?", how does it arrive at the answer?**
"The agent (LLM) first parses the expression and recognizes operator precedence — multiplication before addition, per standard math rules. It calls the Multiplication tool with (3, 5) → gets 15. Then it calls the Addition tool with (2, 15) → gets 17. The key point is the agent needs to reason about order of operations *before* deciding which tool call sequence to make — it shouldn't just apply tools left-to-right blindly."

**101. How would you evaluate the performance of such an agent?**
"Test against a set of expressions with known correct answers, checking both the final numeric result and whether the *correct tools were called in the correct order* — since a right answer via wrong reasoning could still be a fluke on more complex inputs. I'd also test edge cases (parentheses, negative numbers, division by zero) to see how robust the tool-selection reasoning is."

**102. If an agent's API call fails mid-workflow, how would you design it to handle the failure?**
"Wrap each tool/API call with retry logic (exponential backoff for transient errors), catch and classify errors (transient vs. permanent), and on failure, either retry, fall back to a default/cached response, or surface a clear error state to the user rather than silently failing or hallucinating a fabricated result."

**103. When the API becomes available again, do you restart from the beginning or resume from the last successful step? How would you implement recovery?**
"Resume from the last successful step, not restart from scratch — this is exactly where LangGraph's checkpointing helps: persist state after each successful node, and on recovery, reload the last saved checkpoint by thread ID and continue execution from there rather than repeating already-completed work."

---

## 12. Synthetic Data Generation (Scenario)

**104. Given a schema, how would you generate a synthetic dataset?**
"Define a prompt template with placeholders for each schema field, specify realistic value ranges/categories per field, and call the LLM in batches to generate rows matching the schema, validating each generated row against the schema's data types and constraints before accepting it."

**105. How would you generate 100K–200K rows efficiently, scaling with LangChain/LangGraph?**
"Generate in batches (e.g., 50–100 rows per LLM call) rather than one row per call, run batches concurrently using async calls to respect rate limits while maximizing throughput, and use LangGraph if the generation process needs conditional logic — e.g., checking a batch's diversity/quality and looping back to regenerate if it's too repetitive, before moving to the next batch."

**106. How do you ensure diversity in generated data and avoid duplicates across batches?**
"Vary the prompt per batch (rotating example seeds, categories, constraints) rather than reusing an identical prompt, and after generation, run deduplication — exact-match hashing for identical rows, and embedding-based similarity checks to catch near-duplicate rows that differ only in wording."

**107. How would you implement parallel batch generation?**
"Use asyncio to fire off multiple batch-generation API calls concurrently (respecting the LLM provider's rate limits with a semaphore to cap concurrency), collect results as they complete, and merge them into the growing dataset, with retry logic for any failed batches."

**108. Would you reuse the same prompt for every batch? If not, how do you add variations?**
"No — reusing the exact same prompt tends to produce repetitive, low-diversity outputs. I'd add variation dynamically: rotate through a list of example rows/categories to seed each batch differently, adjust value ranges or constraints per batch, and as batch count scales up (say 100K → 200K), programmatically expand the variation set (more categories, wider ranges) rather than just repeating the same variation cycle more times, to keep diversity proportional to volume."

**109. How would you handle different intents per batch, and who provides those intent values at runtime?**
"Define an 'intent' parameter per batch (e.g., transaction type, customer segment, region) that's injected into the prompt template for that batch. These intent values would typically come from a config file or a controlling script/orchestrator at runtime — either a predefined list covering all needed categories, or dynamically pulled from the target schema's categorical field distributions so generated data mirrors real-world proportions."

---

## 13. RAG Evaluation & Monitoring

**110. How would you evaluate a RAG system end-to-end?**
"Two layers: retrieval evaluation (precision@k, recall@k, MRR — is the system finding the right chunks) and generation evaluation (faithfulness — does the answer match the retrieved context; relevance — does it answer the actual question). I'd combine automated metrics (LLM-as-judge for faithfulness), a curated test set of representative queries with expected answers, and periodic human review of real production queries."

**111. What KPIs would you use for the retrieval component specifically?**
"Precision@k, Recall@k, MRR (Mean Reciprocal Rank), and retrieval latency. I'd also track a 'no relevant result found' rate — how often the top-k results contain nothing actually relevant — since that directly signals gaps in the knowledge base or chunking strategy."

**112. Explain Precision using a concrete retrieval example (not just the definition).**
"Say a planner asks 'which trucks are available for Route 12 tomorrow?' and the system retrieves the top 5 chunks. If 4 of those 5 chunks are actually about Route 12 truck availability, and 1 is about an unrelated route, Precision@5 is 4/5 = 0.8 — it measures how much of what you retrieved was actually relevant, not how much relevant material exists overall."

**113. How do you determine whether retrieved documents are actually relevant?**
"Compare the retrieved chunk's content directly against what the query is asking — either through human judgment on a sample set, or automated relevance scoring using an LLM-as-judge that reads the query and chunk and rates relevance, which scales better than manual review for large test sets."

**114. If you don't have labeled data, how would you evaluate retrieval — alternative approaches?**
"Generate synthetic question-answer pairs from your own documents using an LLM (ask it to write a question a document chunk would answer), then check whether retrieval for that generated question actually surfaces the source chunk — this creates a pseudo-labeled test set without manual labeling. Also useful: LLM-as-judge scoring on live queries, and tracking user feedback signals (thumbs up/down, follow-up rephrasing rate) as an implicit relevance signal."

**115. Did you prioritize precision, recall, F1, or faithfulness? How do you trade off accuracy vs. latency?**
"For a planning-assistant use case, I prioritized faithfulness and precision over recall — a wrong or hallucinated recommendation is more costly than occasionally missing a relevant but non-critical chunk. For the accuracy vs. latency trade-off, I'd tune the top-k retrieved (fewer chunks = faster but riskier to miss context; more chunks = slower and noisier) and use reranking selectively — only add the reranking step when initial precision testing showed it was needed, since it adds latency."

**116. Have you used an evaluation framework, or tools like LangSmith? How do you monitor a deployed GenAI app?**
"I've used logging/tracing patterns similar to what LangSmith provides — capturing each step's input/output (query, retrieved chunks, final prompt, generated answer) for later analysis. In production, I'd monitor latency per stage, retrieval hit rate, faithfulness scores on a sampled subset, error/failure rates, and cost per query, with alerting on anomalies (e.g., sudden drop in retrieval relevance or spike in latency)."

---

## 14. Chatbot Memory & Caching

**117. What kind of caching would you implement in a chatbot, and why?**
"Cache frequent/repeated queries and their embeddings (so identical or near-identical questions don't re-trigger a full embedding + retrieval + generation cycle), and cache retrieved context for recently-accessed data that hasn't changed — using Redis for fast in-memory lookups. This reduces latency and LLM/embedding API cost for common questions."

**118. If a chatbot supports multiple conversations, why might it fail to recall something from Day 1 when asked on Day 60?**
"Most likely because conversation history/context isn't being persisted long-term — either the context window simply can't hold 60 days of history (it gets truncated or dropped), or the system only stores short-term session memory that resets/expires, without a separate long-term memory store (like a vector database of past conversation summaries) that could be retrieved on demand."

**119. How would you solve long-term memory retention in a chatbot?**
"Instead of stuffing full history into the prompt, summarize and embed key facts/preferences from past conversations into a vector store as 'memory' — then at query time, retrieve relevant memories the same way you'd retrieve RAG context, and inject only what's relevant to the current question. This scales far better than trying to keep growing raw conversation history inside a limited context window."

---

## 15. Multimodal / Scanned-Document RAG

**120. How would you design an end-to-end RAG pipeline for a 100-page scanned PDF (images only) returning text + diagram?**
"Run OCR to extract text page by page, and separately detect/extract embedded images/diagrams (using layout detection). Chunk and embed the OCR'd text as usual, storing each chunk with metadata linking it to its page number and any image(s) on that page. At query time, retrieve the most relevant text chunk(s), then look up and return the associated image(s) via that page-number/image-ID link alongside the generated text answer."

**121. How do you extract images (not just text) from a scanned PDF, and where do you store them?**
"Use a PDF-processing library (PyMuPDF/pdf2image combined with layout detection) to detect and crop image regions distinct from text regions on each page, save each extracted image to object storage (like S3/Azure Blob) with a unique ID, and store that ID plus its page/section reference in the same metadata store used for text chunks."

**122. How do you associate the generated answer with the correct extracted image and display both together?**
"Since each text chunk's metadata includes its page number, and each extracted image is also tagged with its page number, I can look up any images sharing the page number of the retrieved/cited chunk and return their storage URLs alongside the generated answer — the frontend then renders the text and fetches/displays the linked image(s) together."

**123. Have you worked with graph databases or graph structures?**
"My hands-on experience is primarily with vector databases (FAISS/ChromaDB) rather than graph databases like Neo4j. Conceptually, I understand graph-based retrieval (GraphRAG) — representing entities and relationships as a graph to answer questions requiring multi-hop reasoning that pure vector similarity struggles with — and I'd be comfortable picking it up given my LangGraph experience with node/edge-based workflow modeling."

---

## 16. Azure / Cloud Services & Deployment

**124. What Azure services did you use in your project?**
"Azure OpenAI for LLM and embedding access, and Azure AI Services more broadly for AI capabilities within an enterprise-compliant environment. On the AWS side (a different project), I used AWS Bedrock for managed foundation model access and AWS Lambda for serverless functions."

**125. What is the difference between Azure App Services and Virtual Machines?**
"App Services is a fully managed PaaS — you deploy your code/container and Azure handles the OS, scaling, patching, and load balancing for you, which is faster to get running but gives less low-level control. Virtual Machines are IaaS — you get a full VM you configure and manage yourself (OS, runtime, scaling), giving maximum control and flexibility at the cost of more operational overhead. I'd choose App Services for standard web apps/APIs, and VMs only when I need custom OS-level configuration or software that doesn't fit the PaaS model."

**126. How do you secure Azure services and your application to prevent data leaks?**
"Azure AD-based authentication and RBAC for access control, Key Vault for secrets/API keys instead of hardcoding them, network isolation via VNets and private endpoints for sensitive services, encryption at rest and in transit, and audit logging via Azure Monitor to detect anomalous access patterns."

**127. Which cloud platform did you deploy on, and why? Which are you most comfortable with?**
"I've used both Azure (OpenAI, AI Services) in enterprise/compliance-sensitive contexts and AWS (Bedrock, Lambda) for serverless/managed model access. I'm comfortable with both; the choice usually came down to what the client's existing infrastructure and compliance requirements were, rather than a personal preference."

**128. Which LLMs did you connect with, including inside Azure OpenAI?**
"GPT-4-class models through Azure OpenAI, and I've also worked with LLaMA-family open models in other contexts where a self-hosted or open-weight option was preferred for cost or data-residency reasons."

**129. How did you manage authentication and access to Azure Blob Storage?**
"Access was managed through a service account/managed identity for the backend service — not exposing storage credentials to end users or the frontend directly. The frontend never talked to Blob Storage directly; all access went through the backend API, which validated the user's permissions before fetching or serving any blob content."

**130. How do you generate a signed URL so users can open a cited PDF when only the backend has Blob Storage access?**
"The backend generates a SAS (Shared Access Signature) URL — a time-limited, scoped token appended to the blob's URL — using its service credentials, and returns that SAS URL to the frontend. The user's browser can then access that specific blob directly via the signed URL for a limited time window, without ever having direct storage account credentials."

**131. How do you deploy your AI application and expose its APIs? Did you handle deployment personally?**
"The application was containerized with Docker and deployed via CI/CD (Jenkins), with REST APIs exposed through the backend service, typically behind a load balancer/API gateway. I was involved in the application-level deployment configuration (Dockerfile, environment config, API structure); infrastructure provisioning was often handled in coordination with a DevOps/platform team rather than entirely by me alone."

**132. What post-deployment challenges did you face, and how did you resolve them?**
"Common ones: retrieval relevance drifting as underlying data changed (fixed by scheduling regular re-indexing), occasional latency spikes under load (addressed with caching and connection pooling), and edge-case queries producing unhelpful answers (addressed by refining prompts and adding fallback responses for out-of-scope questions)."

**133. How many users currently use your application, and how would you scale it for a sudden spike?**
"[Adjust to real numbers if known] It served planners across the logistics team — not an enormous user base, but concurrent usage could spike during peak planning hours. To scale for a spike (e.g., 500+ concurrent requests), I'd rely on horizontal auto-scaling of the backend service, connection pooling for the DB, caching frequent LLM responses, and queuing/backpressure for the AI service specifically since LLM calls are the slowest, most rate-limited part of the pipeline."

**134. Is your system microservices, monolith, or event-driven? Which is best for a banking product?**
"Service-oriented — the AI/RAG service was a distinct backend service from core business logic (WMS integration, order management), callable independently. For a banking product, I'd recommend a hybrid: microservices for core domains (accounts, transactions, compliance) combined with event-driven communication between them, since banking needs strong auditability, independent scaling of sensitive services, and loose coupling for downstream processes like fraud detection and notifications."

**135. What was the infrastructure setup, and which CI/CD pipeline do you use?**
"Docker containers deployed via Jenkins-based CI/CD pipelines — code changes triggered automated builds, tests (Jest/React Testing Library on frontend, unit tests on backend), and deployment to the target environment after passing checks."

**136. Did you use Kubernetes / container orchestration — which service specifically?**
"My hands-on orchestration experience is more with Docker and Jenkins-based deployment pipelines than deep Kubernetes administration. I understand Kubernetes concepts (pods, services, deployments, auto-scaling) and would be comfortable working within a Kubernetes-managed environment, but I'd position my direct hands-on depth as stronger in Docker/CI-CD than in K8s cluster management specifically."

**137. How would you make an open-source LLM efficient enough to support many concurrent users?**
"Techniques include quantization (reducing model precision, e.g., to 8-bit or 4-bit, to cut memory/compute needs), batching multiple requests together for GPU efficiency, using an efficient inference server (like vLLM or TGI) that supports continuous batching and KV-cache optimization, and horizontally scaling multiple model replicas behind a load balancer for concurrent throughput."

**138. How do you process data in parallel, and scale your AI pipeline? How do you manage API rate limits?**
"Use async I/O for concurrent LLM/embedding API calls, multiprocessing for CPU-bound preprocessing (like OCR or chunking large volumes), and a task queue (Celery/Redis) to distribute work across multiple workers. For rate limits, I'd implement a semaphore/token-bucket style limiter client-side to stay under the provider's cap, plus exponential backoff and retry logic for 429 responses."

---

## 17. API Security & Authentication

**139. How do you secure API calls between frontend (React/Next.js) and backend (FastAPI)?**
"JWT-based authentication issued at login, sent as a Bearer token on every request and validated server-side on each call. Role/permission checks happen server-side (never trust client-side role flags), HTTPS everywhere, CORS configured to only allow the known frontend origin, and rate limiting/input validation on every endpoint to prevent abuse."

**140. How do you ensure an API call is genuinely coming from your UI and not an attacker?**
"You can't fully guarantee the *specific* origin of a request (anyone can call your public API), so the real defense is: validate authentication (a valid JWT tied to a legitimate user session) and authorization (does this user have permission for this action) on every request, rather than relying on origin/CORS checks alone — CORS protects browsers, not a determined attacker calling the API directly."

**141. How do you prevent someone from forging/manipulating a JWT to add roles via Postman?**
"JWTs are signed (typically HMAC or RSA) with a server-side secret/private key — the signature is verified on every request, so any tampering with the payload (like adding an 'admin' role) invalidates the signature and the request is rejected. The critical practice is: never trust or read claims like 'role' from an unverified token, always verify the signature server-side before trusting any claim inside it, and keep the signing secret/key secure and never exposed to the client."

**142. Is the FastAPI backend a separate service/container? Is there a BFF layer?**
"Yes, the backend ran as its own containerized service, separate from the frontend build. Depending on the project, there was sometimes a thin BFF-style layer aggregating/shaping backend responses for the frontend's needs, but core business and AI logic lived in the backend service itself, not duplicated across a BFF and the main API."

**143. What is CORS, and how did you implement CORSMiddleware in FastAPI?**
"CORS (Cross-Origin Resource Sharing) is a browser security mechanism that blocks a web page from making requests to a different origin than the one it was served from, unless the server explicitly allows it via response headers.
```python
from fastapi.middleware.cors import CORSMiddleware

app.add_middleware(
    CORSMiddleware,
    allow_origins=[\"https://myfrontend.com\"],
    allow_credentials=True,
    allow_methods=[\"GET\", \"POST\", \"PUT\", \"DELETE\"],
    allow_headers=[\"*\"],
)
```
I explicitly listed the known frontend origin(s) rather than using a wildcard `*`, especially since `allow_credentials=True` requires specific origins, not a wildcard."

---

## 18. Backend / Data Architecture Deep-Dive

**144. Walk through the architecture and implementation patterns for your project.**
"Frontend (React/TypeScript) → REST API layer (FastAPI-style backend) → service layer containing business logic and the RAG/LLM orchestration → data layer (WMS integration, vector DB, relational DB for structured records). In code, you'd see route handlers that stay thin (just parsing input/calling services), a service layer with the actual RAG pipeline and business logic, and a repository/data-access layer isolating DB and vector store queries — this separation keeps each layer testable and swappable independently."

**145. Was the backend connecting directly to the database, or through a service layer?**
"Through a service/repository layer — route handlers never touched the ORM or raw queries directly. The UI never talks directly to the database either; it always goes through the backend API, which enforces business rules and access control before any data operation happens."

**146. Was your backend a single FastAPI service or a microservices setup?**
"The core business/CRUD logic and the AI/RAG logic were split into distinct services rather than one monolithic app — the AI service could be scaled, deployed, and iterated on independently from the core planning/business API, which is a lightweight microservices-style separation rather than a single large FastAPI monolith."

---

## 19. FastAPI — Core Concepts

**147. What is dependency injection in FastAPI (and Python generally)? Why yield instead of return for a DB dependency?**
"Dependency injection means declaring what a function needs (a DB session, current user, config) as parameters resolved externally, rather than the function creating them itself — in FastAPI this is done via `Depends()`. For a DB connection dependency, you use `yield` instead of `return` because it lets you run cleanup code (closing the session) *after* the request finishes:
```python
def get_db():
    db = SessionLocal()
    try:
        yield db
    finally:
        db.close()
```
`return` would give you the session but there'd be no clean, request-scoped place to close it afterward — `yield` turns the dependency into a context-manager-like generator so setup happens before, and teardown happens after, the request is handled."

**148. What are path parameters vs. query parameters?**
"Path parameters are part of the URL path itself and typically identify a specific resource, e.g., `/users/{user_id}` — required by definition. Query parameters come after `?` in the URL, e.g., `/users?active=true`, and are typically optional filters/modifiers rather than identifying a specific resource. In FastAPI, path parameters are declared as function parameters matching the path's `{}` placeholders, while query parameters are just regular function parameters with default values."

**149. How did you use Pydantic in FastAPI (validation, serialization)?**
"Defined Pydantic models for request bodies and response schemas — FastAPI automatically validates incoming JSON against the model (rejecting malformed/invalid data with a clear 422 error before it reaches business logic), and serializes outgoing responses to match the defined response model, which also auto-generates accurate OpenAPI/Swagger documentation."

**150. What is the key difference between Django and FastAPI, and how do you choose?**
"Django is a full-featured, batteries-included framework (ORM, admin panel, templating, auth) best suited for traditional server-rendered web apps or when you want a lot built in out of the box. FastAPI is a lightweight, async-first framework focused on building fast APIs, with automatic validation (Pydantic) and OpenAPI docs, but you assemble the rest of your stack (ORM, auth) yourself. I'd choose FastAPI for API-first/microservice/AI-integration projects needing async performance, and Django for a more traditional full-featured web app where its built-ins save significant time."

**151. Is FastAPI synchronous or asynchronous? Difference between ASGI and WSGI?**
"FastAPI supports both — you can write `def` (sync) or `async def` (async) route handlers, but it's built on ASGI, which natively supports async, unlike older WSGI-based frameworks. WSGI (Web Server Gateway Interface) handles one request at a time per worker in a blocking, synchronous model. ASGI (Asynchronous Server Gateway Interface) supports async I/O, WebSockets, and long-lived connections, allowing a single worker to handle many concurrent requests efficiently when using `async def` and non-blocking I/O calls."

---

## 20. FastAPI — Background Tasks, Caching & Async

**152. Have you heard of Celery and Redis? What is Celery used for?**
"Redis is an in-memory store used as a cache, message broker, or fast key-value store. Celery is a distributed task queue for running work outside the request/response cycle — background jobs like sending emails, processing large batches of embeddings, or generating reports — typically using Redis or RabbitMQ as the broker to pass tasks to worker processes."

**153. How do you implement background tasks in FastAPI?**
"For lightweight work, FastAPI's built-in `BackgroundTasks` parameter runs a function after the response is returned. For heavier or longer-running work, I'd use Celery with Redis as the broker — the endpoint enqueues a task and returns immediately with a task ID, while a separate Celery worker process handles the actual work asynchronously, and the client polls a status endpoint or gets notified when it's done."

**154. Have you implemented in-memory or Redis caching in a FastAPI application?**
"Yes — Redis caching for frequently requested, expensive-to-compute responses (like common LLM query results or repeated data lookups), with a TTL (time-to-live) so cached values expire and stay reasonably fresh, reducing both latency and load on the DB/LLM API for repeat queries."

**155. Have you implemented startup/shutdown events in FastAPI?**
"Yes — using the `lifespan` context manager (or the older `@app.on_event('startup'/'shutdown')`) to initialize resources like DB connection pools, the vector store client, or the LLM client once when the app starts, and to gracefully close/release them when the app shuts down, rather than creating/tearing down connections per request."

---

## 21. FastAPI — Deployment, Scaling & Rate Limiting

**156. How have you deployed your FastAPI application? Which server runs inside the image?**
"Docker container with Gunicorn managing multiple Uvicorn worker processes inside the image — Gunicorn handles process management (restarts, graceful reloads) while Uvicorn workers handle the actual ASGI/async request serving."

**157. What is the difference between Gunicorn and Uvicorn, and how do you decide worker count?**
"Uvicorn is the ASGI server that actually runs FastAPI's async code. Gunicorn is a process manager that can supervise multiple Uvicorn worker processes for multi-core utilization and resilience (auto-restarting crashed workers). Worker count is generally set based on CPU cores — a common starting formula is `(2 × CPU cores) + 1` — then tuned based on load testing, since I/O-bound apps (heavy on external API/LLM calls) can often handle more concurrent load per worker than pure CPU-bound apps."

**158. How would you configure FastAPI to handle 100 req/sec on a 1 CPU, 1 GB machine?**
"On a single CPU, you can't get true multi-core parallelism, so the priority is maximizing async I/O efficiency: use `async def` handlers with non-blocking DB/HTTP clients so the single worker isn't blocked waiting on I/O, keep the worker count low (1–2, since more workers on 1 CPU just adds context-switching overhead without real parallel gains), add caching to avoid redundant work, and use connection pooling sized conservatively given the 1GB memory limit. If 100 req/sec truly needs more raw throughput than a single core allows, the honest answer is you need to scale horizontally (multiple small instances behind a load balancer) rather than force it all onto one constrained machine."

**159. How would you design a FastAPI REST API to handle 100,000 requests/second?**
"No, a single endpoint definition alone isn't remotely enough. You'd need: horizontal scaling across many instances behind a load balancer, aggressive caching (Redis/CDN) for anything cacheable, async I/O throughout with efficient connection pooling, a message queue to absorb bursts and process asynchronously where the response doesn't need to be synchronous, database read replicas/sharding since a single DB instance can't handle that write/read volume, and careful profiling to find and eliminate bottlenecks — 100K req/sec is an infrastructure and architecture problem, not just an application-code problem."

**160. How would you implement rate limiting (e.g., 50 calls/hour/user) in FastAPI?**
"Use Redis to track a counter per user with a sliding-window or fixed-window key (e.g., `rate_limit:user_123:2026-08-23-14`), incrementing on each request and setting a TTL matching the window. As a FastAPI dependency, check the current count before processing the request — if it exceeds the limit, return a 429 Too Many Requests response; otherwise increment and proceed. Libraries like `slowapi` or `fastapi-limiter` implement this pattern out of the box if you don't want to hand-roll it."

---

## 22. Database & Migrations

**161. Have you worked with SQL or NoSQL databases? Which ORM have you used?**
"Primarily relational/SQL databases for structured business data (customer records, transactions, shipment data), typically with SQLAlchemy as the ORM in Python/FastAPI projects. I've also worked with vector databases (ChromaDB/FAISS), which function more like a specialized NoSQL store for embeddings rather than a general document/NoSQL DB like MongoDB."

**162. How do you handle migrations in FastAPI models (Alembic)?**
"Use Alembic to auto-generate migration scripts from SQLAlchemy model changes, review the generated script for correctness (auto-generation isn't always perfect, especially for renames or complex constraint changes), test it against a staging DB copy, then apply it in production via the deployment pipeline, keeping migrations version-controlled alongside the codebase."

**163. If you add a column and data, then roll back the migration, is the data also rolled back? Will Alembic allow dropping a column with data?**
"If the down-migration simply drops the column, yes — any data in that column is lost, Alembic won't stop you by default since it just executes the DDL you wrote. Safe rollback steps: before rolling back, back up or archive the column's data (e.g., copy it to a separate table), confirm the application no longer depends on that column, test the rollback against a staging copy first, and only then run the down-migration in production."

**164. How do you resolve Alembic migration conflicts when two developers modify the same table on different branches?**
"Alembic migrations form a linear chain via `down_revision` pointers, so two branches creating divergent migrations from the same parent revision creates a conflict (two heads). Resolve it by using `alembic merge` to create a merge migration that reconciles both branches into a single head, carefully reviewing that both sets of schema changes apply correctly together and don't conflict at the DDL level (e.g., both trying to add a column with the same name differently)."

---

## 23. Deep Learning

**165. Can you describe your deep learning project experience? Why was DL necessary there?**
"My direct hands-on depth is more in applying pretrained deep learning models (LLMs, embedding models) within RAG/GenAI applications, rather than training deep learning models from scratch. Where deep learning was necessary was specifically for semantic understanding — the transformer-based embedding models used in my RAG pipeline give far better semantic similarity than classical keyword-based methods (like TF-IDF), which was essential for a natural-language query interface where users don't phrase questions using exact database terminology."

---

## 24. Healthcare AI / Domain Project Example

**166. Explain your healthcare AI (donor-matching) project.**
*(This isn't on your resume — if asked, either redirect to your actual projects or, if you do have such experience, describe it factually. Sample structure if relevant:)* "Problem statement: matching donors to recipients based on multiple compatibility criteria that go beyond simple exact-match filters. Approach: use semantic/embedding-based search over donor and recipient profiles to capture nuanced compatibility signals, combined with structured filtering for hard constraints (blood type, location). Design: a retrieval layer over profile embeddings plus a rules engine for non-negotiable medical constraints. Deployment: [describe your actual client/country if this applies to you]."

**167. Why use AI/semantic search for donor matching instead of basic database filters?**
"Basic filters only catch exact-match criteria (blood type, age range) but miss nuanced compatibility factors described in free-text medical notes or preference criteria that don't map cleanly to rigid database fields. Semantic search can surface good matches based on meaning and context in those notes, which purely structured filtering would miss, while still using hard structured filters for non-negotiable medical constraints as a first-pass narrowing step."

---

## 25. AI-Accelerated Delivery (Scenario)

**168. How would you set up a framework to deliver a production-ready, AI-heavy banking product in 1 year instead of 4?**
"I'd invest early in: a strong modular architecture (so teams can work in parallel without blocking each other), heavy use of AI coding assistants (Copilot/Claude) for boilerplate and repetitive code so engineers focus on domain-critical logic, automated testing and CI/CD from day one (not bolted on later) to catch issues fast, and close, continuous collaboration with compliance/security from the start rather than a late-stage audit — compressing timeline safely means parallelizing and automating, not skipping steps."

**169. How do you avoid hallucination and "junk code" while aggressively fast-tracking delivery with AI?**
"Treat AI-generated code like any other pull request — mandatory code review, strong test coverage requirements, and static analysis/linting gates in CI that must pass before merge. For AI-generated business logic (like RAG-based decisions), ground it in retrieval and validate against real data rather than trusting free-form generation, and maintain a 'trust but verify' culture where speed doesn't waive the review process."

**170. What percentage of effort savings / code generation have you achieved using AI tools?**
"[Give your honest, defensible estimate] In my experience using GitHub Copilot, Codex, and Claude AI for boilerplate, test scaffolding, and documentation, I've seen roughly a 20–30% reduction in time spent on repetitive coding tasks — the savings are largest on boilerplate and test generation, and smaller on complex business logic that still needs careful human design and review."

**171. What's your approach to choosing architecture for AI-heavy systems, and specifically for banking?**
"Start from the domain's actual requirements: does it need strict transactional consistency (favor a more monolithic/tightly-coupled core for money movement), independent scaling of AI/inference workloads (favor separating the AI service out as its own scalable microservice), or loose coupling for auditability and downstream processing (favor event-driven communication). For banking specifically, I'd lean hybrid: a consistent, tightly controlled core transaction service, with AI/analytics/fraud-detection and notification services decoupled via events, since AI workloads have very different scaling and failure-tolerance profiles than core ledger operations."

---

## 26. Python Fundamentals

**172. What are decorators in Python, and can you give a practical example?**
"A decorator is a function that wraps another function to add behavior without modifying its source code. Practical example — a timing decorator:
```python
import functools, time

def timer(func):
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        print(f\"{func.__name__} took {time.time() - start:.3f}s\")
        return result
    return wrapper

@timer
def fetch_data():
    time.sleep(1)
    return \"data\"
```
I used this pattern in FastAPI route handlers to log execution time for performance monitoring."

**173. What is the difference between a list and a tuple (and other data structures)? Trade-offs?**
"List — ordered, mutable, O(1) amortized append, good when the collection changes over time. Tuple — ordered, immutable, hashable (usable as dict keys/set elements), slightly more memory-efficient, good for fixed data like coordinates. Dict — key-value pairs, O(1) average lookup, insertion-ordered since Python 3.7. Set — unordered unique elements, O(1) average membership check, ideal for deduplication. Trade-off summary: mutability and hashability are the key differences that determine which structure fits a given use case."

**174. Do you know about call by reference vs. call by value in Python?**
"Python is technically neither in the classic sense — it's 'call by object reference' (or 'call by sharing'). When you pass an argument, you're passing a reference to the object, but whether changes are visible outside the function depends on whether the object is mutable. If you mutate a mutable object (like a list) inside the function, the caller sees the change, because both refer to the same object. If you reassign the parameter to a new object (or the object is immutable, like an int or string), the caller's original variable is unaffected, because reassignment just points the local name to a different object."

**175. What is the type of user input in Python, and why is it always a string?**
"`input()` always returns a `str`, regardless of what the user types, because input is fundamentally raw text from stdin — Python doesn't guess whether '42' should be an int or 'True' should be a bool. It's up to the developer to explicitly convert it (e.g., `int(input())`), which also forces you to handle invalid input gracefully with validation/exception handling."

**176. What is idempotency? Examples of idempotent vs. non-idempotent operations.**
"Idempotency means performing the same operation multiple times has the same effect as performing it once. Idempotent: `UPDATE users SET status='active' WHERE id=5` (repeating gives the same end state), HTTP `DELETE`/`PUT` on a resource, setting a value directly. Non-idempotent: `UPDATE users SET login_count = login_count + 1` (each run changes the result), HTTP `POST` creating a new resource (calling it twice creates two records) — this is why idempotency keys matter for retried operations like payments."

**177. How do you handle memory allocation issues in complex Python code?**
"Profile memory usage first (using `tracemalloc` or `memory_profiler`) to find the actual source rather than guessing, use generators/iterators instead of loading entire large datasets into lists in memory, process large data in chunks/streams, explicitly release references to large objects when no longer needed, and for very large-scale processing, offload to a language/tool better suited for memory-heavy numeric work (e.g., NumPy's efficient array storage instead of plain Python lists)."

**178. Rate yourself (1–5) in Python, databases, ORMs, and DevOps.**
"Python: 4/5 — strong in application development, FastAPI, async, and AI integration. Databases: 3.5/5 — solid relational DB design and querying, plus vector DB experience; less deep on advanced DBA tuning. ORMs: 3.5/5 — comfortable with SQLAlchemy for a few years in FastAPI projects, though I'd want to verify against your actual years of hands-on ORM use. DevOps: 3/5 — comfortable with Docker and Jenkins CI/CD, growing in deeper Kubernetes/infra-as-code experience."

**179. Do you have experience with authentication/authorization?**
"Yes — JWT-based authentication and role-based access control (RBAC), which I implemented at MUFG for controlling access to customer records and business opportunities based on user roles, plus standard practices like password hashing and token expiration/refresh handling."

**180. What does it mean that tuples can be dictionary keys? Which objects are hashable? Can a tuple ever be unhashable?**
"An object is hashable if it has a fixed hash value for its lifetime, which requires immutability — tuples, strings, ints, and frozensets are hashable; lists, dicts, and sets are not (they're mutable). A tuple *can* become unhashable if it contains an unhashable element — for example, `(1, [2, 3])` is unhashable because it contains a list, even though the tuple itself is 'immutable' as a container; Python checks hashability recursively based on the actual contents, not just the outer type."

**181. Are you aware of SOLID principles?**
"Yes — Single Responsibility (a class/function should have one reason to change), Open/Closed (open for extension, closed for modification), Liskov Substitution (subtypes should be substitutable for their base type without breaking behavior), Interface Segregation (prefer many small, specific interfaces over one large general one), and Dependency Inversion (depend on abstractions, not concrete implementations) — I apply these especially in the service-layer/repository-pattern separation I use in FastAPI backends, keeping business logic decoupled from data-access details."

---

## 27. Live Coding Exercises

**182. Write pseudocode/code to detect if user input is a mathematical or general query, and route it accordingly.**
```python
import re

def is_math_query(text: str) -> bool:
    # Looks for digits combined with math operators, or common math keywords
    math_pattern = re.compile(r'\d+\s*[\+\-\*/\^]\s*\d+')
    math_keywords = ['calculate', 'sum', 'average', 'sqrt', 'percentage']
    return bool(math_pattern.search(text)) or any(kw in text.lower() for kw in math_keywords)

def route_query(text: str):
    if is_math_query(text):
        return handle_math_query(text)
    else:
        return handle_general_query(text)  # e.g., send to RAG/LLM pipeline

def handle_math_query(text: str):
    # route to a calculator/tool instead of the LLM directly
    return f\"Routed to math tool: {text}\"

def handle_general_query(text: str):
    return f\"Routed to RAG/LLM pipeline: {text}\"
```
"In a real agent, I'd use an LLM-based intent classifier rather than pure regex for robustness, but this regex/keyword approach is a fast, cheap first-pass filter before deciding whether to invoke a calculator tool or the general RAG pipeline."

**183. Write code to fetch prime numbers between 1 and 10.**
```python
def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True

primes = [n for n in range(1, 11) if is_prime(n)]
print(primes)  # [2, 3, 5, 7]
```

**184. Write Python code to calculate a cumulative total of sales for the last three months.**
```python
from datetime import datetime, timedelta

def cumulative_sales_last_3_months(sales_records):
    # sales_records: list of dicts like {'date': datetime, 'amount': float}
    cutoff = datetime.now() - timedelta(days=90)
    recent = [r for r in sales_records if r['date'] >= cutoff]
    recent.sort(key=lambda r: r['date'])

    cumulative = []
    running_total = 0
    for r in recent:
        running_total += r['amount']
        cumulative.append({'date': r['date'], 'cumulative_total': running_total})
    return cumulative
```

**185. Write a SQL query to delete duplicates from a table using window functions.**
```sql
WITH ranked AS (
    SELECT
        id,
        ROW_NUMBER() OVER (
            PARTITION BY column1, column2  -- columns that define a "duplicate"
            ORDER BY id
        ) AS row_num
    FROM my_table
)
DELETE FROM my_table
WHERE id IN (
    SELECT id FROM ranked WHERE row_num > 1
);
```
"`ROW_NUMBER()` assigns a rank within each duplicate group ordered by id, keeping the first occurrence (row_num = 1) and marking the rest for deletion."

**186. Write a Python function to find all unique contiguous subarrays where total cost doesn't exceed a budget.**
```python
def subarrays_within_budget(costs, budget):
    n = len(costs)
    result = []
    seen = set()
    for start in range(n):
        total = 0
        for end in range(start, n):
            total += costs[end]
            if total > budget:
                break
            subarray = tuple(costs[start:end + 1])
            if subarray not in seen:
                seen.add(subarray)
                result.append(list(subarray))
    return result

# Example
print(subarrays_within_budget([1, 2, 3], 4))  # [[1], [1, 2], [2], [3], [2, 3]... within budget]
```
"This is O(n²) in the worst case; I'd mention that a sliding window could optimize the 'total ≤ budget' check itself, but for uniqueness we still need to track distinct subarrays."

**187. Extract and count unique 'ORG' entities from a dataset using spaCy.**
```python
import spacy
from collections import Counter

nlp = spacy.load(\"en_core_web_sm\")

def count_org_entities(texts):
    org_counter = Counter()
    for text in texts:
        doc = nlp(text)
        orgs = {ent.text for ent in doc.ents if ent.label_ == \"ORG\"}
        org_counter.update(orgs)
    return org_counter

texts = [\"Walmart partnered with Coforge.\", \"Coforge is expanding.\"]
print(count_org_entities(texts))  # Counter({'Coforge': 2, 'Walmart': 1})
```

**188. Given a string, count character frequency (ignoring special characters/spaces) and sort ascending.**
```python
# Without Counter
def char_freq_manual(s):
    freq = {}
    for ch in s:
        if ch.isalnum():
            ch = ch.lower()
            freq[ch] = freq.get(ch, 0) + 1
    return dict(sorted(freq.items(), key=lambda x: x[1]))

# With Counter
from collections import Counter

def char_freq_counter(s):
    cleaned = [ch.lower() for ch in s if ch.isalnum()]
    freq = Counter(cleaned)
    return dict(sorted(freq.items(), key=lambda x: x[1]))

print(char_freq_manual(\"Hello, World!\"))
```

**189. Write pseudocode/code for a RAG application, including selective log retrieval with metadata filtering.**
```python
def rag_query(user_query: str, metadata_filters: dict, vector_store, llm):
    # 1. Embed the query
    query_vector = embed(user_query)

    # 2. Retrieve with metadata filtering (e.g., only logs from a specific route/date range)
    candidates = vector_store.similarity_search(
        query_vector,
        top_k=10,
        filter=metadata_filters  # e.g., {\"route_id\": \"R12\", \"date\": {\"$gte\": \"2026-08-01\"}}
    )

    # 3. Optional rerank
    reranked = rerank(user_query, candidates)[:5]

    # 4. Build augmented prompt
    context = \"\\n\".join(chunk.text for chunk in reranked)
    prompt = f\"Context:\\n{context}\\n\\nQuestion: {user_query}\\nAnswer only using the context above.\"

    # 5. Generate
    return llm.generate(prompt)
```

**190. Write a simple Flask API that accepts two values via POST and returns their sum.**
```python
from flask import Flask, request, jsonify

app = Flask(__name__)

@app.route('/add', methods=['POST'])
def add():
    data = request.get_json()
    a = data.get('a')
    b = data.get('b')
    if a is None or b is None:
        return jsonify({'error': 'Both a and b are required'}), 400
    return jsonify({'sum': a + b})

if __name__ == '__main__':
    app.run(debug=True)
```

**191. Write the Dockerfile to containerize a Flask/FastAPI app.**
```dockerfile
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 8000

CMD [\"gunicorn\", \"-k\", \"uvicorn.workers.UvicornWorker\", \"-w\", \"4\", \"-b\", \"0.0.0.0:8000\", \"main:app\"]
```

**192. Write a FastAPI signup endpoint that collects and saves user details.**
```python
from fastapi import FastAPI, Depends
from pydantic import BaseModel, EmailStr
from passlib.hash import bcrypt

app = FastAPI()

class SignupRequest(BaseModel):
    name: str
    email: EmailStr
    phone: str
    password: str

@app.post(\"/signup\")
def signup(payload: SignupRequest, db=Depends(get_db)):
    hashed_pw = bcrypt.hash(payload.password)
    user = User(
        name=payload.name,
        email=payload.email,
        phone=payload.phone,
        password_hash=hashed_pw,
    )
    db.add(user)
    db.commit()
    return {\"message\": \"User created successfully\", \"user_id\": user.id}
```

**193. Create a custom exception for age-based voting eligibility.**
```python
class UnderageError(Exception):
    def __init__(self, age):
        self.age = age
        super().__init__(f\"Age {age} is below the voting eligibility of 18.\")

def check_voting_eligibility(age):
    if age < 18:
        raise UnderageError(age)
    return \"Eligible to vote\"

try:
    check_voting_eligibility(16)
except UnderageError as e:
    print(f\"Error: {e}\")
```

**194. Find all pairs in an array whose values sum to a target (e.g., sum = 9).**
```python
def find_pairs(arr, target):
    seen = set()
    pairs = []
    for num in arr:
        complement = target - num
        if complement in seen:
            pairs.append((complement, num))
        seen.add(num)
    return pairs

print(find_pairs([1, 8, 3, 6, 2, 7], 9))  # [(1, 8), (3, 6), (2, 7)]
```

**195. Find the second-largest number in a list without built-in functions or sets.**
```python
def second_largest(nums):
    largest = second = float('-inf')
    for n in nums:
        if n > largest:
            second = largest
            largest = n
        elif n > second and n != largest:
            second = n
    return second

print(second_largest([4, 1, 7, 7, 3, 9]))  # 7
```

**196. Write a reusable decorator to convert dict keys between snake_case and camelCase (nested), without modifying the original dict — with and without regex.**
```python
# Without regex
import copy, functools

def to_camel(key):
    parts = key.split('_')
    return parts[0] + ''.join(p.title() for p in parts[1:])

def to_snake(key):
    result = []
    for ch in key:
        if ch.isupper():
            result.append('_')
            result.append(ch.lower())
        else:
            result.append(ch)
    return ''.join(result)

def _convert(data, converter):
    if isinstance(data, dict):
        return {converter(k): _convert(v, converter) for k, v in data.items()}
    elif isinstance(data, list):
        return [_convert(item, converter) for item in data]
    return data

def key_case_converter(direction=\"camel\"):
    converter = to_camel if direction == \"camel\" else to_snake
    def decorator(func):
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            result = func(*args, **kwargs)
            return _convert(copy.deepcopy(result), converter)
        return wrapper
    return decorator

# With regex
import re

def to_camel_re(key):
    return re.sub(r'_([a-zA-Z])', lambda m: m.group(1).upper(), key)

def to_snake_re(key):
    s1 = re.sub(r'(.)([A-Z][a-z]+)', r'\\1_\\2', key)
    return re.sub(r'([a-z0-9])([A-Z])', r'\\1_\\2', s1).lower()
```
"The `copy.deepcopy` ensures the original dict passed in isn't mutated — we always build and return a new structure. Verbally: I'd explain this decorator wraps any function returning a dict/list of dicts and recursively converts key naming convention, which is a common need when a Python backend (snake_case) serves a JS frontend (camelCase)."

---

## 28. Concurrency in Python

**197. Difference between asyncio, multithreading, and multiprocessing — which is faster, when to use each?**
"asyncio — single-threaded, cooperative concurrency via an event loop, best for I/O-bound work (API/DB/LLM calls) where the program mostly waits rather than computes; very lightweight, can handle thousands of concurrent I/O operations. Multithreading — multiple threads sharing memory, but Python's GIL means only one thread executes Python bytecode at a time, so it doesn't give true parallelism for CPU-bound work, though it still helps for I/O-bound tasks using blocking libraries. Multiprocessing — separate processes with separate memory, bypassing the GIL, giving true parallelism for CPU-bound work (embedding generation, heavy computation). Which is faster depends on the workload: I/O-bound → asyncio is usually fastest and most resource-efficient; CPU-bound → multiprocessing wins."

**198. Have you used ThreadPoolExecutor? Can you safely run tasks in parallel without it? Why is a thread pool recommended?**
"Yes — `concurrent.futures.ThreadPoolExecutor` for running multiple blocking I/O calls concurrently without manually managing raw `threading.Thread` objects. You *can* run tasks with raw threads directly, but a thread pool is recommended because it manages a fixed, bounded number of reusable threads (avoiding the overhead and resource exhaustion risk of spawning unlimited unmanaged threads), and gives you a clean `Future`-based API for collecting results and exceptions."

**199. Difference between ThreadPoolExecutor and ProcessPoolExecutor? What is a "concurrent worker"?**
"`ThreadPoolExecutor` runs tasks in a pool of threads within the same process (subject to the GIL — good for I/O-bound work). `ProcessPoolExecutor` runs tasks in separate processes (true parallelism, no GIL limitation — good for CPU-bound work), but with higher overhead for inter-process communication and data serialization. A 'concurrent worker' just refers to one unit (a thread or process) in the pool actively capable of executing a task at the same time as the others — the pool size determines how many tasks can genuinely run at once."

---

## 29. Testing

**200. Which unit-testing frameworks have you used? What are fixtures? Are they only for databases?**
"Pytest on the Python/backend side, and Jest with React Testing Library on the frontend. Fixtures in pytest are reusable setup/teardown functions you can inject into test functions as parameters — they handle 'arrange' logic (creating test data, mock objects, DB sessions) so you don't repeat setup code in every test. Fixtures are not only for databases — they're used for anything reusable: mock API clients, temporary files, authenticated test users, configuration objects, etc."

**201. What is conftest.py in pytest, and how do you use a fixture from it in a test function?**
"`conftest.py` is a special pytest file where you define fixtures (and hooks) that are automatically available to all test files in that directory and its subdirectories, without needing to import them explicitly. To use one, you simply declare it as a parameter in your test function by name:
```python
# conftest.py
import pytest

@pytest.fixture
def sample_user():
    return {\"name\": \"Satish\", \"email\": \"test@example.com\"}

# test_users.py
def test_user_email(sample_user):
    assert sample_user[\"email\"] == \"test@example.com\"
```
Pytest automatically discovers and injects `sample_user` because it's defined in `conftest.py` in scope for that test."

---

## 30. Connection Pooling

**202. What is connection pooling, and what design considerations affect pool size?**
"Connection pooling maintains a set of reusable open DB connections instead of opening/closing one per request, since establishing a connection has real overhead. Pool size should absolutely not equal total requests per second (e.g., 100,000 req/sec should never mean 100,000 connections) — most requests are short-lived, so you size the pool for expected *concurrent* DB operations, not total throughput. Key considerations: the database's max_connections limit (must account for pool size × number of app instances all staying under it), typical query duration (longer queries hold connections longer, needing a larger pool for the same concurrency), and load testing to tune from a reasonable starting point (e.g., 10–20 per instance) rather than guessing a large number."

---

## 31. System Design — Transaction / Fintech API

**203. Design a fault-tolerant, idempotent, scalable transaction API (deduct A, credit B, update balances, notify both).**
"API layer accepts the request with a client-generated idempotency key, checks a fast store (Redis/DB) for that key first — if already processed, return the stored result immediately. If new, execute the debit/credit inside a single database transaction (ACID) so both balance updates and the transaction record insert commit atomically together — never partially. Store the idempotency key and result as part of that same transaction. After commit, publish an event to a queue for the notification step, rather than sending notifications synchronously — keeping the core transaction fast and decoupled from slower downstream side effects. Scalability comes from horizontal scaling of the API layer and having the notification/queue consumers scale independently."

**204. The notification step uses an expensive third-party API — how do you handle it asynchronously? Role of a queue?**
"After the transaction commits, publish a 'transaction.completed' event to a message queue (Redis Streams/RabbitMQ) — this is triggered right after the DB commit succeeds, not before, so notification failures never block or roll back the actual money movement. A separate worker process consumes from the queue and calls the expensive third-party notification API, with its own retry/backoff logic if that call fails, independent of the core transaction path's performance or reliability."

**205. Write pseudocode for the transaction API covering idempotency, exception handling, and notifications.**
```python
def process_transaction(request, idempotency_key):
    existing = idempotency_store.get(idempotency_key)
    if existing:
        return existing  # already processed, return same result

    try:
        with db.begin_transaction():
            debit(request.account_a, request.amount)
            credit(request.account_b, request.amount)
            txn_record = save_transaction_record(request)
            idempotency_store.save(idempotency_key, txn_record)
    except InsufficientFundsError as e:
        return {\"status\": \"failed\", \"reason\": str(e)}
    except Exception as e:
        log_error(e)
        return {\"status\": \"error\", \"reason\": \"internal error, please retry\"}

    # Only after successful commit
    queue.publish(\"transaction.completed\", txn_record)
    return {\"status\": \"success\", \"transaction_id\": txn_record.id}
```
"The notification step itself just returns an immediate 'queued' acknowledgment to the caller (the transaction API doesn't wait on notification delivery) — the actual notification success/failure is handled and logged separately by the queue consumer."

---

## 32. System Design — Broader ML/AI Scenarios

**206. How would you design a real-time anomaly detection system for financial transactions?**
"Stream transactions through a message queue (Kafka), apply feature extraction in real time (transaction amount, frequency, location deviation from user history), score each transaction against a trained anomaly model (statistical thresholds or a lightweight ML model like isolation forest, running with low latency), and flag/hold high-score transactions for review while letting normal ones pass through. Feed confirmed fraud/non-fraud outcomes back to periodically retrain the model, and monitor false-positive/false-negative rates continuously."

**207. How would you design and deploy a recommendation system for a large e-commerce platform?**
"Combine collaborative filtering (user-item interaction patterns) with content-based filtering (product attributes) in a hybrid model, precompute recommendations in batch for most users (cached), with real-time re-ranking based on the current session's activity for freshness. Deploy behind a recommendation service with caching (Redis) for low-latency serving, and A/B test model changes before full rollout, tracking click-through and conversion rate as the core success metrics."

**208. How would you design an end-to-end QA system over a large corpus of legal documents?**
"This is a RAG use case at larger scale: ingest and OCR/parse legal documents preserving section/clause structure, chunk along logical legal sections (not arbitrary character counts, since legal meaning depends heavily on clause boundaries), embed and store with rich metadata (document type, jurisdiction, date, section), retrieve with metadata filtering plus semantic search, and enforce very strict grounding/citation in generation since legal answers without traceable sourcing are risky. I'd also add a disclaimer and human-review step given the high stakes of legal accuracy."

**209. How would you diagnose and improve an existing translation system that's fluent but inaccurate?**
"Fluent-but-inaccurate typically means the model is confidently generating plausible-sounding but factually wrong translations — a classic hallucination-style failure mode even in translation. I'd evaluate with reference-based metrics (BLEU/COMET) against known-correct translations to quantify the gap, inspect failure patterns (specific phrase types, domain-specific terminology, idioms), and address it via domain-specific fine-tuning or glossary/terminology-constrained decoding, plus potentially adding a retrieval step for domain-specific terms rather than relying purely on the base model's generalization."

**210. How would you architect a feature engineering pipeline for enterprise tabular data (Pandas/NumPy/scikit-learn)?**
"Ingest raw data into a staging layer, apply cleaning (handle missing values, outliers) and transformation steps (encoding categoricals, scaling numerics) using scikit-learn Pipelines so preprocessing steps are reproducible and can't leak information between train/test splits, version the feature engineering logic alongside the model code, and separate the pipeline into ingestion → cleaning → feature computation → feature store stages so features can be reused consistently across training and inference."

**211. How would you implement automated release gates to block deployment if toxicity/hallucination exceeds a threshold?**
"Add an automated evaluation stage in the CI/CD pipeline that runs the model/prompt against a curated test set after any change, scoring outputs for toxicity (using a classifier) and faithfulness/hallucination rate (LLM-as-judge against known-correct context), and fail the pipeline (block deployment) if scores fall below a defined threshold — treating these evaluation metrics as a required gate exactly like unit tests, not an optional post-launch check."

**212. How do you ensure architectural consistency during a technical handover of a GenAI platform from a vendor to in-house?**
"Require comprehensive documentation of the architecture, prompts, chunking/embedding configuration, and evaluation criteria as part of the handover — not just working code. Run the in-house team through a structured knowledge-transfer period with hands-on pairing, and validate consistency by re-running the vendor's own evaluation suite against the in-house-maintained system to confirm behavior hasn't drifted before fully cutting over."

**213. How would you troubleshoot a production chatbot generating duplicate reports, quality issues, and rising latency after weeks of uptime?**
"Rising latency after weeks of uptime often points to a resource leak (unclosed DB/HTTP connections, growing in-memory cache without eviction, or an ever-growing conversation context being resent every call) — I'd check memory/connection metrics over time first. Duplicate reports suggest either a missing idempotency check or a retry mechanism firing more than once without dedup. I'd check logs for retry patterns and confirm whether background jobs or webhooks lack idempotency protection, and restart/patch the leaking resource as an immediate mitigation while fixing the root cause."

**214. How would you approach model versioning?**
"Version prompts, embedding model versions, and any fine-tuned/base model identifiers explicitly alongside the application code (not just relying on 'whatever is latest' from the provider), tag each production deployment with the exact model/prompt version used, and keep old versions available for rollback. For RAG systems specifically, also version the embedding model tied to the vector index, since switching embedding models requires re-indexing the entire vector store."

---

## 33. Production Performance, Latency & Incident Debugging

**215. How can you check and reduce latency/timeout issues in production (ms to seconds)?**
"Add stage-level timing logs (retrieval time, LLM call time, DB query time) to isolate where the slowdown is happening rather than guessing. Common fixes: add caching for repeated queries, use connection pooling to avoid connection setup overhead, check if the vector store index needs optimization/rebuilding, check for LLM provider-side rate limiting causing queued/retried calls, and check for N+1 query patterns or unbounded result sets that grew over time."

**216. How do you optimize cost for a high-volume GenAI application?**
"Cache frequent/repeated LLM and embedding calls, use smaller/cheaper models for simpler sub-tasks (classification, routing) and reserve the largest model only for final generation, batch embedding calls instead of one-at-a-time, reduce prompt size by only sending the minimum necessary retrieved context (fewer, better-ranked chunks rather than a large noisy context), and monitor cost per query as a first-class metric to catch regressions early."

**217. How do you monitor and log LLM latency and tokenization?**
"Log input/output token counts and latency per call (most LLM APIs return token usage in the response), track these over time in a monitoring dashboard, and set alerts for latency spikes or unexpected jumps in token usage (which often signals prompt bloat or a retrieval step returning too much context)."

**218. How do you design backend scalability for sudden usage spikes?**
"Horizontal auto-scaling behind a load balancer, queue-based decoupling for anything that doesn't need a synchronous response, caching for repeated requests, and rate limiting/backpressure to protect downstream dependencies (especially the LLM provider, which has its own rate limits) so a spike degrades gracefully instead of cascading into full failures."

**219. All API requests suddenly return 500 errors with no recent deployments/config changes — how do you investigate?**
"First check external dependencies — is a downstream service (DB, LLM provider, third-party API) down or degraded, since 'no recent deployment' strongly points outward rather than to your own code. Check application logs and error traces for the actual exception type, check infrastructure metrics (CPU/memory/disk, are instances crashing or out of resources), and check for expired credentials/certificates or a hit rate limit from a dependency — these are common causes of sudden failures with zero code changes on your side."

**220. What database-side issues could cause this? Why is calling an external API inside a DB transaction a problem, and how do you mitigate it?**
"Database-side causes: connection pool exhaustion, a lock/deadlock building up, disk space filling up, or a runaway query holding locks. Calling an external API inside a DB transaction is dangerous because the transaction holds locks on rows/tables for the entire duration of that external call — if the API is slow or hangs, you're holding those locks far longer than necessary, blocking other transactions and potentially cascading into widespread lock contention across the whole system. Mitigation: do the DB work and commit first, then make the external API call afterward (outside any open transaction), using the queue/async pattern discussed earlier for anything not required synchronously."

---

## 34. Scenario-Based / Behavioral

**221. How do you convince a stakeholder when your solution is more optimized than theirs, without offending them?**
"I start by understanding their reasoning — often there's context I'm missing. Then I frame the conversation around shared goals ('we both want this to scale reliably') rather than 'my way is better,' and back my case with data or a small proof-of-concept comparing both approaches on a concrete metric, so the decision is grounded in evidence rather than opinion. I also acknowledge genuine trade-offs in my own approach — that builds trust and makes the recommendation land better."

**222. How do you convince a stakeholder to give you more time when a deadline isn't feasible due to R&D/complexity?**
"I'd present a clear breakdown of where the complexity/risk actually lies (not just 'it's hard'), show what's achievable in the original timeline versus what needs more time, and propose options — a phased delivery with a reduced scope by the original deadline, plus the full solution shortly after, so the stakeholder still gets value on time rather than hearing a flat 'no.'"

**223. What would you do if your data pipeline/ingestion isn't working properly, or a native connection is no longer available?**
"First isolate whether it's a transient issue (retry-able) or a genuine change (API deprecated, credentials expired, schema changed) by checking logs and error messages. I'd communicate the issue and impact to stakeholders early rather than silently trying to fix it for hours, implement a temporary fallback if one exists (cached/last-known-good data) to minimize downstream impact, then fix the root cause and add monitoring/alerting so the same failure is caught faster next time."

**224. As a senior, how do you handle a junior team member who can't understand stakeholder requirements, risking escalation?**
"I'd step in early — pair with them to walk through the requirement together, clarify ambiguous points directly with the stakeholder if needed, and help them break the requirement into smaller, clearer tasks. The goal is unblocking them and preventing the escalation while also using it as a coaching moment, not just taking the task away from them entirely unless the timeline truly doesn't allow for it."

**225. How would you structure communication to address a project setback in an all-hands meeting?**
"Lead with the factual situation (what happened, current impact) without sugar-coating or over-apologizing, follow immediately with the concrete plan to address it (what's being done, by when), and be clear about what support/decisions are needed from the group. Keeping it factual, forward-looking, and specific builds more confidence than a vague reassurance."

**226. What will you do if a stakeholder asks for pipeline changes outside your working hours?**
"I'd acknowledge the request promptly, but set clear expectations about when I can realistically address it rather than immediately jumping on it outside working hours as a default — for something genuinely urgent/production-impacting, I'd handle it and flag it as an exception, but for a standard change request, I'd confirm I'll pick it up during my next working hours, unless there's an on-call/support agreement that says otherwise."

---

## 35. Git

**227. How do you update your feature branch with the latest changes from main?**
```bash
git checkout feature-branch
git fetch origin
git merge origin/main
# or, for a cleaner linear history:
git rebase origin/main
```
"I use merge when I want to preserve the full history and it's a shared branch others are also working on, and rebase when I want a clean, linear commit history on my own feature branch before opening a PR."

**228. What's the difference between git pull (merge) and git pull --rebase?**
"`git pull` by default does a fetch + merge — it brings in the remote changes and creates a merge commit if your local branch has diverged, preserving both histories. `git pull --rebase` does a fetch + rebase instead — it replays your local commits on top of the updated remote branch, producing a cleaner, linear history without an extra merge commit. I use `--rebase` on my own feature branches to keep history tidy, and plain merge on shared/long-lived branches where rewriting history could disrupt collaborators."

---

## 36. Compensation, Notice Period & Closing

**229. What is your current CTC / salary?**
"[Fill in your real current CTC]. I'm looking for an increase in line with market standards for this role and my GenAI/full-stack skill set — happy to discuss specifics once we're aligned on the role."

**230. How long will it take you to exit your current company?**
"[Fill in your real notice period, e.g., '60 days from my resignation date'] — I can check with my current employer about the possibility of a shorter buyout if that's important for your timeline."

**231. Do you know anything about our organization? Did you get context from a referrer?**
*(Research the specific company before each interview and personalize this.)* "[Fill in: 1–2 sentences on what the company does, a recent product/news item, and why it interests you, plus mention if a referrer gave you context]."

**232. Why did you resign without another offer in hand?**
*(Only answer if this applies to you — otherwise skip/adjust.)* "[Adjust to your real situation] I wanted to fully focus on finding the right next step rather than rushing into something misaligned with my growth into GenAI/full-stack work, and I felt confident in my skills and experience translating into strong opportunities."

**233. Do you have any questions for us?**
"Yes — a few I always like to ask: What does success look like in this role in the first 6 months? What's the team's current biggest technical challenge with your GenAI/AI initiatives? And how does the team approach evaluating and improving RAG/LLM system quality over time? [Add 1–2 more tailored to the specific company/role after your own research]."

---

## Quick Prep Priorities
- **Section 3 (RAG fundamentals), Section 6 (chunking), Section 7 (embeddings), Section 8 (vector DBs)** — near-guaranteed in every GenAI interview. Know these cold.
- **Section 10 (LangGraph)** — practice the checkpointing code out loud; it's a common differentiator question.
- **Section 27 (live coding)** — actually type these out on a blank editor, don't just read them.
- **Section 19–22 (FastAPI/DB)** — expect 3–5 follow-up questions if you mention FastAPI on your resume.
- **Fill in your real numbers** for Q19/Q49/Q133/Q170/Q229/Q230 before your next interview.