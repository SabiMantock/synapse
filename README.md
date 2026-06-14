# synapse

A local RAG (retrieval-augmented generation) system for your Obsidian vault. Ask questions in plain English and get answers grounded in your own notes.

## How it works

1. Loads all markdown notes from your Obsidian vault
2. Embeds them using `sentence-transformers` (`all-MiniLM-L6-v2`)
3. Finds the most semantically relevant notes for your question
4. Sends those notes + your question to Claude, which answers using only what's in your notes

## Setup

1. Clone the repo and copy the example env file:

```bash
cp .env.example .env
```

2. Fill in `.env` with your values:

```
WIKI_PATH=/path/to/your/obsidian/vault
ANTHROPIC_API_KEY=your-api-key-here
```

3. Install dependencies:

```bash
pip install sentence-transformers scikit-learn python-dotenv anthropic
```

4. Open `synapse.ipynb` and run all cells.

## Stack

- [`sentence-transformers`](https://www.sbert.net/) — local embeddings
- [`scikit-learn`](https://scikit-learn.org/) — cosine similarity search
- [`anthropic`](https://docs.anthropic.com/) — Claude for grounded answers
