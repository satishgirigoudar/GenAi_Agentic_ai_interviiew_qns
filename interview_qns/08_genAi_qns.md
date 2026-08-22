# Python / Gen AI Interview — Practice Questions
*Source: Interview transcript, 29-07-2026 (session 2)*

## Introduction & Project Overview
1. Introduce yourself and explain your projects step by step with use cases.
2. Can you explain any of your projects?
3. Can you explain your project?
4. Can you tell me about your last project and the company where you worked?

## LLM Fundamentals
5. What do you understand by LLM (Large Language Model)?
6. What is the difference between traditional machine learning and LLMs (Large Language Models)?
7. Can you explain an end-to-end LLM pipeline?
8. What is the difference between RAG (Retrieval-Augmented Generation) and Agentic AI?

## Vector Databases & Protocols
9. What is FAISS database?
10. What is the difference between a normal database and a vector database?
11. What is the difference between MCP and API?

## Project & Team Context
12. Who was the customer for your last project?
13. Does the product you built have any customers yet?
14. How big was your team on this project?
15. What was your module, and how many people were in your module/team?
16. In the module you worked on, how many team members were there?
17. Are you working alone, or how many people are in your module team?
18. In your 18-member team, what was your module, and how many people were in your module?
19. What were your roles and responsibilities in your module?

## Enterprise Data Handling & Ingestion
20. What kind of enterprise data did you work with in your project?
21. What kind of format did you get the enterprise data in (e.g., troubleshooting documents)?
22. What types of documents do you receive in Word format, and what types in PDF format?
23. How often do you receive the data (e.g., documents, updates)?
24. How frequently do you receive this enterprise data (documents/updates)?
25. What do you do after you receive the documents?
26. How do you get the Word or PDF documents into your system?
27. Once you get the data from cloud storage, what do you do next?
28. How do you process Word and PDF files for use in a RAG model? What is the step-by-step process for uploading and integrating these files into the RAG pipeline?
29. How do you handle corrupted files or files that fail during extraction in your pipeline?

## RAG Vector Database Choice
30. Which database do you use for the RAG model?
31. Why do you use two different vector databases (FAISS and ChromaDB) for RAG? When do you choose one over the other?

## Deep Learning Experience
32. Can you explain your deep learning project experience?
33. In which project did you use deep learning, and what was the scenario or reason for using deep learning?
34. Why do we need to use deep learning instead of just machine learning for this use case?

## Compensation
35. What was the salary that you were getting at your last company?

---
*Total: 35 questions*

# Python / Gen AI Interview — Practice Questions
*Source: Interview transcript, 27-07-2026*

## Introduction & Interview Mechanics
1. Introduce yourself and explain your projects step by step with use cases.
2. Should I use print statements in the middle of my code during interviews to check answers?

## Enterprise Project Overview
3. Which of your projects was the largest-scale, enterprise-level project that was shipped to production?
4. What was the real purpose of building the enterprise AI assistant/document intelligence platform, and what problem did it solve?
5. Walk through the architecture, platform/tool choices, challenges, production issues, user feedback, and new features for your enterprise AI assistant project.

## RAG Architecture & Knowledge Base
6. Was the solution a simple RAG or a hybrid RAG architecture?
7. Was the knowledge base structured or unstructured data?

## Chunking & Embeddings
8. How did you handle the chunking process, and which chunking and embedding models did you use?
9. Which chunking strategy did you try for PDFs (paragraph, fixed size, recursive splitter, etc.), and which one worked best in your pipeline?
10. What chunk size and overlap percentage did you use for chunking?
11. What embedding models did you use for your chunked document pipeline?
12. How did you handle the risk of losing context or splitting related content when using smaller chunk sizes (like paragraph chunking), especially when information was spread across multiple PDFs? What chunking and instructions worked best?

## Prompting & Guardrails
13. What prompting techniques are you aware of?
14. How did you implement guardrails and orchestrate LLMs in your solution?
15. Did you use prompting to keep the LLM within boundaries and prevent it from generating off-topic or "crazy" outputs? How did you achieve this?

## Cloud Deployment
16. On which cloud platform was your solution deployed?
17. What Azure cloud services did you use for your generative AI solution?
18. Did you personally handle deployment, or was there a separate deployment team?
19. What post-deployment challenges did you face, and how did you address them?

## Monitoring & Evaluation
20. How did you monitor the deployed application, and what evaluation metrics did you use?
21. Did you focus on precision, recall, F1 score, or faithfulness for evaluation? How did you handle the trade-off between accuracy and latency, especially for retrieval time?

## Scale & Usage
22. How many users are currently using your application?
23. How would you scale your GenAI application to handle a sudden increase in users and concurrent requests (e.g., from 1000 to 2000 users and 500+ simultaneous requests)?

## Notice Period, Compensation & Company Awareness
24. How long will it take for you to exit from Happiest Minds?
25. What is your present CTC (Cost to Company)?
26. Do you know anything about our organization? Did you get a heads up from [referrer]?

---
*Total: 26 questions*

