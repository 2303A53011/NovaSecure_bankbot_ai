# NovaSecure BankBot FAQ System

## Overview
NovaSecure BankBot is an AI-powered banking assistant built using Streamlit and Ollama. It provides concise, controlled responses strictly limited to banking-related queries using a predefined knowledge filter and a constrained language model.

The system enforces domain restriction, ensuring that only valid banking queries are processed while rejecting unrelated inputs.

---

## Features

- Secure banking-only chatbot  
- Query validation using keyword-based filtering  
- AI-powered responses via Mistral 7B (Ollama)  
- Login system with session handling  
- Chat history management  
- FAQ quick-access system  
- Custom UI styling with CSS  
- Real-time streaming responses  

---

## Project Structure


.
├── ai_chatbot_faq.py
├── bank_knowledge.json
├── README.md


---

## Core Components

### 1. Query Filtering System
The function `is_bank_query()` ensures strict domain control:

- Allows greetings  
- Matches user input against banking keywords  
- Rejects unrelated queries  

Keywords are loaded from:  
- :contentReference[oaicite:0]{index=0}

---

### 2. AI Response Engine
- Uses `ollama.chat()` with model `mistral:7b-instruct`  
- Enforces:
  - Low temperature for deterministic responses  
  - Short responses (max two sentences)  
- Controlled via a strict system prompt  

System prompt behavior:
- Only answers banking queries  
- Rejects non-banking questions  
- Provides concise responses  

Defined in:  
- :contentReference[oaicite:1]{index=1}

---

### 3. Streamlit Interface

#### Login Page
- Simple username and password authentication  
- Session-based login tracking  

#### Chat Dashboard
- Real-time chat interface  
- Message streaming  
- Sidebar with:
  - Chat history  
  - New chat creation  
  - Logout option  
  - Popular FAQ shortcuts  

---

### 4. Chat Session Management

Maintains:
- Multiple chat sessions  
- Chat titles based on first query  
- Timestamped history  
- Ability to load and delete past chats  

---

### 5. FAQ System
Predefined quick-access queries:
- Accounts  
- Loans  
- Cards  
- Security  
- Payments  
- Transfers  
- Mobile banking  
- Support  

Each FAQ generates a concise AI response automatically.

---
