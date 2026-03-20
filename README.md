# Ghost Load Eliminator – Predictive Backhaul Orchestration

[![Hackathon](https://img.shields.io/badge/Hackathon-HH%202.0-orange)](https://github.com/yourteam/ghost-load-eliminator) 
[![License](https://img.shields.io/badge/License-MIT-blue)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.10+-blue)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.95+-teal)](https://fastapi.tiangolo.com/)
[![React](https://img.shields.io/badge/React-18-blue)](https://reactjs.org/)

> **Turning empty miles into revenue – before the truck moves.**

## 📌 Table of Contents
- [Overview](#overview)
- [Problem Statement](#problem-statement)
- [Our Solution](#our-solution)
- [Key Features](#key-features)
- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [Demo & Prototype](#demo--prototype)
- [Installation & Setup](#installation--setup)
- [Pilot Results](#pilot-results)
- [UN SDG Alignment](#un-sdg-alignment)
- [Team](#team)
- [References](#references)

---

## Overview

**Ghost Load Eliminator** is an AI‑powered logistics platform that predicts and matches return loads *before* a truck finishes its current trip. By integrating with India’s **Unified Logistics Interface Platform (ULIP)** and using **Multi‑Agent Reinforcement Learning**, we help small fleet owners eliminate deadheading, reduce idle days, and increase revenue – all through a simple WhatsApp interface.

---

## Problem Statement

- **~30–40% of trucks in India run empty on return trips** (deadheading), leading to **₹80,000 crore** in annual losses.
- Small fleet owners (10+ million) lose ~25% of potential revenue to fuel and maintenance costs without earning.
- Current load boards are **reactive** – they only show loads after the truck is empty, causing long waiting times and information asymmetry.

---

## Our Solution

**Predictive Backhaul Orchestration** that matches loads *before* the truck reaches its destination.

- **ULIP Integration** – real‑time Fastag location + E‑way bill data.
- **Multi‑Agent Reinforcement Learning** – optimises truck–load assignments with ROI‑driven detours.
- **WhatsApp Bot + Bhashini Voice** – regional language interface for drivers (Hindi, Marathi, Telugu).

### Pilot Results (Pune–Mumbai Corridor, 15 trucks, 4 weeks)
- **68% reduction in empty miles**
- **₹7,200 additional income per truck/week** (₹28,800/month)
- **Zero idle days** for matched trucks

---

## Key Features

| Feature | Description |
|---------|-------------|
| **Predictive Matching** | AI forecasts return loads 4–6 hours ahead using LSTM & MARL. |
| **ROI‑Driven Detours** | Suggests minor route changes (≤15 km) that yield high‑margin loads. |
| **WhatsApp Driver Bot** | Intuitive voice + text interface; supports Hindi, Marathi, Telugu. |
| **Shipper Dashboard** | Real‑time load board, route visualisation, ULIP sync. |
| **ULIP & FASTag Integration** | Live tracking of trucks via government APIs. |
| **Auto E‑Way Bill** | Generation after load acceptance – fully compliant. |

---

## Tech Stack

| Layer | Technology |
|-------|------------|
| **Frontend** | React (Web Dashboard) + WhatsApp Business API (Driver) |
| **Backend** | FastAPI (Python) – async, high‑performance |
| **Database** | PostgreSQL with **PostGIS** (geospatial queries) |
| **AI/ML** | LSTM (demand forecasting), Ray RLlib (Multi‑Agent RL) |
| **APIs** | ULIP Sandbox, Google Maps API, ONDC (future) |
| **Infrastructure** | Docker, AWS (EC2, RDS, S3) |

---

## Architecture

```mermaid
graph TD
    A[Driver WhatsApp] -->|Voice/Text| B[WhatsApp Business API]
    B --> C[FastAPI Backend]
    D[ULIP API] -->|FASTag + E‑way bill| C
    C --> E[PostgreSQL + PostGIS]
    C --> F[AI Matching Engine]
    F -->|MARL + LSTM| G[Predictive Loads]
    G --> C
    C --> H[Shipper Dashboard]
    H --> I[React Frontend]
    C -->|Push Notifications| A
```


---

## Demo & Prototype

- **Live Prototype Screens** – see the `ghost-load-mvp.html` file for interactive mockups of:
  - Shipper Dashboard  
  - WhatsApp Driver Bot  
  - AI Matching Console  
  - Pilot Analytics  


---

## Installation & Setup

### Prerequisites
- Python 3.10+
- Node.js 18+
- PostgreSQL with PostGIS
- Docker (optional)

### Backend
```bash
cd backend
pip install -r requirements.txt
uvicorn main:app --reload --port 8000
```

### Frontend (Shipper Dashboard)
```bash
cd frontend
npm install
npm start
```

### WhatsApp Bot
- Configure WhatsApp Business API account
- Set webhook URL to `https://yourdomain.com/webhook/whatsapp`
- Update environment variables (see `.env.example`)

### Environment Variables
```env
ULIP_API_KEY=your_key
GOOGLE_MAPS_API_KEY=your_key
DATABASE_URL=postgresql://user:pass@localhost/ghostload
```

---

## Pilot Results

| Metric | Before GhostLoad | After GhostLoad | Change |
|--------|------------------|-----------------|--------|
| Empty miles (%) | 30–40% | **12.8%** | **-68%** |
| Idle days per week | 2–3 days | **0 days** | **-100%** |
| Income per truck/week | ~₹18,000 | **₹25,200** | **+40%** |

*Data from 4‑week pilot with 15 trucks on Pune–Mumbai corridor (Jan–Feb 2024).*

---

## UN SDG Alignment

| SDG | Goal | How GhostLoad Contributes |
|-----|------|--------------------------|
| **9** | Industry, Innovation and Infrastructure | Optimises supply chains via ULIP, reduces logistics cost (14% of GDP). |
| **12** | Responsible Consumption and Production | Eliminates fuel waste from empty returns, promotes efficient resource use. |
| **13** | Climate Action | Saves ~12 tons CO₂ per truck per year – directly combating climate change. |

---

## Team

| Name  | Year | LinkedIn | GitHub |
|-------|------|----------|--------|
| ASHIKA | 3rd Year | https://www.linkedin.com/in/ashika-krishnamurthy/ | https://github.com/Ashika005 |
| Buvaneswari S | 3rd Year | https://www.linkedin.com/in/buvaneswari-sakthivel| - |
---

## References

1. **National Logistics Policy 2022** – Government of India  
2. **ULIP (Unified Logistics Interface Platform)** – Developer Documentation  
3. **Cordeau, J.F. et al.** (2007) – “Vehicle Routing Problem with Time Windows”  
4. **NITI Aayog** – “India Logistics Efficiency Enhancement Program”  
5. **SDG Indicators** – United Nations Department of Economic and Social Affairs

---

## 📜 License

This project is submitted for **Hackathon HH 2.0** and is open‑source under the MIT License.

---

**Built with ❤️ by Team ASHIKA K (github.com/Ashika005) & Buvaneswari S**
