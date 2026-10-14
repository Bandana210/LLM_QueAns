# Q&A — LLM-Powered Question Answering System

An LLM-powered question-answering application that helps users find answers to frequently asked questions about courses, bootcamps, and learning programs. The application uses Retrieval-Augmented Generation (RAG) to retrieve relevant information from an FAQ dataset and generate context-based answers.

## Overview

Finding answers in a large collection of FAQs can be time-consuming. This project explores how Large Language Models (LLMs), text embeddings, and vector similarity search can be combined to build a simple question-answering system.

Users can enter a natural-language question through a Streamlit interface. The application retrieves relevant FAQ content from a locally stored FAISS index and uses Google PaLM through LangChain to generate an answer based on the retrieved context.

## Features

- **Natural-language question answering:** Ask questions in everyday language.
- **Retrieval-Augmented Generation (RAG):** Ground generated answers in retrieved FAQ content.
- **Semantic search:** Use text embeddings to find relevant FAQ documents.
- **Vector storage with FAISS:** Store and search document embeddings locally.
- **Interactive interface:** Ask questions through a Streamlit web application.
- **Reusable knowledge base:** Generate and save a searchable index from the FAQ dataset.

## Tech Stack

| Technology | Purpose |
|---|---|
| Python | Application logic |
| Streamlit | Web interface |
| LangChain | LLM and retrieval pipeline |
| Google PaLM | Language model for answer generation |
| Hugging Face Instructor Embeddings | Text embedding generation |
| FAISS | Vector similarity search |
| Pandas / CSVLoader | FAQ data loading and document preparation |
| python-dotenv | Environment variable management |

## Architecture

The application follows a basic RAG workflow:

1. **Load FAQ data:** Read questions and answers from the CSV dataset.
2. **Generate embeddings:** Convert FAQ documents into vector representations.
3. **Build the vector index:** Store the vectors in FAISS for efficient similarity search.
4. **Retrieve relevant documents:** Find FAQ content relevant to the user's question.
5. **Generate an answer:** Provide the retrieved context and question to the language model.
6. **Display the result:** Show the generated answer in the Streamlit interface.

```text
FAQ Dataset (CSV)
       |
       v
Document Loading
       |
       v
Text Embeddings
       |
       v
FAISS Vector Index
       |
       v
User Question
       |
       v
Relevant Document Retrieval
       |
       v
Google PaLM + LangChain
       |
       v
Generated Answer
       |
       v
Streamlit Interface
```


## Key Concepts Explored

- Retrieval-Augmented Generation (RAG)
- Text embeddings and semantic similarity
- Vector databases and FAISS indexing
- Document loading and retrieval
- Prompt engineering and context-grounded generation
- LLM integration with LangChain
- Building interactive applications with Streamlit
- Environment variable management

## Limitations

- Answer quality depends on the coverage and quality of the FAQ dataset.
- Relevant information may not be retrieved for ambiguous or unsupported questions.
- The application does not guarantee that every generated answer is factually correct.
- The original implementation uses older Google PaLM and LangChain APIs.
- The current implementation is a learning project and has not been verified as a production-ready service.

## Acknowledgements

This project was developed as a learning exercise using the Codebasics Q&A tutorial and its reference implementation.

Original repository: [Codebasics LangChain Tutorial](https://github.com/codebasics/langchain)

The project is intended to demonstrate my understanding of LLM application development, embeddings, vector search, and RAG workflows. Any additional modifications or improvements should be documented separately from the original tutorial implementation.

## Future Improvements

- Migrate to a currently supported LLM provider and LangChain APIs.
- Display retrieved source documents alongside generated answers.
- Add input validation, error handling, and logging.
- Cache the loaded model, vector index, and retrieval chain.
- Evaluate retrieval quality and answer faithfulness using a test dataset.
- Add automated tests and reproducible setup instructions.
