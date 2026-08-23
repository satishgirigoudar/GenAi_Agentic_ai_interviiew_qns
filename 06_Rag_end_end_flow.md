# RAG Architecture (Retrieval-Augmented Generation) 

## Explain Your RAG Architecture End-to-End

**RAG (Retrieval-Augmented Generation)** is an architecture that combines a **Large Language Model (LLM)** with a **Vector Database** to generate accurate, context-aware answers using enterprise data instead of relying only on the model's pre-trained knowledge.

The biggest advantage of RAG is that it retrieves relevant business documents first and then asks the LLM to answer, which reduces hallucinations and keeps responses up to date.

---

## Step 1: Data Ingestion

The workflow starts with **data ingestion**, where we collect documents from multiple enterprise sources such as:

** - PDFs,Word,APIs,Databases(sql),SharePoint,Excel Files**

Before indexing, we perform basic preprocessing such as:
        - Extracting text
        - Removing unwanted characters
        - Handling duplicate content
        - Preserving metadata like document name, page number, and source
This metadata is useful later for filtering and traceability.
---
## Step 2: Document Chunking
After preprocessing, the next step is **Document Chunking**.
We cannot send an entire **200-page document** to an LLM because:
        - It exceeds the context window.
        - It increases token cost.
        - Retrieval becomes less accurate.
Instead, we split the document into smaller chunks so the system retrieves only the relevant portions.

### Chunking Strategy
In our implementation, we used **Recursive Character Text Splitting**, which is one of the most common production strategies in LangChain.

It tries to split the document in this order:
1. Paragraphs
2. Sentences
3. Words
4. Characters
This preserves the natural meaning of the content.

### Configuration
- **Chunk Size:** 500 characters
- **Chunk Overlap:** 100 characters

### Example
Suppose we have a **200-page logistics document**.
Instead of storing one huge document:

            ```text
            Page 1 → Page 200
            ```

We create overlapping chunks like this:

| Chunk   | Character Range |
|---------|-----------------|
| Chunk 1 | 0–500           |
| Chunk 2 | 400–900         |
| Chunk 3 | 800–1300        |
| Chunk 4 | 1200–1700       |

Notice that each new chunk overlaps the previous one by **100 characters**.


---

## Step 3: Embedding Generation

Once the chunks are created, each chunk is converted into a **vector embedding**.

An **embedding model** converts text into high-dimensional numerical vectors that represent semantic meaning rather than exact words.

Example:

| Text           | Meaning |
|----------------|         |
| Truck Capacity | Similar |
| Vehicle Load   | Similar |

Although the wording is different, their vectors are close because the meanings are similar.

### Embedding Model Used

In an AWS environment, I would use:

- **Amazon Titan Embeddings** (AWS Bedrock)

Other popular alternatives include:

- `text-embedding-3-small`
- `text-embedding-3-large`
- BGE Embeddings
- Sentence Transformers

### Why Use the Same Embedding Model?

Both:

- Document chunks
- User queries

must be converted using the **same embedding model**, so they exist in the same vector space and similarity search works correctly.

---

## Step 4: Store in Vector Database

The generated embeddings are stored in a **Vector Database** such as:

- ChromaDB
- FAISS

Along with each embedding, we store metadata like:

- Document name
- Page number
- Source
- Department

This metadata helps filter results and identify where the answer originated.

---

## Step 5: User Query

When a user asks a question, for example:

> "Which truck can carry a 20-ton shipment?"

the system converts the question into an embedding using the **same embedding model** used during indexing.

---

## Step 6: Similarity Search

The vector database performs **semantic similarity search**, typically using **Cosine Similarity**, to compare the query vector with all stored document vectors.

Instead of searching for exact keywords, it retrieves the **Top-K** most relevant chunks based on meaning.

### Example

| User Query  | Retrieved Content |
|-------------|-------------------|
| Truck space | Vehicle capacity |
| Shipment delay | Late delivery |

Even though the wording is different, the semantic meaning is similar.

---

## Step 7: Prompt Augmentation

The retrieved chunks are combined with the user's question to create an **augmented prompt**.

### Example

**Retrieved Context**

- Truck A capacity is **20 tons**
- Route A allows heavy-load vehicles

**User Question**

> Which truck should be assigned for this shipment?

This complete prompt is then sent to the LLM.

---

## Step 8: LLM Response Generation

Finally, the augmented prompt is sent to an LLM through:

- AWS Bedrock
- GPT

Because the model receives relevant business context before generating the answer, it produces:

- More accurate responses
- Context-aware answers
- Fewer hallucinations

---

## Walmart Logistics Project Example

In my **Walmart Logistics Project**, this RAG pipeline helped planners query:

- Shipment details
- Truck capacity
- Warehouse rules
- Route information

using natural language.

Instead of manually searching through large logistics documents, the system retrieved the most relevant document chunks and generated context-aware recommendations, making information retrieval much faster and more accurate.

---

# One-Line Architecture Flow

                ```text
                Ingest Data
                    ↓
                Preprocess
                    ↓
                Recursive Chunking (500 + 100 Overlap)
                    ↓
                Titan Embeddings
                    ↓
                ChromaDB / FAISS
                    ↓
                Query Embedding
                    ↓
                Cosine Similarity Search
                    ↓
                Top-K Retrieval
                    ↓
                Prompt Augmentation
                    ↓
                AWS Bedrock / GPT
                    ↓
                Final Response
                ```

---

# Common Interview Follow-up Questions

## Q1. Why did you choose Recursive Chunking?

**Answer:**

> We chose Recursive Character Text Splitting because it preserves natural boundaries like paragraphs and sentences, reducing context loss while improving retrieval accuracy.

---

## Q2. Why use a 100-character overlap?

**Answer:**

> The overlap ensures that important information split between two chunks remains available in both chunks, improving semantic retrieval.

---

## Q3. Why use the same embedding model for documents and queries?

**Answer:**

> Both documents and queries must exist in the same vector space so Cosine Similarity can correctly identify the most relevant document chunks.

---

## Q4. Why use a Vector Database instead of SQL?

| SQL Database | Vector Database |
|-------------|-----------------|
| Exact keyword search | Semantic search |
| Structured data | Unstructured text |
| `WHERE truck` | Finds "vehicle capacity" |
| Exact matches | Meaning-based matches |

### 05) Why Overlap Matters

Imagine this sentence:

> "The truck capacity for Route A is 20 tons."

Without overlap:

- Chunk 1 → "The truck capacity..."
- Chunk 2 → "...is 20 tons."

The meaning gets broken.

With a **100-character overlap**, both chunks contain enough context, improving retrieval quality.


### Best Interview Answer

> SQL searches exact keywords, while a Vector Database searches based on semantic meaning, allowing it to retrieve relevant information even when the user's wording is different.

---

# 30-Second Revision

> RAG has two phases: **offline indexing** and **online retrieval**. We ingest enterprise documents, preprocess them, split them into **500-character chunks with a 100-character overlap** using Recursive Character Text Splitting, generate embeddings with **Amazon Titan Embeddings**, store them in **ChromaDB or FAISS**, retrieve the **Top-K** relevant chunks using **Cosine Similarity**, augment the prompt with those chunks, and finally generate a context-aware response through **AWS Bedrock or GPT**.