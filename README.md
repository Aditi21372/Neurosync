# NeuroSync: Empathic AI for Inclusive Co-Design

> A full-stack empathic-AI platform that fuses **facial and vocal emotion signals in real time** to detect stress and engagement, then adapts the experience through a conversational companion and VR interaction modalities.

![React](https://img.shields.io/badge/React-19-20232A?style=flat&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-Fusion%20Model-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![Hume EVI](https://img.shields.io/badge/Voice-Hume%20EVI-FF6B6B)

## What it does

- 🎥 **Facial emotion capture** in-browser via camera
- 🎙️ **Vocal emotion analysis** through the Hume Empathic Voice Interface (EVI)
- 🧠 **Multi-modal fusion network** (PyTorch): face + voice embeddings with intensity weighting and an adapter layer, predicting stress/engagement signals
- 💬 **Conversational companion** (chat modality) that adapts to the user's state
- 🥽 **VR interaction modality** for immersive co-design sessions
- 📈 **Live dashboards**: emotion summaries, trend plots, expression levels
- 🧩 **Inclusive co-design flow**: cognitive preference forms, personalization, task breakdown and checklists tuned to the user's state

## Architecture

```
   Browser (React 19 + TypeScript)
   ├── CameraCapture  ──► facial emotion scores ─┐
   ├── HumeEVI        ──► vocal emotion scores ──┤
   │                                             ▼
   │                              neuro-api (FastAPI/Python)
   │                              MultiModalFusionNetwork (PyTorch)
   │                              face_emb + voice_emb + context
   │                              → adapter → stress/engagement outputs
   │                                             │
   └── Chat (NURO companion) ◄───────────────────┘
        VR lounge ◄── session state + emotion trends
```

Trained fusion model weights ship in `neuro-api/fusion_model_weights.pt`; evaluation targets: **MSE 0.0032, cosine similarity 0.9877** on held-out data.

## Quick start

```bash
git clone https://github.com/Aditi21372/Neurosync.git
cd Neurosync

# Web client
npm install
cp .env.example .env
npm start                      # http://localhost:3000

# Emotion fusion API (separate terminal)
cd neuro-api
python -m venv venv && source venv/bin/activate
pip install -r requirements.txt
uvicorn API:app --reload
```

## Built by

Team of 4, Jan to May 2025: [Aditi](https://github.com/Aditi21372), [theaadya](https://github.com/theaadya), [Kanakyadav88](https://github.com/Kanakyadav88), and teammates. Full commit history preserved from the original team repository.

---

Built by [@Aditi21372](https://github.com/Aditi21372) · [More projects](https://github.com/Aditi21372?tab=repositories)
