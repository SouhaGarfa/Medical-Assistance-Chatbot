# 🩺 Medical-Assistance-Chatbot

> **Internship project @ [Multiverse AI](https://www.multiverse-ai.com)**  
> Supervised by **Amine MOSBAH** · Summer 2025  
> Stack: Python · FastAPI · Groq VLM · LLaMA-4 · HTML/CSS/JS

---

## Overview

**Medical-Assistance-Chatbot** is a multimodal medical chatbot that processes both **text queries** and **medical images** (skin lesions, X-rays, radiographs) to deliver preliminary health guidance. Built during my AI Engineering internship at Multiverse AI, this project explores the practical integration of open-source Vision-Language Models (VLMs) into a lightweight, privacy-respecting web application.

The core challenge: most existing medical chatbots are text-only. This system bridges that gap by enabling visual understanding alongside natural language, without relying on paid proprietary APIs.

---

## Motivation

> *"How can we design a medical chatbot capable of understanding both text and medical images using open-source technologies, while ensuring accessibility, reliability, and data privacy?"*

Existing solutions like ChatGPT Vision or Gemini require cloud access and paid APIs, making them unsuitable for local or academic deployment. This project demonstrates that open models — specifically Meta's LLaMA-4 family served via Groq — can achieve competitive accuracy in medical multimodal tasks.

---

## Architecture

```
User
 │
 ▼
Frontend (HTML/CSS/JS)
 │  text query + image upload
 ▼
Backend (FastAPI REST API)
 │  formats multimodal payload
 ▼
Groq VLM (LLaMA-4 Scout / Maverick)
 │  image + text → medical response
 ▼
Frontend — response displayed in real time
```

Three-layer design ensures clean separation of concerns: the frontend, backend, and AI model can each evolve independently.

---

## Models

Two LLaMA-4 models were benchmarked side by side via the [Groq API](https://console.groq.com/docs/vision):

| Model | Architecture | Strengths |
|---|---|---|
| `llama-4-maverick-17b-128e-instruct` | MoE · 128 experts | Higher accuracy, detailed visual reasoning |
| `llama-4-scout-17b-16e-instruct` | MoE · 16 experts | Faster inference, lighter deployment |

Both models process **text and image simultaneously**, enabling true multimodal understanding.

---

## Evaluation Results

The system was evaluated on **20–30 examples per input type per model**, processed automatically via `main.py` hitting the FastAPI endpoints.

| Input Type | Maverick Accuracy | Scout Accuracy | Notes |
|---|---|---|---|
| Text queries | **95%** | 90% | Both strong; Maverick more specific |
| Normal images | **100%** | **100%** | Both correctly reject non-medical content |
| Skin lesions | **90%** | 75% | Maverick provides more precise diagnosis |
| X-ray images | **85%** | 80% | Complex reasoning; Maverick slightly better |

**Key finding:** Maverick's larger expert count (128 vs 16) translates into measurable gains in medical specificity, particularly for dermatological images. Scout's lower latency makes it a viable option for resource-constrained contexts.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Language | Python 3.10 |
| Backend | FastAPI |
| AI / VLM | Groq API — LLaMA-4 Scout & Maverick |
| Frontend | HTML · CSS · JavaScript |
| Testing | Python · JSON test sets |
| Version control | Git / GitHub |
| Deployment | Localhost / Render |

---

## Features

- **Multimodal input** — accepts text questions and image uploads (skin, X-ray, general)
- **Dual-model comparison** — responses from both Scout and Maverick displayed side by side
- **Automated evaluation pipeline** — Python script tests all examples and logs accuracy + latency
- **Privacy-first** — no user data or medical images stored after processing
- **Responsive UI** — usable on desktop and mobile without technical knowledge

---

## Limitations & Future Work

- **Test set size** — ~20–30 samples per category; larger benchmarks needed for statistical robustness
- **No domain fine-tuning** — models used as-is; fine-tuning on CheXpert or DermNet would improve diagnostic accuracy
- **No conversational memory** — each query is stateless; future versions could add context retention
- **Explainability** — confidence scores and attention heatmaps would improve trust in clinical settings
- **Regulatory compliance** — HIPAA/GDPR considerations required for real-world medical deployment

---

## Project Structure

```
Medical-Assistance-Chatbot/
├── templates/
│   └── index.html          # Web interface (frontend)
├── app.py                  # FastAPI app — routing & Groq API integration
├── main.py                 # Evaluation pipeline — automated model benchmarking
├── .gitignore
└── README.md
```

---

## Context

This project was developed as part of my **2nd-year Software Engineering internship** at **Multiverse AI** (Tunisia), under the supervision of **Amine MOSBAH**. It was also submitted as an academic report to **Ibn Khaldoun University** (UIK), directed by **Dr. Yasmine BEN DHIAB**.

The internship followed a **Solo Scrum** methodology across 5 sprints: environment setup → model integration → backend → frontend → testing & deployment.

---

## Disclaimer

> This chatbot is a **research prototype** and is not a substitute for professional medical advice, diagnosis, or treatment. Always consult a qualified healthcare provider for medical decisions.

---

*Built with curiosity and caffeine · Multiverse AI · 2025*
