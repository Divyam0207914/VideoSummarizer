# 🎥 AI Video Intelligence Assistant

An end-to-end AI-powered meeting intelligence platform that transforms YouTube videos or local recordings into searchable knowledge.

The application automatically downloads videos, transcribes speech, summarizes discussions, extracts action items and decisions, and allows users to chat with the meeting using Retrieval-Augmented Generation (RAG).

---

## Features

- 🎥 Download audio from YouTube videos
- 🎙️ Local transcription using OpenAI Whisper
- 🌍 Hindi/Hinglish → English transcription using Sarvam AI
- 📝 Professional AI meeting summaries
- 📌 Automatic meeting title generation
- ✅ Action Item Extraction
- 🔑 Key Decision Extraction
- ❓ Open Question Identification
- 🧠 Retrieval-Augmented Generation (RAG)
- 💬 Chat with your meeting transcript
- 📊 Modern Streamlit dashboard

---

## Architecture

```
YouTube / Local Video
          │
          ▼
 Audio Extraction (yt-dlp)
          │
          ▼
 WAV Conversion (FFmpeg)
          │
          ▼
 Audio Chunking
          │
          ▼
 Whisper / Sarvam AI
          │
          ▼
 Complete Transcript
          │
          ├──────────────► Meeting Summary
          │
          ├──────────────► Meeting Title
          │
          ├──────────────► Action Items
          │
          ├──────────────► Decisions
          │
          ├──────────────► Open Questions
          │
          ▼
 Chroma Vector Store
          │
          ▼
 Mistral + LangChain RAG
          │
          ▼
 Chat with Meeting
```

---

## Tech Stack

### AI

- OpenAI Whisper
- Mistral AI
- LangChain LCEL
- ChromaDB
- HuggingFace Embeddings

### Backend

- Python
- yt-dlp
- FFmpeg
- Pydub

### Frontend

- Streamlit

---

## Folder Structure

```
.
├── app.py
├── main.py
├── core
│   ├── extractor.py
│   ├── rag_engine.py
│   ├── summarize.py
│   ├── transcriber.py
│   └── vector_store.py
├── utils
│   └── audio_processor.py
├── requirements.txt
└── README.md
```

---

## Installation

Clone the repository

```bash
git clone https://github.com/Divyam0207914/VideoSummarizer.git
cd VideoSummarizer
```

Create a virtual environment

```bash
python3.11 -m venv .venv
source .venv/bin/activate
```

Install dependencies

```bash
uv pip install -r requirements.txt
```

Install FFmpeg

```bash
brew install ffmpeg
```

---

## Environment Variables

Create a `.env` file.

```
MISTRAL_API_KEY=your_key
SARVAM_API_KEY=your_key
WHISPER_MODEL=small
```

---

## Run

### CLI

```bash
python main.py
```

### Streamlit

```bash
streamlit run app.py
```

---

## Future Improvements

- Speaker Diarization
- Multi-language support
- PDF Report Export
- Email Meeting Minutes
- Meeting Timeline
- OCR from Presentation Slides
- Video Timestamp Search
- Cloud Deployment

---

## License

MIT License
