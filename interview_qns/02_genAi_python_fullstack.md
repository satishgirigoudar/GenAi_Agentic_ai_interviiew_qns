# Python / Gen AI Interview — Practice Questions
*Source: Python / Gen AI interview transcript, 18-07-2026*

## Introduction & Project Overview
1. Introduce yourself and explain your projects step by step with use cases.
2. Tell me about yourself, your work experience, and what you are currently doing in your company.
3. Tell me about your recent project, especially the procurement management system, and how you implemented the GenAI assistant.
4. Can you share more about your experience working on AI projects — anything else you've built or contributed to in AI?

## Animation / Production Quality (early warm-up questions)
5. How would you rate this animation in production?
6. How would you reduce animation retention (or attention) in production?

## Hallucination & Guardrails
7. How would you reduce hallucination in production?
8. Do you know about guardrails in GenAI applications?
9. How do you create guardrails in GenAI applications? Do you use any services, or do you build them manually?
10. Did you implement guardrails in your GenAI projects, or not?
11. How would you implement guardrails in a GenAI application, given you haven't used them before?
12. You said that you used guardrails, right?

## Embeddings & Gateways
13. Can you tell about Azure Embedding Model?
14. Which embedding model are you using in your project?
15. Do you know about gateway? (API Gateway or similar concept)
16. What is an LLM gateway? (Explain the concept and practical use)

## Python Fundamentals
17. What are decorators in Python? (Explain in simple terms and with practical context)
18. What type of data do we get from the user input — string, dictionary, tuple, or list?
19. What is the type of the user input in Python?
20. What is the type of the user input in Python? Is it a list, dictionary, integer, or something else?
21. Why is the user input type a string in Python, not a list or dictionary?
22. Why is user input always a string in Python?
23. Do you know about call by reference and call by value?

## RAG Pipeline (Chunking, Retrieval, Metadata)
24. The project you described a few minutes ago — is this a RAG-based system?
25. Can you explain how you used RAG in your project? Specifically, describe the pipeline, chunking strategy, embedding model, and retrieval method.
26. What kind of chunking strategy did you use?
27. Which chunking strategy did you use for your data?
28. Can you explain more about the window (sliding window) chunking strategy?
29. When you created your chunks, how did you decide what metadata to include?
30. How did you decide what metadata to include when chunking documents?
31. How did you decide the metadata for your document chunks?

## Document Processing & OCR
32. What types of documents did you process (e.g., .txt, .pdf, .docx), and how did you handle them?
33. Did you use the same extraction technique for all document types (PDF, DOCX, etc.), or did you adapt your approach based on whether documents had images or just text?
34. Which OCR service or tool did you use for extracting data from images and scanned documents?
35. How do you store and maintain the structure and context of a document (with mixed content like text, images, and tables) after extraction, so that you know where each element appears and how they relate to each other?

## BM25 & Search Strategies
36. Do you know about BM25?
37. Is BM25 mainly used for keyword search?
38. How have you used BM25 in your projects? Do you use BM25 or similarity-based (embedding/vector) search?
39. Do you use BM25, similarity (embedding/vector) search, or semantic search? How do you use them in your projects?
40. Can you explain how BM25 works?

## Live Coding — Math Query Detection & Routing
41. Write pseudocode to take input from the user (with some syntax, but focus on logic over perfect code).
42. Write pseudocode to take user input, check if it's a general or mathematical query, and if mathematical, pass it to an LLM to solve.
43. How would you write pseudocode to check if a user's question is mathematical or general (non-mathematical)?
44. Have you finished writing the code for detecting mathematical queries and routing them?
45. How are you calling the function that detects and routes the query?
46. Can you write the complete Python script with a proper main function to handle the query detection and routing?
47. How would you write the complete Python script so that I can run the file directly and it works as expected?
48. How can I improve the math query detection so it works for both symbols and general English (e.g., "add 5 and 7")?
49. Can you update your code to include keyword-based math detection (like "sum", "divide", etc.) in addition to symbols?
50. How can I enhance the current code to detect math queries using both symbols and English keywords?
51. How would you check if a math symbol (like '+', '-', '*', or '/') exists in a given text string and return true if found?
52. What should we do if we don't find any math symbol in the user's input text?
53. Is the `math_query` function correct, or does it need improvement?
54. Is the current `math_query` function complete, or are there things missing from it?
55. The interviewer is pointing out a logic issue in the loop: in your code, you are looping with `for text in math_text` and then checking `if text.lower() in math_text`, which may not be correct. Is this the right way to check for keywords in the user input?
56. Is the `+` operator in `return "LLM res" + query` used for concatenation, and is this the right way to combine strings in Python?
57. What is the time complexity of the `math_query` function?
58. Why is the time complexity of the math_query function O(n * m)?
59. After getting user input as a string, how do you handle and validate it if the user enters a math query? How do you process it for mathematical operations?

## GenAI Workflow, Orchestration & Deployment
60. Have you worked with the GenAI workflow?
61. Do you know about orchestration, router, or planner components in GenAI workflows (outside of agentic AI)?
62. Have you handled end-to-end production deployments, including AWS and deployment tasks, for your GenAI projects?
63. Have you personally deployed a chatbot so that users can access it, or does someone else handle deployment in your projects?
64. What is more beneficial for storing files — using blob storage (cloud) or your local system memory?

## FastAPI & Pydantic
65. How comfortable are you with FastAPI? Did you write FastAPI code yourself, or did you rely on LLMs like ChatGPT or Claude to generate the code for you?
66. How would you write a simple FastAPI code for user signup that saves the email address and password?
67. If you have two files representing frontend and backend systems, how would you handle the backend part for a signup feature using FastAPI?
68. How would you implement a FastAPI backend for a signup page that collects first name, last name, email, phone, and password, and saves this information when the user clicks "Sign Up"?
69. Why is the Pydantic library used in FastAPI?

---
*Total: 69 questions (includes interviewer follow-up rephrasings on the same core question)*