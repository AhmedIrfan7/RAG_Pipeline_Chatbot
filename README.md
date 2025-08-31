# RAG_Pipeline_Chatbot using N8N
📌 My Workflow – Google Drive → Pinecone → AI Agent

This workflow automates the process of ingesting FAQ or document files from Google Drive, transforming them into embeddings using OpenAI, storing them in Pinecone, and making them queryable through an AI Agent connected to a chat interface.

🚀 Workflow Overview
1. Google Drive Trigger

Watches a specific Google Drive folder (FAQ_n8n).

Triggers the workflow whenever a new file is created.

2. Download File

Downloads the newly created file from Google Drive.

Passes the file content forward for processing.

3. Document Processing

Recursive Character Text Splitter: Splits large text files into smaller, manageable chunks.

Default Data Loader: Converts binary file data into text format for embeddings.

4. OpenAI Embeddings

Generates embeddings for each text chunk using OpenAI Embeddings API.

Ensures text is in a machine-readable format for semantic search.

5. Pinecone Vector Store

Inserts the embeddings into Pinecone Index (testn8n1).

Stores them in the FAQ namespace for organized retrieval.

6. Chat Integration

Chat Trigger: Listens for incoming chat messages.

AI Agent: Acts as the reasoning engine, powered by OpenAI (via OpenRouter).

Pinecone Vector Store Tool: Enables the AI Agent to search the stored FAQ embeddings.

7. AI Response

The agent retrieves relevant document chunks from Pinecone.

Responds to user queries in natural language using the OpenRouter Chat Model (gpt-4o-mini).

🛠️ Tech Stack

n8n – Workflow automation engine.

Google Drive API – File trigger + download.

OpenAI API – Text embeddings.

Pinecone – Vector database for semantic search.

OpenRouter – Chat model integration (gpt-4o-mini).
