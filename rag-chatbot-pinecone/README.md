# RAG AI Chatbot Pincone

![Alt text](https://github.com/lymxfti/ai-automation-portfolio/blob/main/rag-chatbot-pinecone/n8n-workflow-screenshot.png)

## Overview

This project is a Retrieval-Augmented Generation (RAG) chatbot designed to answer user questions based on a curated set of internal documents. It uses Pinecone as a vector store, OpenAI embeddings for semantic search, and n8n for orchestration. The chatbot was built to serve as an intelligent, document-grounded assistant that can be queried via webhook and respond with contextually accurate, non-hallucinated answers.

## Features

- **Webhook-based chatbot**: Easily integrates into frontend interface.
- **Real-time Google Drive ingestion**: Watches a specific folder and updates the vector database as soon as files are modified.
- **Chunking & Embedding**: Documents are chunked using the Recursive Text Splitter and vectorized using OpenAI embeddings.
- **Namespace isolation**: Each document is stored in its own Pinecone namespace.
- **Multi-tool AI Agent**: Each namespace is mapped to a dedicated tool with rules.
- **Conversational memory**: Maintains short-term memory using n8n's Simple Memory feature.

## Stack & Tools

- n8n (workflow orchestration)
- Google Drive (document source)
- Pinecone (vector database)
- OpenAI (embeddings)
- Custom AI Agent (LLM-augmented response)

## Architecture

1. **Document Ingestion**
   - A Google Drive file-watcher node monitors for changes in the document folder.
   - Each updated or added document is downloaded individually.
   - Each document is chunked (size: `1000`, overlap: `0`) to ensure context fidelity.
   - Chunked text is embedded and stored in Pinecone under a namespace matching the filename.

2. **Chatbot Interaction**
   - A webhook receives user messages.
   - The AI Agent uses tools mapped to each document/namespace.
   - The system prompt enforces tone, behavior, and fallback escalation.
   - Retrieved documents are used as grounding context for LLM-generated replies.

## Document Types

- Privacy & Cookie Policy
- Terms of Service
- ESG Policy
- FAQ
- Data Retention Policy

These documents were selected to simulate a typical compliance-driven internal knowledge base.

## Demo / How it Works

A sanitized workflow (`rag-chatbot-pinecone-sanitized.json`) is included. All API keys, IDs, prompts, and sensitive logic have been removed.

## Outcomes

- Provides document-grounded, hallucination-free responses
- Modular architecture allows adding/removing tools with minimal config
- Fully webhook-compatible and scalable across domains or document types
- Automatically syncs updated documents to Pinecone in near real-time

## Limitations & Next Steps

- Current setup overwrites full namespaces on each sync
- Future versions should implement diffing or document version control
- No hybrid search (keyword + semantic)
- Could benefit from contextual caching or embeddings hash validation
- A more robust RAG workflow to be added soon

Laith Mufti  
[LinkedIn](https://www.linkedin.com/in/laith-mufti) | lysmufti@gmail.com
