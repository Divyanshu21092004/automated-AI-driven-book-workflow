# Automated-AI-driven-book-workflow

This project builds a complete AI-powered system that automates the processing, enhancement, and semantic querying of book chapters using LLMs, human-in-the-loop review, and vector storage with ChromaDB.

Features & Workflow

- Chapter Scraping:
Uses Playwright to extract book chapters from URLs (e.g., Wikisource).
Saves clean chapter text in data/chapters/original.

- Chapter Spinning using AI:
Uses DeepSeek LLM (via OpenRouter API) to rewrite ("spin") the original chapter into an engaging, human-like narrative.
Stores output in data/chapters/spun.

- Human-in-the-Loop Review:
Loads the AI-spun chapter for manual review.
Opens a temporary editable file (edit_me.txt) where human edits can be applied.
Final reviewed version is saved in data/chapters/final.

- Semantic Storage with ChromaDB:
Final chapter version is stored in ChromaDB as a document vector.
Metadata like chapter name and version are stored for easy retrieval.

- Intelligent Question Answering:
Queries are semantically matched against stored chapters using ChromaDB.
Uses DeepSeek LLM again to provide contextual answers based on top-matching text chunks.

- Modular & Reusable:
Can be extended to handle multiple chapters.
Works with any LLM compatible with OpenRouter (e.g., DeepSeek, Mistral, etc.)
