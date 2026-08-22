# Python / Gen AI Interview — Practice Questions
*Source: Interview transcript, 30-07-2026*

## Introduction
1. Introduce yourself and explain your projects.

## Role, Architecture & Implementation (Project 1)
2. What exactly was your role in this project? Did you work on both the front end and back end?
3. Walk me through the architecture and implementation patterns you used for this project.
4. If I looked at your code and implementation, what would I actually see? What are you doing at each step, and for what purpose?
5. Can you walk me through the architecture between the UI and the API? Is there a BFF (Backend-for-Frontend) or is it just one big application? How does everything fit together?
6. Is the FastAPI backend running as a separate application/container, and how does the React/Next.js frontend interact with it?

## API Security & JWT
7. How do you secure API calls between a React/Next.js frontend and a FastAPI backend, and prevent privilege escalation or unauthorized access?
8. In your application, how do you make sure that an API call is actually coming from your UI and not from an attacker or an unauthorized source?
9. How do you prevent someone from manually changing or forging the JWT token to impersonate a user or escalate privileges?
10. How do you make sure a JWT token hasn't been manipulated, for example, if someone tries to add roles or change claims and then uses Postman to call the API?

## PSA Timesheet / HR Assistant Project
11. Walk me through your AI-powered HR assistant in the PSA timesheet and workforce management system. How did it work?
12. Was the architecture for the PSA timesheet and HR assistant project the same as your previous project? What was your role, and how was it different?
13. Was your backend connecting directly to the database, or was it some kind of service? How did you handle changes and updates?
14. Where does the ORM fit into your architecture? Is the UI connecting directly to the database, or is there a backend in between?
15. Was your backend just one big FastAPI service, or did you use microservices?

## RAG & Vector Database Implementation
16. What are you exposing with RAG in this project? What is the RAG implementation actually used for?
17. Which vector database did you use for storing embeddings and retrieval in your RAG pipeline?
18. Where was your FAISS vector database hosted? Was it self-hosted, cloud, or managed?
19. What is the actual vector search or vector database capability you used? How does it compare to Azure's managed vector search?
20. How did you generate embeddings? Did you call out to an LLM, or did FAISS handle embedding creation automatically?
21. How did you generate embeddings for each document? Did you use an LLM, or does FAISS handle embedding creation? (follow-up)
22. What challenges did you face getting documents in and making them searchable with embeddings and FAISS?

## Closing
23. Do you have any questions for us?

---
*Total: 23 questions*

# Python / Gen AI Interview — Practice Questions
*Source: Interview transcript, 31-07-2026 (session 1)*

## Introduction
1. Introduce yourself and explain your projects step by step with use cases.

## Experience Self-Rating
2. How many years of experience do you have?
3. How much experience do you have in Python?
4. How would you rate yourself in Python on a scale of 5?
5. How would you rate yourself on databases on a scale of 5?
6. Which databases have you worked with?
7. Which SQL databases have you worked with?
8. How much do you rate yourself on ORMs?
9. Which ORM have you used?
10. How many years of experience do you have with SQLAlchemy?
11. For migration management, what have you used in your project?
12. Do you have experience with authentication and authorization as well?
13. Which cloud have you used?
14. In which cloud are you more comfortable?
15. What are the AWS services that you have used?
16. Do you have experience in software architecture, like design patterns and different types of software patterns?
17. How would you rate yourself on DevOps tasks?

## Project Overview
18. Can you briefly and simply explain your most recent project, focusing just on the business problem it solves (no technical details)?
19. In a concise way, what tools and technologies did you use in your project, and what was your role?
20. Just list out the tools and technologies you used, and your role in the project.
21. What was the infrastructure? Where was everything deployed?
22. Which CI/CD pipeline are you using?
23. Was the project following microservices architecture or monolith, or what kind of architecture was it?
24. Did you also use Kubernetes for container orchestration?
25. Which service did you use for container orchestration?

## Python Fundamentals — List vs Tuple, Hashability
26. What is the difference between a list and a tuple in Python?
27. What else is different between a list and a tuple in Python?
28. What does it mean that tuples can be used as keys in a dictionary?
29. Which Python objects are hashable and which are not hashable?
30. Are tuples always hashable, or can they sometimes be unhashable?
31. Is there a way a tuple can be unhashable? Can you give an example?

## Live Coding — Custom Exceptions
32. Have you ever created any custom exception before?
33. Create a custom exception in Python for age-based voting eligibility, with a function that raises the exception if age is less than 18.
34. Write a simple function that checks if someone is allowed to vote based on age, and raises an exception if not.
35. Is the code correctly set up to raise and display an exception when the age is under 18?
36. Show a custom exception used instead of the built-in Exception in your code.

## Concurrency — asyncio, Multithreading, Multiprocessing
37. Have you used asyncio before?
38. What is the difference between asyncio, multiprocessing, and multithreading in Python?
39. Which is faster: asyncio, multithreading, or multiprocessing?
40. Have you ever used ThreadPoolExecutor before?
41. Without ThreadPoolExecutor, can we still safely run tasks in parallel?
42. Why is it recommended to use a thread pool?

## Live Coding — Decorators & Key Case Conversion
43. Have you ever worked with decorators before?
44. What is a decorator?
45. Can you explain what a decorator is in a more clear manner?
46. How would you convert all the keys in the API response from snake_case to camelCase, but only for the keys (not the values), and leave keys already in camelCase unchanged?
47. How would you write a reusable Python decorator to convert all dictionary keys in an API response from snake_case to camelCase, handling nested structures, and apply it to multiple API functions?
48. The API response keys need to be converted from camelCase to snake_case to match the expected output format.
49. You are not allowed to change the dictionary keys directly; you need to convert the API response keys from camelCase to snake_case dynamically, without modifying the original dictionary.
50. What's your overall plan to solve the camelCase to snake_case conversion for API response keys?
51. How are you planning to solve the camelCase to snake_case conversion, including nested keys?
52. What if you're not allowed to use regular expressions?
53. Implement camelCase to snake_case conversion using regular expressions.

## Testing — pytest, Fixtures, conftest.py
54. Which frameworks have you used for unit testing?
55. What are fixtures?
56. Are fixtures just for databases?
57. What are fixtures in simple terms?
58. Have you heard of conftest.py in pytest?
59. How do we use conftest.py in pytest?
60. How do we run tests that use conftest.py in pytest?
61. How do we use a fixture from conftest.py in a test function?

## System Design — Transaction API
62. How would you design a transaction API that deducts balance from Account A, adds it to Account B, updates both balances, sends notifications to both, and is fault tolerant, idempotent, and scalable?
63. The balance for each account exists in the database. How would you design the transaction API?
64. The notification step uses a third-party API and is an expensive operation. How would you handle notifications in your transaction API design?
65. Can you write the pseudocode for the transaction API, explaining each step and handling exceptions, idempotency, and notifications?
66. Which queue would you use for asynchronous notifications in the transaction system?
67. What role will the queue (like Redis or RabbitMQ) play in this notification system?
68. Where does the notification system get triggered in the transaction flow?
69. What would you use as a worker for processing messages from Redis in this notification system?
70. Where would you put the worker in the system architecture?
71. What status code or message would you have as a response for the notification system?

## Production Incident — 500 Errors & DB Transactions
72. How would you handle a situation where all API requests in production suddenly start returning 500 errors?
73. If there were no recent deployments or config changes, but suddenly all API requests start returning 500 errors, how would you proceed?
74. What potential database issues could cause all API requests to return 500 errors?
75. What is the issue with calling an API in the middle of a database transaction?
76. Why is it a problem if the transaction takes extra time because of an external API call, since all DB operations take some time?
77. What is the exact issue caused on the database side when calling an external API inside a transaction?
78. How do you mitigate the issue of holding database locks for too long due to external API calls inside a transaction?
79. Have you heard of connection pooling?

---
*Total: 79 questions*