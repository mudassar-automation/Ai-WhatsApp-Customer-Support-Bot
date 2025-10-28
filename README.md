# 💬 AI-Powered WhatsApp Chatbot (Text, Voice, Images, PDF + RAG)

---

## 👥 Who Is This For?  

This template is designed for **internal support teams, product specialists, and knowledge managers** in technology companies who want to:  
- Automate the ingestion of product documentation  
- Enable **AI-driven, retrieval-augmented question answering (RAG)**  
- Deliver accurate, context-aware support via **WhatsApp messaging**  

It’s ideal for organizations that need 24/7 automated assistance without compromising accuracy or brand tone.

---

## 💡 What Problem Does This Workflow Solve?  

Support teams often spend hours manually searching through documentation, resulting in **delayed or inconsistent responses**.  

This solution automates the process by:  
- Importing, chunking, and embedding your internal documents  
- Creating a searchable vector database for instant knowledge retrieval  
- Using **RAG (Retrieval-Augmented Generation)** to deliver **precise, AI-generated answers** through WhatsApp — text, voice, image, or PDF.  

The result: **instant, accurate, and consistent customer support**, directly inside WhatsApp.

---

## ⚙️ What These Workflows Do  

### 🧩 **Workflow 1: Document Ingestion & Indexing**  
- **Trigger:** Manually run to import product documentation from Google Docs.  
- **Splitting:** Automatically divides large documents into smaller chunks for efficient semantic search.  
- **Embedding:** Generates vector embeddings for each chunk using **OpenAI Embeddings API**.  
- **Storage:** Inserts embedded chunks and metadata into **MongoDB Atlas Vector Store** for high-speed similarity search.  

This process converts your internal documentation into a structured, searchable knowledge base.  

---

### 💬 **Workflow 2: AI-Powered Query & Response via WhatsApp**  

- **Input Sources:**  
  - 📝 **Text Messages** — Plain text user queries  
  - 🎙️ **Audio Messages** — Voice notes automatically transcribed into text  
  - 🖼️ **Image Messages** — Screenshots or photos analyzed for contextual responses  
  - 📄 **Document Messages** — PDFs, spreadsheets, or manuals parsed for relevant content  

- **AI Query Handling:**  
  - Converts incoming messages into vector embeddings  
  - Performs **similarity search** on MongoDB Atlas for context retrieval  
  - Uses **OpenAI GPT-4o-mini** with RAG to generate precise, context-aware answers  
  - Maintains **conversation memory** using a memory buffer node for multi-turn context  
  - Routes different message types to dedicated processing nodes to maximize accuracy and relevance  

This workflow ensures smooth, intelligent two-way interaction directly through WhatsApp.

---

## 🛠️ Setup  

### ⚙️ Setting Up Vector Embeddings  
1. **Google Docs Authentication**  
   - Connect your Google account and link the document(s) you want to index.  
   - The workflow automatically extracts text and splits it into search-friendly chunks.  

2. **MongoDB Atlas Connection**  
   - Authenticate MongoDB Atlas and link the target collection for storing embeddings.  
   - Create a **Vector Search Index** in MongoDB (e.g., `data_index`).  
   - Ensure the index name matches your n8n configuration.  
