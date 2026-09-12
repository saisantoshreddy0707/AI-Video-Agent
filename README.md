# 🎬 AI Video Assistant: Meeting Intelligence Platform

An end-to-end AI-powered meeting intelligence system built with **LangChain (LCEL)**, **Mistral AI**, **OpenAI Whisper**, **Sarvam AI**, **ChromaDB**, and **Streamlit**. 

This application ingests audio/video from YouTube links or local media files, transcribes speech, extracts key insights, generates structured summaries, and builds a local Retrieval-Augmented Generation (RAG) vector store so you can interactively chat with your meeting transcript.

---

## 🌟 Key Features

* **Dual-Engine Speech-to-Text (STT)**:
  * **English**: Uses local **OpenAI Whisper** models (`small`, `base`, etc.) for offline transcription.
  * **Hinglish / Code-Switched**: Routes to **Sarvam AI** (`saaras:v2.5`) for speech translation and transcription into English.
* **Audio Processing Pipeline**: Automatically downloads YouTube audio via `yt-dlp`, converts media files to 16kHz mono WAV, and handles long audio files using smart chunking (`pydub`).
* **Intelligent Extraction & Summarization**:
  * **Map-Reduce Summarization**: Handled with `RecursiveCharacterTextSplitter` to summarize long audio transcripts without exceeding context windows.
  * **Structured Insights**: Automatically extracts **Action Items** (Task, Owner, Deadline), **Key Decisions**, and **Open Questions**.
  * **Title Generation**: Generates concise, context-aware meeting titles.
* **Interactive RAG Chat Engine**:
  * Uses **ChromaDB** vector store and **HuggingFace Embeddings** (`all-MiniLM-L6-v2`) to index transcript chunks.
  * Question-Answering powered by **Mistral AI** (`mistral-small-latest`).
* **Dual User Interfaces**:
  * **Streamlit Web Dashboard**: Custom-styled cyber/dark neon aesthetic with step-by-step pipeline status bars, styled insight cards, and chat history.
  * **CLI Tool**: Run full analysis pipelines directly from the terminal via `main.py`.

---

## 🏗 System Architecture
