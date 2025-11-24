# AI-Powered Movie Recommender – Containerized DevOps Capstone

![React](https://img.shields.io/badge/React-61DAFB?logo=react&logoColor=000)
![Node.js](https://img.shields.io/badge/Node.js-339933?logo=node.js&logoColor=white)
![Gemini](https://img.shields.io/badge/Google_Gemini-8E75B2?logo=google&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?logo=kubernetes&logoColor=white)
![Azure](https://img.shields.io/badge/Azure_Kubernetes_Service-0089D6?logo=microsoft-azure&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?logo=github-actions&logoColor=white)
![GHCR](https://img.shields.io/badge/GHCR-181717?logo=github&logoColor=white)

This repository contains the **official Week 6 Capstone Project** — a group-built, fully containerized and CI/CD-automated **Movie Recommendation Web App** powered by **Google Gemini 2.5 Flash** and successfully deployed on **Azure Kubernetes Service (AKS)**.

## Project Overview

A sleek, responsive React application that delivers highly personalized movie recommendations using natural-language prompts. Powered by **Google Gemini 2.5 Flash**, users simply describe what they’re in the mood for and instantly get curated suggestions with reasoning.

Fully production-grade stack: multi-stage Docker → GHCR → GitHub Actions → AKS.

## Roles & Contributors (as per Project Brief)

| # | Role                          | Name                    | Primary Focus Area                                                  | Core Requirements Covered                                      |
|---|-------------------------------|-------------------------|---------------------------------------------------------------------|-----------------------------------------------------------------|
| 1 | **AI Application Developer**  | **Thoriso**           | Designed & built the React frontend + Gemini 1.5 Flash integration | 2: AI-Powered Low-Code Application Development                |
| 2 | **Containerization Specialist**| **Pallo**           | Created optimized multi-stage Dockerfile & managed GHCR            | 1: Containerization Setup                                      |
| 3 | **DevOps Engineer (CI/CD)**   | **Lethabo**           | Built and tested end-to-end GitHub Actions pipeline                | 3: DevOps Integration                                          |
| 4 | **Cloud/Platform Engineer**   | **Lesego**           | Deployed, secured, and scaled the app on Azure Kubernetes Service  | 4: Orchestration & Cloud Deployment<br>5: Security & Resource Management |

## Features

- Modern React UI (Vite + Vanilla CSS)
- Node.js runtime for build and production
- Real-time movie recommendations via **Gemini 2.5 Flash**
- Natural language input (e.g., “cozy Christmas movie with dogs”)
- Streaming responses, loading states, error handling
- Secure API key management with Kubernetes Secrets

## Tech Stack

- **Frontend**: React 18 + Vite + Vanilla CSS
- - **Runtime**: Node.js
- **AI**: Google Gemini 2.5 Flash
- **Container**: Docker (multi-stage, ~180 MB final image)
- **Registry**: GitHub Container Registry (ghcr.io)
- **CI/CD**: GitHub Actions
- **Orchestration**: Azure Kubernetes Service (AKS)


## Core Requirements Status

| Requirement                                 | Status | Evidence                                          |
|---------------------------------------------|--------|---------------------------------------------------|
| Multi-stage Dockerfile                      | Done   | `/Dockerfile` (~180 MB)                           |
| Image on GHCR                               | Done   | `ghcr.io/kono-seema/ai-low-code-app:latest` |
| Gemini 2.5 Flash integration                | Done   | Live recommendations                              |
| GitHub Actions CI/CD                        | Done   | `.github/workflows/main.yml`                    |
| Automated deployment to AKS                 | Done   | Pipeline runs `kubectl apply`                     |
| Live HTTPS deployment                       | Done   | HTTPS via Ingress + cert-manager           |
| Secrets, limits, HPA, security best practices | Done | All in `k8s/`                                     |

## Live Demo

**Movie Recommender**: http://4.253.88.198/  

Try prompts like:  
- “A mind-bending thriller like Inception but with more humor”  
- “Feel-good 90s rom-com with a strong soundtrack”

## Local Development

```bash
git clone https://github.com/yourusername/movie-gemini-recommender.git
cd movie-gemini-recommender
npm install
# Add your key
echo "VITE_GEMINI_API_KEY=your_key_here" > .env
npm run dev 
```

## CI/CD & Deployment Highlights

- **GitHub Actions** automatically builds, pushes to GHCR, and deploys to AKS on every push to `main`  
- Zero-downtime rolling updates  
- Horizontal Pod Autoscaler (HPA) with CPU-based scaling + strict resource requests/limits  
- Gemini API key stored securely as a Kubernetes Secret (never exposed in code or images)  

## Azure Kubernetes Deployment

Running on **Azure Kubernetes Service (AKS)** with the following production-grade configuration:

- **Horizontal Pod Autoscaler** (HPA) — auto-scales pods when CPU > 60%  
- **Resource requests & limits** enforced for predictable performance and cost control  
- **Google Gemini API key** securely injected via Kubernetes Secret (never hardcoded)  
- **Automatic SSL/TLS** powered by cert-manager + Let's Encrypt (free, auto-renewing certificates)  
