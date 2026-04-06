# Agentic RAG (LangChain + Gemini)

A simple Retrieval-Augmented Generation (RAG) learning project built with LangChain.

This repository demonstrates:
- document creation and loading,
- text chunking,
- vector indexing and retrieval,
- final answer generation using Gemini models.

## Project Structure

- `main.py`: Minimal Python entrypoint.
- `notebook/document.ipynb`: Main end-to-end RAG workflow.
- `data/text_files/`: Sample source files used for retrieval.
- `requirements.txt`: Pip dependency list.
- `pyproject.toml`: Project metadata and dependencies.

## Features

- Creates and loads plain-text documents.
- Splits documents into retrieval-friendly chunks.
- Builds an in-memory vector store and retriever.
- Runs a final prompt + LLM chain with Gemini.
- Includes simple model fallback logic.

## Requirements

- Python 3.13+
- A Gemini API key (set in environment as `GOOGLE_API_KEY`)

## Setup

### Option 1: Use existing virtual environment

```bash
source .venv/bin/activate
pip install -r requirements.txt
```

### Option 2: Fresh environment

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## Run the notebook

1. Open `notebook/document.ipynb` in VS Code.
2. Select the Python kernel from your `.venv`.
3. Run cells from top to bottom.
4. Before the Gemini section, set your API key as an environment variable.

Linux/macOS:

```bash
export GOOGLE_API_KEY="your_gemini_api_key"
```

Windows PowerShell:

```powershell
$env:GOOGLE_API_KEY="your_gemini_api_key"
```

## Run the Python entrypoint

```bash
python main.py
```

## Security Notes

- Do not hardcode API keys in notebooks or source files.
- Use environment variables for secrets.
- If a key is exposed, rotate/revoke it immediately.
- Notebook outputs can accidentally capture sensitive data; clear outputs before sharing.

## Troubleshooting

- If imports fail, verify the correct virtual environment is active.
- If Gemini calls fail, confirm `GOOGLE_API_KEY` is set in the same shell/kernel session.
- If model access is limited, try another model from the candidate list in the notebook.

## Next Improvements

- Add persistent vector storage (FAISS/Chroma).
- Add document ingestion for PDFs.
- Add evaluation prompts and retrieval quality checks.
- Add dependency security scanning in CI.
