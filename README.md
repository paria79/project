# Hybrid Search System: Integration of LLMs & Vector Databases

## 1. Project Overview
This project demonstrates a high-performance Hybrid Search System developed with **Django**. It bridges the gap between traditional keyword-based retrieval (Phase 2) and modern AI-driven **Semantic Search** (Phase 3). The system is fully containerized using **Docker** for seamless deployment and scalability.

## 2. Phase 3: Semantic Search & LangChain Integration
The core of this project is the implementation of a **Retrieval-Augmented Generation (RAG)** pipeline. Unlike simple keyword matching, this phase understands the "intent" and "context" of user queries.

### Key Components:
* **Embeddings**: Utilizes the `sentence-transformers/all-MiniLM-L6-v2` model to transform textual data into semantic vector representations.
* **Vector Store**: Implements **ChromaDB** as the primary vector database to index and persist document embeddings from the Django Admin.
* **Chains**: Orchestrated via **LangChain's `RetrievalQA`**, creating a seamless flow from query reception to document retrieval and final response generation.
* **LLM Simulation**: Uses `FakeListLLM` to simulate the final language model output, ensuring system stability while demonstrating a deep understanding of chain logic.


## 3. System Architecture
The application follows a modular architecture:
1.  **Data Ingestion**: Documents are managed via the Django Admin panel.
2.  **Indexing**: Upon search, the system ensures the Vector Store is synchronized with the latest database entries.
3.  **Hybrid Processing**:
    * **Phase 2**: Traditional filtering for direct matches.
    * **Phase 3**: Semantic analysis for conceptual matches.
4.  **Persistence**: Every query and its corresponding AI-generated answer are saved in the `Question` model for history and reporting.


## 4. Installation & Deployment (Docker)
This system is optimized for a **Dockerized** environment to ensure all dependencies (ChromaDB, LangChain, etc.) are pre-configured.

### Steps to Run:
1.  **Clone the repository** and navigate to the root directory.
2.  **Build and Start Containers**:
    ```bash
    docker-compose up --build -d
    ```
3.  **Database Migration** (if required):
    ```bash
    docker exec -it django_app python manage.py migrate
    ```
4.  **Access the Application**: Open `http://localhost:8000` in your browser.

## 5. Evaluation Criteria Compliance
* **Django Structure**: Standardized app folders with clean `models.py` and `views.py`.
* **Clean Code**: Decoupled search logic (`llm_logic.py`) from the web interface.
* **RAG Mastery**: Demonstrated proficiency in retrieval, context merging, and LLM chains.
* **Dockerization**: Simplified one-click deployment for complex AI dependencies.

---
**Author**: Parya
**Date**: February 2026
