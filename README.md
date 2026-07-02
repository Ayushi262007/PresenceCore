# PresenceCore — Multi-Modal Biometric Identity System

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)

**Enterprise-grade biometric presence detection using facial recognition and acoustic voice fingerprinting.**

[App Service](./ai-attendance-project-app) · [Landing Portal](./ai-attendance-project-landing) · [GitHub Profile](https://github.com/Ayushi262007)

</div>

---

## 🧠 Project Overview

PresenceCore is a full-stack, AI-powered biometric identity system designed for real-world enterprise deployment. It combines two independent pipelines — **facial biometrics** and **acoustic voice fingerprinting** — to achieve multi-modal presence detection with high accuracy and low-latency verification.

The system is built to replace traditional manual attendance or card-based check-in systems with a seamless, automated, and secure AI-driven alternative.

---

## 🏗️ Repository Structure

```
PresenceCore/
├── ai-attendance-project-app/       # Core App Service (Streamlit)
│   ├── app.py                       # Application entry point
│   ├── requirements.txt
│   └── src/
│       ├── screens/                 # Home, Teacher, Student views
│       └── components/              # Reusable UI components & dialogs
│
└── ai-attendance-project-landing/   # Public Landing Portal (Flask + Vercel)
    ├── app.py                       # Flask server
    ├── vercel.json                  # Edge deployment config
    ├── templates/                   # HTML templates
    └── static/                      # CSS, JS, assets
```

---

## 🔬 Core Technical Features

### Facial Biometric Pipeline
- Extracts **128-dimensional facial embeddings** using `dlib`'s deep neural network
- Trains a **balanced-class SVM classifier** on enrolled user embeddings
- Achieves real-time identity verification with sub-second inference latency

### Acoustic Voice Footprinting
- Processes microphone input using `librosa` audio segmentation (`top_db=30` threshold)
- Generates **unique voice embeddings** per speaker via `Resemblyzer`'s deep speaker encoder
- Enables speaker diarization and verification in multi-speaker classroom environments

### Relational Database & Access Control
- Powered by **Supabase (PostgreSQL)** for persistent user profiles, session records, and attendance logs
- Implements **Role-Based Access Control (RBAC)** distinguishing Teacher and Student roles
- Secure join-code-based auto-enrollment flow via URL query parameters

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| App Framework | Streamlit |
| Landing Page | Flask + Jinja2 |
| Face Recognition | dlib, face-recognition |
| Voice Recognition | Resemblyzer, librosa |
| Database | Supabase (PostgreSQL) |
| Deployment | Vercel (landing), Streamlit Cloud (app) |

---

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/Ayushi262007/PresenceCore.git
cd PresenceCore
```

### 2. Run the App Service
```bash
cd ai-attendance-project-app
pip install -r requirements.txt
streamlit run app.py
```

### 3. Run the Landing Portal
```bash
cd ai-attendance-project-landing
pip install -r requirements.txt
python app.py
# Serves on http://localhost:5002
```

> **Note:** Configure Supabase credentials (`SUPABASE_URL`, `SUPABASE_KEY`) in your environment before running the app service.

---

## 📐 System Architecture

```
┌─────────────────────────────────────────────────────────┐
│                   PresenceCore System                     │
│                                                           │
│  ┌─────────────┐    ┌──────────────────────────────────┐ │
│  │   Landing   │    │         App Service               │ │
│  │   Portal    │───▶│  ┌────────────┐ ┌─────────────┐  │ │
│  │  (Flask)    │    │  │  Face      │ │   Voice     │  │ │
│  └─────────────┘    │  │  Pipeline  │ │  Pipeline   │  │ │
│                     │  │  (dlib+SVM)│ │(Resemblyzer)│  │ │
│                     │  └─────┬──────┘ └──────┬──────┘  │ │
│                     │        └────────┬───────┘         │ │
│                     │         ┌───────▼──────┐          │ │
│                     │         │   Supabase   │          │ │
│                     │         │  PostgreSQL  │          │ │
│                     │         └──────────────┘          │ │
│                     └──────────────────────────────────┘ │
└─────────────────────────────────────────────────────────┘
```

---

## 👩‍💻 Author

**Ayushi Gohel**
- GitHub: [@Ayushi262007](https://github.com/Ayushi262007)

---

## 📄 License

This project is intended for academic and research portfolio purposes.
