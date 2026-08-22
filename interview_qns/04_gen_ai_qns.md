# Python / Gen AI Interview — Practice Questions
*Source: Python / Gen AI interview transcript, 31-07-2026*

## Introduction & Project Overview
1. Introduce yourself and explain your projects.
2. What was the problem statement for your procurement management system project?
3. Which cloud platform did you use to deploy this project?
4. What was the main architectural decision you made for this project?

## Enterprise Chatbot — Scope & Design Decisions
5. What was the file size limit for documents users could chat with in your procurement document chatbot?
6. Did users have to upload documents, or was there a centralized repository for the procurement chatbot?
7. What was the unique problem you solved with your procurement document chatbot, compared to just using Copilot or ChatGPT for document Q&A?
8. In your enterprise chatbot, users still had to upload documents to get answers, not search across all enterprise documents — was that the main problem statement?
9. What was the client's requirement — should users interact with already-stored enterprise documents, or upload their own documents to chat with?
10. Did you provide citations and grounding in your enterprise chatbot?

## Authentication, Access & Blob Storage
11. How did you manage authentication and access for the enterprise chatbot?
12. Who has access to the Azure Blob Storage — every user, or just a service account?
13. How do you let users open a PDF from a citation link if only the backend has access to Blob Storage? How do you generate and provide a signed URL to the user?

## Frontend vs. Backend Experience
14. Is the AI integration experience only on the frontend, or does it include backend as well?
15. Does your experience mean you only have control over the frontend, or do you also handle backend responsibilities?

## RAG Implementation, Chunking & Vector Search
16. What failed during your RAG implementation with PgVector, and how did you resolve it?
17. What issues did you face with chunk size in RAG using PgVector, and how did you resolve them?
18. What chunk size should you use when creating vectors from a PDF for RAG?
19. What are the different techniques of chunking?
20. Which chunking technique is best for creating vectors from a PDF?
21. For Q&A over a PDF, which chunking technique should you use?
22. How do you decide what type of chunking to use for a PDF when structure alone isn't enough?
23. What does FAISS mean in the context of vectors?
24. What's the difference between exact search and similarity search in vector databases like FAISS?
25. What's the difference between nearest neighbor (similarity) search and exact search in FAISS or vector databases?
26. In similarity search, what are the main distance metrics used, and how do you choose between them?

## Cost, Monitoring & Scalability
27. How do you optimize the cost for a high-volume GenAI application?
28. How do you handle monitoring and logging for tracing LLM latency and tokenization?
29. How many users are using your application, and how do you design backend scalability for sudden spikes in usage?

## Backend & Databases
30. Which backend framework did you use?
31. Have you worked on SQL or NoSQL databases?
32. If you want to create database tables, how do you proceed using FastAPI?

## Alembic Migrations
33. How do you handle migrations in FastAPI models?
34. If you add a column to a table and need to revert that change, how do you proceed?
35. If you add some data to the table, and then roll back the migration, will the data also be rolled back?
36. If we add new columns and data, then realize there's a problem and need to roll back, how do we handle it?
37. Will Alembic allow you to downgrade (drop columns) if there is still data in those columns?
38. What happens if you have already dropped the column?
39. If there are already records in a column and you drop that column in a new release, will Alembic allow you to drop it?
40. In production, if we run an Alembic migration that adds two columns and drops one existing column (with data), will Alembic allow us to do this?
41. In production, if the column we're dropping already has data, will Alembic allow us to drop it?
42. What should be your steps to roll back after dropping a column with data using Alembic?
43. How do you resolve Alembic migration conflicts when two developers add columns to the same table on different branches?

## Python Fundamentals — OOP & Concurrency
44. Do you know classes and objects in Python?
45. What is a class in Python?
46. What is the difference between *args and **kwargs in Python, and why do we use them?
47. What are Dunder methods in Python classes?
48. What is self in the __init__ method (and in Python classes)?
49. What is the difference between multiprocessing and multithreading in Python?
50. If you need to call 500 websites, should you use multithreading or multiprocessing?

## Git
51. How do you update your feature branch with the latest changes from the main branch in Git?
52. What's the difference between git pull (merge) and git pull --rebase?

## FastAPI, Flask, ASGI/WSGI & Routing
53. How does FastAPI resolve the URL pattern?
54. How does FastAPI know which function to call for a given route or URL?
55. Is FastAPI asynchronous or synchronous?
56. Have you heard of Flask?
57. Is Flask asynchronous?
58. Are both Flask and FastAPI used for API development only?
59. What is the difference between ASGI and WSGI?
60. Can Python handle requests concurrently with ASGI?

## Concurrency & Scaling Under Resource Constraints
61. How should you configure FastAPI to handle 100 requests per second on a 1 CPU, 1 GB machine?
62. How would you handle 100 requests per second on a 1 CPU, 1 GB container, for a FastAPI microservice that fetches and processes data before returning a response?
63. How do you determine the worker limit for your FastAPI app in production, and what should you do if you need to handle more requests than your current setup allows?
64. If each request takes 1 second, and you need to serve 100 requests per second on a 1 CPU, 1 GB container, how do you achieve true concurrency for all 100 requests at the same time?
65. How do you handle 100 concurrent requests per second when each request takes 1 second, but your main container is limited to 1 CPU and 1 GB RAM?
66. What is the difference between Gunicorn and Unicorn?
67. How do you decide the number of Gunicorn workers?

---
*Total: 67 questions*

# Python / Gen AI Interview — Practice Questions
*Source: Python / Gen AI interview transcript, 16-07-2026 (session 2)*

## Introduction & Background
1. Introduce yourself and explain your projects step by step with use cases.
2. What is your overall experience?
3. In which companies have you worked?
4. Can you explain your role in the project and what you have done, step by step, end to end?

## Project Objective & Problem Statement
5. What is the objective of your project?
6. Explain the objective, methodology, process involved in your project, and your role in that flow.
7. What is the problem your project is addressing?
8. Explain with an example the actual problem your project is trying to resolve.

## Log Processing & Document Extraction
9. How are you taking the logs, processing them in your application, what challenges did you face, and how did you address them?
10. How do you handle device logs in multiple formats (text, screenshots, PDFs, JPEGs), and how do you extract text from these varied formats for processing?
11. How do you process device logs and related information that come in multiple formats such as screenshots, PDFs, and images?
12. How do you handle extracting and processing tables from PDFs or images during text extraction?
13. How do you handle tables during document extraction?

## OCR — Mechanism, Accuracy & PII Handling
14. How do you handle extracting tables from PDFs and images, especially when using OCR services?
15. How does the OCR mechanism work internally, and how do you ensure that the extracted text is accurate and appropriate?
16. Is OCR a tool or a model, and how does it function?
17. How do you verify that the text extracted by OCR is accurate?
18. What extra precautions do you take when extracting sensitive PII data like phone numbers using OCR?
19. Are you adopting any other mechanisms to handle mobile numbers (PII) extracted via OCR?
20. How do you handle any personal information extracted via OCR?

## Embeddings & Storage Strategy
21. After extracting text and required details via OCR, how do you store this large amount of information? What storage strategy do you apply?
22. What model have you used to convert text to embeddings?
23. How do you handle long text when converting to embeddings? Do you use a chunking strategy or pass the entire long text directly to the model before storing embeddings?
24. Did you perform the embedding process in the cloud, locally, or in a low-level environment? How did you manage this?
25. How did you use the embedding process — was it via a cloud endpoint or some other method?
26. How did you use the embedding process — was it via a cloud endpoint, local setup, or something else? How exactly did you convert text to embeddings?

## Cloud Storage & Production Workflow
27. Where do you store local data such as logs? Do you use blob storage or some other storage solution?
28. Can you explain in detail the process of storing local data such as logs, and how you use cloud services or blob storage in that workflow?
29. Which cloud blob storage service did you use for storing logs and data?
30. How is the solution productionized to handle multiple logs regularly — covering log ingestion, storage, chunking, embedding conversion, and the overall cloud workflow?

## Python & Framework Skills
31. How good are your Python skills?
32. How good are your Python skills, and how would you rate yourself out of ten?
33. What is your experience with FastAPI and Flask frameworks?

## Idempotency
34. Do you know what idempotency is?
35. Can you explain idempotency?
36. Explain idempotency with examples of idempotent and non-idempotent calls.

## Live Coding — RAG Pseudocode & Retrieval
37. Write pseudocode for a Retrieval-Augmented Generation (RAG) application.
38. Explain the Retrieval-Augmented Generation (RAG) pipeline and how it retrieves knowledge.
39. What is the retrieval mechanism in the RAG pipeline?
40. What is the retrieval strategy used in the RAG pipeline?
41. What is the threshold used in the retrieval strategy?
42. How can we improve the current RAG retrieval implementation shown on the screen?
43. How do you establish relationships between logs when processing large volumes of data in a RAG pipeline?
44. When processing vast logs containing extensive information about a scenario, do you compare the complete log with the query?
45. How do you handle comparing a query against vast logs containing extensive information — do you compare the complete log or use a different approach?
46. Can you quickly write a function to perform selective log retrieval with metadata filtering and chunking for similarity search?

## Live Coding — Flask API
47. Write a simple Flask API pseudocode that accepts two input values and performs an operation (e.g., addition).
48. Write a simple Python function exposed via a Flask API that takes two variables, adds them, and returns the result.
49. Create a Flask app with a POST endpoint that accepts two input values, performs addition, and returns the result when the endpoint is hit.
50. Provide pseudocode for a Flask API endpoint that accepts two values via POST, adds them, and returns the result.
51. Can you write pseudo code for a Flask app that accepts two values via POST, adds them, and returns the result?
52. Can you write the actual Python code for a Flask app that accepts two values via POST, adds them, and returns the result?

## Deployment & Containerization
53. How do you host and run a Flask application, and how do you containerize it?
54. How do you host and run the Flask app and how do you containerize it for deployment?
55. Can you write the Dockerfile code to containerize the Flask app?

---
*Total: 55 questions*