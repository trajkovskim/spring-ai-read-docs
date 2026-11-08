# Spring AI – Read Documents

A document-based AI chat application built with **Spring AI**, **Ollama**, and **Qdrant**, using Retrieval-Augmented Generation (RAG) to provide context-aware answers based on ingested documents and web content.

The application combines PDF ingestion and web crawling with vector embeddings and semantic search, allowing users to ask questions and retrieve relevant information from their own knowledge base.

## Features

- **PDF Ingestion** – Extract and process text from PDF documents.
- **Web Crawling** – Collect content from web pages to build a searchable knowledge base.
- **Document Processing** – Split extracted content into smaller chunks for efficient retrieval.
- **Vector Embeddings** – Generate numerical representations of document content using embedding models.
- **Vector Storage** – Store document embeddings and associated content in Qdrant.
- **Semantic Search** – Retrieve relevant information based on the meaning of user queries.
- **Context-Aware Q&A** – Generate responses using retrieved document content as context.
- **Local AI Integration** – Use Ollama to run language and embedding models locally.

## How It Works

The application uses Retrieval-Augmented Generation (RAG) to answer questions based on information collected from external sources. Documents are ingested from PDF files and web pages through web crawling. Their content is extracted, split into smaller chunks, and converted into vector embeddings using an embedding model.

The generated embeddings and associated document content are stored in Qdrant, enabling semantic search across the ingested data. When a user submits a question, the application converts it into an embedding and searches the vector store for the most relevant document chunks. The retrieved content is then provided as context to the language model through Spring AI and Ollama, which generates a response based on the available information.

## Technology Stack

| Category | Technologies |
|---|---|
| Language | Java |
| Backend Framework | Spring Boot |
| AI Integration | Spring AI |
| Language Models | Ollama |
| Embedding Models | Ollama |
| Vector Database | Qdrant |
| Document Sources | PDF, Web Pages |
| AI Architecture | Retrieval-Augmented Generation (RAG) |

## Getting Started

### Prerequisites

Make sure you have the following installed:

- Java
- Maven
- Ollama
- Docker

### Clone the Repository

```bash
git clone https://github.com/trajkovskim/spring-ai-read-docs.git
cd spring-ai-read-docs
```

### Start Qdrant

Run Qdrant locally using Docker:

```bash
docker run -p 6333:6333 -p 6334:6334 qdrant/qdrant
```

The Qdrant dashboard is available at:

```text
http://localhost:6333/dashboard
```

### Configure Ollama

Install Ollama and download the language and embedding models used by the application.

```bash
ollama pull <chat-model>
ollama pull <embedding-model>
```

Make sure the Ollama service is running.

### Configure the Application

Configure the required connection properties for Ollama and Qdrant in the application configuration.

Ensure that the configured model names, Qdrant connection details, and collection settings match your local environment.

### Run the Application

Using the Maven wrapper:

```bash
./mvnw spring-boot:run
```

Alternatively, import the project into your preferred IDE and run the Spring Boot application.

## Concepts Explored

- **Retrieval-Augmented Generation (RAG):** Combining information retrieval with language model generation to produce context-aware responses.
- **Vector Embeddings:** Representing textual content as numerical vectors for semantic comparison.
- **Semantic Search:** Finding relevant information based on meaning rather than exact keyword matches.
- **Vector Databases:** Storing and retrieving high-dimensional embeddings for similarity search.
- **Local LLM Integration:** Integrating locally hosted language and embedding models through Ollama.

## Future Improvements

- Conversational memory for multi-turn interactions.
- Source references and document citations in generated answers.
- Improved document management and re-ingestion.
- Streaming AI responses.
- Metadata-based filtering and retrieval optimization.

## Author

**Martin Trajkovski**

- [GitHub](https://github.com/trajkovskim)
- [LinkedIn](https://www.linkedin.com/in/martin-trajkovski/)
