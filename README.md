# PresenceCore: Multi-Modal Biometric Identity System (App Service)

PresenceCore is an enterprise-grade biometric identity verification system. This repository contains the primary application service, responsible for orchestrating real-time face and voice recognition pipelines, managing database interactions, and providing a scalable interface for end-users.

## Core Features
*   **Facial Biometric Pipeline**: Utilizes `dlib` 128-dimensional facial embeddings and optimized Support Vector Machines (SVM) for high-accuracy identification.
*   **Acoustic Footprinting**: Integrates `Resemblyzer` and `librosa` to process segmented environmental audio and extract unique voice embeddings for speaker verification.
*   **Relational Database Architecture**: Uses Supabase (PostgreSQL) for secure, scalable state management and role-based access control (RBAC).

## Setup & Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/presencecore-app.git
    cd presencecore-app
    ```

2.  **Install Dependencies:**
    It is recommended to use a virtual environment.
    ```bash
    pip install -r requirements.txt
    ```

3.  **Configure Environment Variables:**
    Ensure you have your Supabase credentials configured in the environment or secrets management system before running.

4.  **Run the Application:**
    ```bash
    streamlit run app.py
    ```

## Architecture Notes
The system utilizes a balanced-class SVM to classify known user embeddings. The audio pipeline intelligently chunks active segments using a decibel threshold (`top_db=30`) to isolate distinct speakers.
