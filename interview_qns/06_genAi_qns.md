# GenAI / RAG / Agentic AI — Consolidated Interview Questions
*Compiled from review of multiple interview transcripts (duplicates removed)*

## 1. Introduction & Experience
1. Tell me about yourself.
2. Introduce yourself and discuss your recent projects.
3. Explain your recent project.
4. What are your roles and responsibilities in your project?
5. What was your last project?
6. How many years of experience do you have?
7. How much relevant experience do you have in Generative AI?
8. Is your experience only in Generative AI or also in Data Science/ML?

## 2. Project-Based Questions
9. Explain your project step by step.
10. What business problem does your project solve?
11. Explain the complete RAG workflow used in your project.
12. What kind of documents are you ingesting?
13. Are the documents structured or unstructured?
14. What is the size of the documents?
15. What is the volume of documents?
16. How many documents do you process per hour?
17. How do you handle large document volumes?
18. Is your ingestion event-driven or batch processing?
19. Why did you choose that approach?
20. How do you reduce hallucinations?
21. What vector database did you use?
22. What embedding model did you use?

## 3. RAG & LLM Questions
23. What is RAG?
24. Explain the RAG architecture.
25. What happens after data ingestion?
26. Explain embeddings.
27. Explain vector storage.
28. Explain retrieval.
29. Explain prompt augmentation.
30. Explain LLM response generation.
31. Explain API integration in your RAG application.
32. How do you improve response accuracy?

## 4. Generative AI Concepts (Core)
33. What is Generative AI?
34. Explain your experience in Generative AI.
35. What is the difference between Generative AI and Agentic AI?
36. What is the difference between an AI model and an AI Agent?

## 5. LangChain / AI Framework Questions
37. What is LangChain?
38. What is the difference between LangChain and Microsoft Foundry?
39. Have you used Microsoft Foundry?
40. Have you used Azure?
41. Have you worked with LangGraph?

## 6. Synthetic Data Generation (Scenario-Based)
42. Given a schema with column names, descriptions, and data types, how would you generate a synthetic dataset?
43. How would you generate 100K–200K rows efficiently?
44. How would you design a scalable solution using LangChain/LangGraph to generate a large and diverse synthetic dataset?
45. How would you ensure diversity in generated data?
46. You mentioned generating data in batches — how would you implement parallel batch generation?
47. Will you use the same prompt for every batch?
48. If you have hundreds of batches, will you manually provide variations for each batch?
49. How will you add variations to each batch prompt?
50. When the number of batches increases dynamically (e.g., from 100K to 200K rows), how will you handle prompt variations?
51. Can you use a static way of adding variations when batch sizes change dynamically?
52. How will you add dynamic variations to batch prompts?
53. How will you handle different intents for different batches instead of just using random seeds?
54. Who will provide or manage the intent values for each batch?
55. Who will fill the intent placeholders at runtime?
56. How would you avoid duplicate data across batches?

## 7. Architecture & Scaling
57. How do you process data in parallel?
58. How do you scale your AI pipeline?
59. How do you manage API rate limits?
60. How do you optimize latency?
61. How do you process real-time data?
62. How do you process batch data?

## 8. Cloud & Deployment
63. Have you worked with cloud platforms?
64. How do you deploy your AI application?
65. How do you expose APIs?

## 9. Agents & Tool Calling (Scenario-Based)
66. Have you worked with AI agents, LangChain, or LangGraph?
67. Suppose an agent has two tools — Addition and Multiplication. If asked "What is 2 + 3 × 5?", how will the agent arrive at the final answer?
68. How would you evaluate the performance of such an agent?

## 10. RAG Evaluation (Scenario-Based)
69. Have you worked with RAG?
70. How would you evaluate a RAG system?
71. What KPIs would you use to evaluate the retrieval component of a RAG system?
72. Can you explain Precision with a retrieval example (not just the definition)?
73. How do you determine whether the retrieved documents are actually relevant?
74. If you don't have labeled data, how would you evaluate retrieval?
75. What different approaches would you use when labeled data is unavailable?
76. What other approaches would you try besides the ones you already mentioned?

## 11. Chatbot Memory & Caching (Scenario-Based)
77. What kind of caching would you implement in a chatbot?
78. Can you explain your caching approach in more detail?
79. If a chatbot supports multiple conversations, why might it fail to remember something mentioned on Day 1 when asked again on Day 60?
80. How would you solve the long-term memory retention problem in a chatbot?

## 12. Agent Failure Recovery (Scenario-Based)
81. If an AI agent calls an API and the API fails, causing the workflow to stop, how would you design the agent to handle such failures?
82. If the API becomes available again after some time, would you restart the workflow from the beginning or resume from the last successful step?
83. How would you implement such a recovery mechanism?

## 13. Open-Source LLMs & Efficiency
84. Have you worked with open-source LLMs?
85. How would you make an LLM efficient enough to support many concurrent users?

---
*Total: 85 unique questions*