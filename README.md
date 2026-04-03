# Corporate Memory RAG Bot

A local Retrieval-Augmented Generation (RAG) pipeline built with Docker, Flowise, and the Gemini API to securely query corporate documents with zero AI hallucinations.

### 📌 Project Overview
As businesses integrate LLMs, eliminating "hallucinations" (confident but incorrect answers) is critical. This project demonstrates an enterprise-grade RAG architecture that strictly anchors the AI to verified corporate documents. If the answer isn't in the provided PDF, the bot is engineered to explicitly refuse to answer, ensuring 100% factual reliability.

### 🏗️ Technical Architecture
* **Environment:** Docker
* **Orchestration:** Flowise AI
* **Foundation Model:** Google Gemini 2.5 Pro API (Temperature = 0)
* **Vectorization:** Google Generative AI Embeddings (Semantic Similarity)
* **Database:** In-Memory Vector Store (Top-K = 4)

*(Insert a screenshot of your Flowise canvas here!)*

### 🔒 Prompt Engineering Guardrails
To prevent the model from using general internet knowledge, the following strict System Prompt was applied:
> "You are a strict and highly accurate technical support assistant for this company. You must answer the user's questions strictly using ONLY the context provided to you. If the answer to the user's question is not explicitly stated in the provided text, you must absolutely refuse to guess. Instead, reply exactly with: 'I'm sorry, but that information is not covered in the standard operating procedures I have been trained on.' Do not use your general knowledge to fill in the blanks."

### 🧪 Testing & Results
The architecture was tested against a standard Health & Safety Manual. 
1. **Factual Retrieval:** Successfully retrieved and formatted strict policy details.
2. **Adversarial Testing:** When asked general trivia outside the document's scope (e.g., "What is the capital of France?"), the AI successfully triggered the guardrail and refused to answer. 

*(Insert a screenshot of your successful chat test here!)*
