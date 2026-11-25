# Wisebase AI Server

Python and FastAPI service that analyses image, audio and video from the Wisebase scan flow. Wisebase is a multi-role workforce management platform that I built at DataC and keep improving.

**Product page:** https://conntinuity.datac.com/

This is the first-generation AI service. A newer service lives in [WiseBase_ai_v2](https://github.com/mnashat18/WiseBase_ai_v2).

## What it does

- Receives scan media from the Wisebase apps through REST APIs
- Validates and scores image, audio and video input
- Runs machine learning inference and returns results to the platform
- Sends results back to the Directus backend (`directus_client.py`)

## Tech stack

Python, FastAPI, PyTorch, OpenCV, MediaPipe, Whisper, Librosa, Docker.

## How it fits together

```text
Flutter app / Angular web app  ->  Directus backend  ->  AI server  ->  models
```

## Repository layout

| Path | Contents |
| --- | --- |
| `main.py` | FastAPI entry point |
| `analysis_runtime.py`, `analysis_worker.py` | Analysis pipeline and worker |
| `audio.py`, `video.py`, `vision.py` | Media processing |
| `validation.py`, `quality.py`, `scoring.py`, `baseline.py` | Validation and scoring |
| `ml/` | Model code |
| `sql/` | SQL scripts |
| `tests/` and `test_*.py` | Tests |
| `Dockerfile` | Container build |

## Run locally

```bash
pip install -r requirements.txt
uvicorn main:app --reload
```

## Author

Mohamed Nashat Ghonim, Full-Stack Developer
[LinkedIn](https://www.linkedin.com/in/mohamed-nashat-ghonim/) · [GitHub](https://github.com/mnashat18) · mnashat2508@gmail.com
