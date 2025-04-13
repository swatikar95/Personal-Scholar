# Personal Scholar

Personal Scholar is an advanced AI-powered research assistant that helps users interact with and analyze academic PDF documents. It leverages state-of-the-art language models and vector databases to provide intelligent document processing and question-answering capabilities.

## Project Overview

Personal Scholar is designed to help researchers, students, and academics efficiently process and interact with academic papers. The system can:
- Extract and process text from PDF documents
- Create vector embeddings for semantic search
- Answer questions about the content of papers
- Provide detailed analysis and summaries
- Support multiple language models for different use cases

## Technical Architecture

### Core Components

1. **Document Processing**
   - PDF text extraction using PyPDF2
   - Text cleaning and preprocessing
   - Chunking and text splitting for efficient processing

2. **Embedding and Vector Storage**
   - Uses HuggingFace's sentence-transformers for embeddings
   - FAISS vector database for efficient similarity search
   - Configurable chunk size and overlap parameters

3. **Language Model Integration**
   - Support for multiple LLM backends (Ollama, GPT, Claude)
   - Configurable model selection
   - Adaptive prompt engineering

### Key Features

- **Multi-Model Support**: Compatible with various LLMs including:
  - Llama 2/3
  - GPT-3.5/4
  - Claude 2/3
  - Gemma
  - Mistral
  - And more

- **Advanced Text Processing**:
  - Intelligent text chunking
  - Semantic search capabilities
  - Context-aware responses

- **Flexible Configuration**:
  - Adjustable chunk sizes
  - Configurable model parameters
  - Customizable prompt templates

## Setup and Installation

### Prerequisites

- Python 3.8+
- Ollama (for local LLM support)
- Required Python packages:
  ```
  PyPDF2
  numpy
  requests
  sentence-transformers
  langchain
  faiss-cpu
  ```

### Installation Steps

1. Clone the repository
2. Install required packages:
   ```bash
   pip install -r requirements.txt
   ```
3. Set up Ollama (if using local models):
   ```bash
   # Install Ollama
   # Pull desired model
   ollama pull llama2
   ```

### Configuration

1. Set up your PDF directory:
   ```python
   PDF_DIRECTORY = "pdf/"
   ```

2. Configure vector database path:
   ```python
   VECTOR_DB_PATH = "faiss_index"
   ```

3. Adjust processing parameters:
   ```python
   CHUNK_SIZE = 1000
   CHUNK_OVERLAP = 200
   ```

## Usage

1. Place PDF files in the configured directory
2. Initialize the system:
   ```python
   from personal_scholar import PersonalScholar
   scholar = PersonalScholar()
   ```

3. Process documents:
   ```python
   scholar.process_documents()
   ```

4. Ask questions:
   ```python
   response = scholar.ask_question("What are the main findings of this paper?")
   ```

## Advanced Features

### Custom Model Integration

The system supports integration with various LLM providers:

```python
# Configure Ollama
OLLAMA_MODEL = "llama2:latest"
OLLAMA_URL = "http://localhost:11434/api/generate"

# Or use other providers
MODEL_PROVIDER = "openai"  # or "anthropic", "huggingface"
```

### Custom Embeddings

Configure different embedding models:

```python
embedding_model = HuggingFaceEmbeddings(
    model_name="sentence-transformers/all-mpnet-base-v2",
    model_kwargs={'device': 'cpu'}
)
```

## Performance Considerations

- Vector database size scales with document collection
- Processing time depends on document length and complexity
- Response time varies based on selected LLM and query complexity

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- HuggingFace for the sentence-transformers library
- Meta for the Llama models
- OpenAI for GPT models
- Anthropic for Claude models
- Google for Gemma

## Author
Swati Kar

PhD Student, UTC, TN, Chattanooga

