# LangChain Tutorials

Personal walkthroughs of the official LangChain tutorials, kept here for reference and practice.

Source: [docs.langchain.com/oss/python/langchain/knowledge-base](https://docs.langchain.com/oss/python/langchain/knowledge-base)

## Tutorials

| Folder | Topic | Source |
| --- | --- | --- |
| [`semantic_search/`](./semantic_search) | Build a semantic search engine over a PDF using OpenAI embeddings + Chroma | [knowledge-base](https://docs.langchain.com/oss/python/langchain/knowledge-base) |

## Running a tutorial

Each tutorial folder is self-contained with its own virtual environment so dependencies don't clash across tutorials.

```bash
cd semantic_search
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt   # or follow the %pip install cells in the notebook
jupyter lab semantic_search.ipynb
```

## API keys

Copy `.env.example` to `.env` at the repo root (or inside a tutorial folder) and fill in the keys you need:

```bash
cp .env.example .env
```

`.env` is gitignored — never commit it. Load it in a notebook with:

```python
from dotenv import load_dotenv
load_dotenv()
```
