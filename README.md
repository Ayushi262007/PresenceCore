# PresenceCore: Multi-Modal Biometric Identity System (Landing Portal)

Welcome to the public-facing landing portal for **PresenceCore**. This repository contains the static marketing and entry-point website that directs users to the main biometric authentication service. 

## Overview
PresenceCore is a scalable biometric presence detection engine. This landing page is designed to highlight the technical features of the platform, including its facial recognition and acoustic footprinting pipelines.

## Setup & Execution

This is a lightweight Flask application designed to serve static assets and templates.

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/presencecore-landing.git
    cd presencecore-landing
    ```

2.  **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Run the Development Server:**
    ```bash
    python app.py
    ```

The server will start locally (typically on port 5002) and serve the static HTML, CSS, and JS assets.

## Deployment
This portal is configured for easy deployment on edge networks like Vercel (see `vercel.json`).
