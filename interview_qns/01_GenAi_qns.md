# EY Python / Gen AI Interview — Practice Questions

## Introduction & Project Overview
1. Introduce yourself and explain your projects step by step with use cases.
2. Please introduce yourself with your technical background.
3. Describe the recent project you worked on, the problems you solved, the tech stack used, deployment details, and project status.
4. Which UI components did you use in the project?
5. Which services have you used in the project?

## Azure Services & Deployment
6. What Azure services did you use in your project?
7. Which Azure infrastructure services like App Services, VMs, or others did you use in your project?
8. Which Azure services like App Services and Virtual Machines (VMs) did you use for deploying your application?
9. Which Azure services have you used?
10. What is the difference between Azure App Services and Virtual Machines?
11. Suppose you have deployed your application on Azure and are using Azure AI services and other related services. How do you manage or utilize these services?
12. How do you secure your AI application deployed on Azure using Azure AI services?
13. How do you secure both Azure services and the application itself to prevent data leaks and ensure data security?

## RAG / Ingestion Pipeline
14. Can you explain the ingestion pipeline you created, how it works, and how data is automatically pulled in?
15. How do you handle PDF documents in your ingestion pipeline?
16. How do you process PDFs containing images, tables, and text for chunking, and which libraries do you use for PDF extraction?
17. How do you handle and reduce hallucinations or wrong answers from a RAG pipeline querying a vector database?
18. What is reranking in the context of retrieval pipelines, and when do you apply reranking?
19. How many types of chunking strategies are there?
20. Is the Retrieval-Augmented Generation (RAG) pipeline currently deployed in production or is it just a proof of concept (POC)?

## LangChain / LangGraph & Agent Workflows
21. What is the difference between LangChain and LangGraph?
22. What are start nodes, end nodes, and conditionals in the context of agent workflows or graph-based AI pipelines?
23. What is a conditional in the context of agent workflows or graph-based AI pipelines?
24. Have you used start nodes, end nodes, and conditionals in your projects?
25. Why do you implement a wrapper around a chain when solving a problem?
26. If you have a simple LangChain flow, why would you use LangGraph instead?

## Backend / FastAPI & Async Processing
27. What is the key difference between Django and FastAPI, and how do you decide which to use?
28. What is dependency injection in FastAPI?
29. Have you heard about Celery and Redis?
30. What is the use of Celery?
31. How do you implement background tasks in FastAPI?

## Performance & Production
32. How can you check and reduce latency or timeout issues when moving an application from server to production, especially when user requests to a chatbot increase latency from milliseconds to seconds?

---
*Total: 32 questions*

# UST Global — AI Python / Gen AI Interview — Practice Questions
*Source: UST_AI_Python__Gen_AI_21-07-2026 (Exported 7/21/2026)*

## Introduction
1. Introduce yourself and explain your projects step by step with use cases.
2. Briefly share your background and what brought you to this role.

## Agent Tool-Calling, RAG Decisioning & Ambiguity Handling
3. How did you handle authentication secrets and safe tool execution when connecting LLM or agent workflows to procurement REST APIs in production?
4. How do you decide when an agent should call tools versus retrieve context from a vector store (RAG) in a multi-step procurement workflow, and how do you prevent wrong actions on ambiguous input?
5. How do you decide whether a procurement agent should use retrieval from documents (RAG) versus call a tool to take an action, and what checks ensure the agent asks clarifying questions on unclear requests?

## CI/CD, Deployment & Instrumentation
6. How would you structure the deployment flow for a live system with GitLab CI/CD pipelines across test and production environments, and what instrumentation would you prioritize to catch regressions before impacting users?
7. How to design rollout and rollback for an LLM-powered service deployed via GitLab CI/CD to catch latency and cost regressions early without interrupting users?

## Evaluation, Observability & Debugging Under Load
8. How would you design evaluation and observability to diagnose whether inconsistent agent answers under load are due to retrieval quality, prompt behavior, or the downstream model, and what would you change first if token cost and latency are rising?
9. How would you use logs or metrics to separate issues between retrieval, prompt, and model when documents are correct but answers weaken under load, and what would you optimize first if cost and latency rise?

## Orchestration Redesign for Reliability & Cost
10. How would you redesign a generative workflow that is correct in testing but makes extra tool calls in production, to keep it reliable, reduce model calls, and maintain answer quality under strict latency and cost caps?
11. What concrete changes would you make to the orchestration so the agent decides earlier, calls tools less often, and still keeps answers accurate when deployment causes extra tool calls?
12. What specific changes would you make in the orchestration logic — such as confidence thresholds, early routing, caching, or asking clarifying questions first — so the agent decides sooner, avoids repeated tool calls, and still returns the right answer?

## Authentication, Authorization & Multi-Tenant Access
13. How would you design the authentication and authorization flow for an AI backend service with multiple business teams having different permissions and data boundaries, and how would you log or trace to isolate access failures in production?
14. How would you set up login and permission flow for multiple teams so each only sees its own data, and what exact logs or traces would you check first to identify if a production access failure is from the identity provider, API gateway, or downstream service?
15. Walk through the login flow and enforcement for a multi-team system ensuring data isolation, and identify the first logs or traces to check for production access issues from the identity provider, API gateway, or downstream service.

## Tool/Connector Validation (MCP) & Failure Handling
16. How would you design validation and fallback for an LLM agent integrating with enterprise tools via a connector pattern like MCP, when one tool returns stale or malformed data in production, to prevent the agent from taking bad actions?
17. What initial checks would you perform to validate stale or bad data returned by a connector like MCP, and what should the agent do if validation fails to avoid wrong actions?

## Hallucination Diagnosis After Prompt/Model Changes
18. How to quickly evaluate and adapt a production AI service showing higher hallucination rates after prompt or model changes, while keeping the service stable?
19. How to quickly evaluate and adapt a production AI service showing higher hallucination rates after a prompt or model change, while keeping the service stable? (follow-up)
20. What is the first step to stabilize a service when hallucinations increase after a prompt or model change, and how to quickly identify if the problem is with the prompt, retrieval layer, or model?

## Team & Stakeholder Management
21. How to keep the team aligned and engaged when an engineer and a product stakeholder sharply disagree on scope under tight delivery pressure?

## Project Deep-Dive (RAG / Agentic Workflow)
22. Describe an end-to-end RAG (Retrieval-Augmented Generation) or agentic workflow you built, including data sources, retrieval handling, quality and tool-calling failure management, and why you are suited to production-grade enterprise integration.
23. Walk through a real RAG or agent workflow from your project, specifying the exact data source, a challenge with retrieval quality or tool failures, and how you handled it in production.
24. Walk me through one specific workflow from your procurement contract project, naming the exact data source, one retrieval or tool failure you encountered in production, and the concrete fix you implemented.

## Closing
25. Is there one project, achievement, or skill you are especially proud of that we haven't discussed yet?

---
*Total: 25 questions*