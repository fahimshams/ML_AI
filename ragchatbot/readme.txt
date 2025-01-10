# PowerPoint-based QA System with OpenAI and ChromaDB

This project implements a pipeline for processing PowerPoint files (`.pptx`), generating embeddings using OpenAI's API, storing them in ChromaDB for efficient retrieval, and enabling question-answering (QA) functionality. The system is designed to handle presentations as input, extract relevant content, and provide concise, context-aware answers to user queries.

---

## ✨ Features

- **PowerPoint File Parsing**: Extracts text from slides in `.pptx` files.
- **Text Chunking**: Splits extracted text into manageable chunks for embedding.
- **Embedding Generation**: Uses OpenAI's `text-embedding-3-small` model to create embeddings for text chunks.
- **Persistent Storage**: Stores embeddings and text in ChromaDB for efficient query processing.
- **QA Functionality**: Leverages OpenAI's `gpt-3.5-turbo` model to generate answers based on retrieved text.

---

## 📂 Project Structure

- `lectures/`: Directory containing `.pptx` files to be processed.
- `chroma_persistent_storage/`: Persistent storage for ChromaDB embeddings.
- Main script: Contains all functions for document loading, embedding, and QA.

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8 or higher
- Install required libraries:
  ```bash
  pip install python-dotenv chromadb openai python-pptx

🛠️ Key Components
1. Loading Documents
Extracts text from .pptx files:
Reads slides and shapes.
Appends text into a single document per file.

2. Chunking Text
Splits long text into overlapping chunks:
Default chunk size: 1000 characters.
Default overlap: 20 characters.

3. Generating Embeddings
Embeddings for each chunk are generated using OpenAI's embedding model.

4. Persistent Storage
Stores text chunks and their embeddings in ChromaDB.

5. Question Answering
Queries ChromaDB for relevant text chunks based on the question.
Generates concise answers using OpenAI's gpt-3.5-turbo.

📖 Usage
Add .pptx files to the lectures directory.
Run the script to process the files and store embeddings.
Ask questions by modifying the question variable in the script.

🛡️ Error Handling
Handles missing .pptx files gracefully.
Adds placeholders for empty slides or shapes without text.
Logs errors for API failures.

📝 Future Enhancements
Add support for other document formats (e.g., .pdf, .docx).
Enable batch processing for larger datasets.
Introduce a web-based interface for user interaction.
Optimize embedding generation for better performance.
