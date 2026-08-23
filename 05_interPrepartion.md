# RAG Architecture (Retrieval-Augmented Generation) -- Interview Notes

## Interview Question

> **Explain your RAG architecture end-to-end.**

**RAG (Retrieval-Augmented Generation)** is an architecture that
combines a **Large Language Model (LLM)** with a **Vector Database** to
generate accurate, context-aware answers using enterprise data instead
of relying only on the model's training knowledge.

The workflow starts with **data ingestion**, where documents from
**PDFs, APIs, databases, or SharePoint** are collected.

These documents are then **chunked into smaller pieces with some
overlap** to preserve context.

Next, each chunk is converted into a **vector embedding** using an
embedding model, and those embeddings are stored in a **Vector
Database** like **ChromaDB** or **FAISS**.

When a user asks a question, the query is converted into an embedding
using the **same embedding model**.

The vector database performs **semantic similarity search** (usually
using **cosine similarity**) and retrieves the most relevant chunks.

These retrieved chunks are combined with the user's question to create
an **augmented prompt**, which is sent to the **LLM** through services
like **AWS Bedrock** or **GPT**.

Since the model receives relevant context, it generates more accurate
answers with fewer hallucinations.

### Project Example (Walmart Logistics)

> In my Walmart logistics project, this approach helped planners query
> **shipment details, truck capacity, and route information** using
> natural language and receive context-aware recommendations.

------------------------------------------------------------------------

# End-to-End Workflow

1.  **Data Ingestion**
    -   Collect documents from PDFs, APIs, databases, or SharePoint.
2.  **Chunking**
    -   Split documents into smaller chunks.
    -   Keep **overlap** to preserve context.
3.  **Embedding Generation**
    -   Convert each chunk into a vector.
4.  **Store in Vector Database**
    -   Save embeddings in ChromaDB or FAISS.
5.  **User Query**
    -   User asks a question.
6.  **Query Embedding**
    -   Convert the question into an embedding.
7.  **Similarity Search**
    -   Find the most relevant chunks using cosine similarity.
8.  **Prompt Augmentation**
    -   Combine retrieved chunks with the user's question.
9.  **LLM Generation**
    -   Send the prompt to AWS Bedrock or GPT.
10. **Final Response**
    -   Return a context-aware answer.

------------------------------------------------------------------------

# Easy-to-Remember Architecture Flow

``` text
Ingest Data
      ↓
Chunk Documents
      ↓
Generate Embeddings
      ↓
Store in ChromaDB / FAISS
      ↓
User Query
      ↓
Query Embedding
      ↓
Similarity Search
      ↓
Retrieve Top Chunks
      ↓
LLM (Bedrock / GPT)
      ↓
Final Response
```

------------------------------------------------------------------------

# Why Do We Chunk Documents?

Instead of sending a 100-page PDF to the LLM, we split it into smaller
pieces.

**Benefits:** - Faster retrieval - Lower cost - Better relevance - Fits
within the LLM context window

Example:

``` text
100-page PDF
      ↓
Chunk 1
Chunk 2
Chunk 3
Chunk 4
```

------------------------------------------------------------------------

# Why Do We Use Embeddings?

Embeddings convert text into numbers that capture **meaning**, not just
words.

Example:

  Query              Retrieved
  ------------------ --------------------
  "truck space"      "vehicle capacity"
  "shipment delay"   "late delivery"

Even though the words are different, embeddings understand that the
meaning is similar.

------------------------------------------------------------------------

# Why Use a Vector Database Instead of SQL?

This is one of the most common interview follow-up questions.

  SQL Database               Vector Database
  -------------------------- --------------------------------------------
  Exact keyword matching     Semantic meaning matching
  Good for structured data   Good for unstructured text
  `WHERE name='truck'`       Finds "vehicle capacity" for "truck space"
  Returns exact matches      Returns similar meaning

### Best Interview Answer

> **"SQL searches exact keywords, while a vector database searches based
> on semantic meaning, so it can retrieve relevant information even when
> the user's wording is different."**

------------------------------------------------------------------------

# Common Interview Follow-Up Questions

### Q1. Why use overlap while chunking?

**Answer:** Overlap prevents important context from being lost when a
sentence is split between two chunks.

### Q2. Why use the same embedding model for documents and queries?

**Answer:** Both must exist in the same vector space so similarity
search works correctly.

### Q3. What similarity metric is commonly used?

**Answer:** Cosine similarity is the most common because it compares the
direction of vectors rather than their magnitude.

### Q4. What causes hallucinations in RAG?

**Answer:** Hallucinations happen when retrieval returns poor context or
the prompt is weak. Better chunking, retrieval, and prompting reduce
them.

### Q5. What is the role of AWS Bedrock?

**Answer:** Bedrock provides managed access to foundation models so we
can generate responses without hosting models ourselves.

------------------------------------------------------------------------

# 30-Second Revision

> **RAG combines an LLM with a Vector Database. Documents are ingested,
> chunked, converted into embeddings, and stored in ChromaDB or FAISS.
> The user's query is embedded using the same model, similar chunks are
> retrieved using cosine similarity, and those chunks are added to the
> prompt before sending it to the LLM. This reduces hallucinations and
> produces accurate, context-aware answers.**

------------------------------------------------------------------------

# 5 Most Important Interview Points

-   Chunk documents with overlap to preserve context.
-   Use the same embedding model for both documents and queries.
-   Store embeddings in a Vector Database like ChromaDB or FAISS.
-   Retrieve relevant chunks using cosine similarity before calling the
    LLM.
-   Vector databases search by meaning, while SQL searches exact
    keywords.

------------------------------------------------------------------------

# One-Line Memory Formula

> **Ingest → Chunk → Embed → Store → Query → Retrieve → Augment Prompt →
> LLM → Answer**
