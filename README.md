<div align="center">

# âœï¸ Writing Pulse
## Agentic AI Blogging Assistant

[![Python](https://img.shields.io/badge/Python-3.11-3776ab?logo=python&logoColor=white)](https://python.org)
[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://project-no-5-vweqdeo9nxhwkobvsk349l.streamlit.app)
[![IBM watsonx.ai](https://img.shields.io/badge/IBM-watsonx.ai-0f62fe?logo=ibm&logoColor=white)](https://www.ibm.com/watsonx)
[![IBM Granite](https://img.shields.io/badge/LLM-IBM%20Granite%203.3-6929c4?logo=ibm&logoColor=white)](https://www.ibm.com/granite)
[![IBM Code Engine](https://img.shields.io/badge/Deploy-IBM%20Code%20Engine-0f62fe?logo=ibm&logoColor=white)](https://cloud.ibm.com/codeengine)
[![License: MIT](https://img.shields.io/badge/License-MIT-22c55e)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen)](https://github.com/mdivate/Project-No-5/pulls)
[![Live Demo](https://img.shields.io/badge/Live%20Demo-Streamlit-ff4b4b?logo=streamlit)](https://project-no-5-vweqdeo9nxhwkobvsk349l.streamlit.app)

**A fully agentic, multi-agent AI blogging assistant powered by IBM Granite LLM via IBM watsonx.ai.**  
Collect real-time news Â· suggest trending topics Â· generate SEO blog drafts Â· analyze audience sentiment Â· predict engagement  
â€” all from an interactive Streamlit dashboard, deployed on **IBM Cloud Code Engine**.

[ðŸš€ Local Quick Start](#-local-quick-start) Â· [â˜ï¸ IBM Cloud Deploy](#ï¸-ibm-cloud-deployment) Â· [âœ¨ Features](#-features) Â· [ðŸ—ï¸ Architecture](#ï¸-architecture) Â· [âš™ï¸ Configuration](#ï¸-configuration)

</div>

---

## âœ¨ Features

| # | Feature | Description |
|---|---|---|
| ðŸ“Š | **Writing Pulse Dashboard** | 5-KPI metrics, live headlines from 10 RSS feeds, trending keyword bar chart, 4-step workflow guide |
| ðŸ” | **Research Agent** | Fetches articles from 10 RSS feeds; IBM Granite synthesizes a 280â€“350-word summary with numbered source citations `[1][2]` |
| ðŸ“ˆ | **Trend Analysis Agent** | Real-time keyword frequency with feed-source attribution; AI-generated SEO topics with differentiating angles |
| âœï¸ | **Content Generation Agent** | Full SEO drafts â€” focus keyword, meta description, H2/H3 structure, CTA; accepts **text + image + voice (.wav)** |
| ðŸŽ¯ | **Editorial Review Agent** | Readability / SEO Quality / Engagement score gauges (0â€“10); strengths, improvements, fact-check flags |
| ðŸ§‘ | **Human-in-the-Loop Gate** | âœ… Approve / âŒ Revise decision gate â€” AI recommends, humans decide |
| ðŸ’¬ | **Audience Sentiment** | Negation- and intensity-aware lexicon; per-comment emoji breakdown; donut chart |
| ðŸ“± | **Social Media Generator** | Twitter/X (â‰¤280 chars), LinkedIn, Instagram; engagement score, reach, optimal publish window |
| ðŸ›¡ï¸ | **Responsible AI Guardrails** | 17-category input **and** output content filter; citations; fact-check flags |
| ðŸ”„ | **Model Fallback** | Granite â†’ Llama 3.3 70B transparent failover â€” zero downtime |

---

## ðŸ—ï¸ Architecture

```
â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
â”‚               Streamlit Web UI  Â·  app.py  (8 pages)             â”‚
â”‚  Dashboard â”‚ Research â”‚ Trends â”‚ Write â”‚ Review â”‚ Audience â”‚ â€¦ â”‚
â””â”€â”€â”€â”€â”€â”€â”¬â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”¬â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”¬â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”¬â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”¬â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
       â”‚           â”‚           â”‚          â”‚          â”‚
  â”Œâ”€â”€â”€â”€â–¼â”€â”€â”€â”€â” â”Œâ”€â”€â”€â”€â–¼â”€â”€â”€â”€â” â”Œâ”€â”€â”€â–¼â”€â”€â”€â”€â”€â” â”Œâ”€â”€â–¼â”€â”€â”€â”€â”€â”€â” â”Œâ–¼â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
  â”‚Research â”‚ â”‚ Trend   â”‚ â”‚ Content â”‚ â”‚Editorialâ”‚ â”‚ Sentiment â”‚
  â”‚  Agent  â”‚ â”‚  Agent  â”‚ â”‚  Agent  â”‚ â”‚  Agent  â”‚ â”‚  (local)  â”‚
  â””â”€â”€â”€â”€â”¬â”€â”€â”€â”€â”˜ â””â”€â”€â”€â”€â”¬â”€â”€â”€â”€â”˜ â””â”€â”€â”€â”¬â”€â”€â”€â”€â”€â”˜ â””â”€â”€â”¬â”€â”€â”€â”€â”€â”€â”˜ â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
       â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”´â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”´â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
                               â”‚
                    â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â–¼â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
                    â”‚    WatsonxClient     â”‚
                    â”‚  IAM token refresh   â”‚
                    â”‚  Granite chat API    â”‚
                    â”‚  Llama fallback API  â”‚
                    â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”¬â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
                               â”‚  HTTPS
                    â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â–¼â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
                    â”‚   IBM watsonx.ai     â”‚
                    â”‚   Region: au-syd     â”‚
                    â”‚   IBM Granite 3.3 8B â”‚â—„â”€â”€ primary
                    â”‚   Llama 3.3 70B      â”‚â—„â”€â”€ fallback
                    â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
```

---

## ðŸ—‚ï¸ Project Structure

```
Project-No-5/
â”‚
â”œâ”€â”€ app.py                      # Streamlit dashboard â€” 8 interactive pages
â”œâ”€â”€ config.py                   # Centralised config â€” secrets from env vars only
â”œâ”€â”€ watsonx_client.py           # IBM watsonx.ai client (Granite + Llama fallback)
â”œâ”€â”€ requirements.txt            # Pinned production dependencies
â”œâ”€â”€ Dockerfile                  # Production container (IBM Cloud Code Engine)
â”œâ”€â”€ deploy.sh                   # Linux/macOS deployment script
â”œâ”€â”€ deploy.ps1                  # Windows PowerShell deployment script
â”œâ”€â”€ .env.example                # Environment template â€” copy to .env
â”œâ”€â”€ .gitignore                  # Excludes .env, caches, venvs
â”œâ”€â”€ .dockerignore               # Excludes secrets & dev files from image
â”‚
â”œâ”€â”€ .streamlit/
â”‚   â””â”€â”€ config.toml             # Streamlit production settings (port 8080)
â”‚
â””â”€â”€ agents/
    â”œâ”€â”€ __init__.py
    â”œâ”€â”€ research_agent.py        # RSS fetch + AI synthesis + APA citations
    â”œâ”€â”€ trend_agent.py           # Keyword trends + topic suggestions + engagement
    â”œâ”€â”€ content_agent.py         # Blog draft + social snippets + guardrails
    â””â”€â”€ editorial_agent.py       # Editorial review + sentiment + approval gate
```

---

## ðŸš€ Local Quick Start

### 1. Clone

```bash
git clone https://github.com/mdivate/Project-No-5.git
cd Project-No-5
```

### 2. Virtual environment

```bash
python -m venv venv
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure credentials

```bash
cp .env.example .env
```

Edit `.env`:

```env
WATSONX_API_KEY=your_ibm_cloud_api_key
WATSONX_PROJECT_ID=280ea383-d47b-42ab-a981-b28f66296121
WATSONX_ENDPOINT=https://au-syd.ml.cloud.ibm.com
WATSONX_MODEL_ID=ibm/granite-3-3-8b-instruct
```

### 5. Run

```bash
streamlit run app.py
```

Open **[http://localhost:8501](http://localhost:8501)**

---

## â˜ï¸ IBM Cloud Deployment

The application is packaged as a Docker container and deployed to **IBM Cloud Code Engine** â€” IBM's fully managed serverless container platform. It auto-scales from 1 to 3 instances and exposes a public HTTPS URL.

### Prerequisites

| Tool | Install |
|---|---|
| IBM Cloud CLI | `winget install IBM.IBMCloudCLI` (Windows) or [Download](https://cloud.ibm.com/docs/cli) |
| Code Engine plugin | `ibmcloud plugin install code-engine` |
| Container Registry plugin | `ibmcloud plugin install container-registry` |
| Docker Desktop | [Download](https://www.docker.com/products/docker-desktop/) |

### Step-by-Step Deployment

#### Step 1 â€” Install IBM Cloud CLI plugins

```bash
ibmcloud plugin install code-engine
ibmcloud plugin install container-registry
ibmcloud plugin list
```

#### Step 2 â€” Login to IBM Cloud

```bash
ibmcloud login --apikey YOUR_IBM_API_KEY -r au-syd -g Default
```

#### Step 3 â€” Create a Code Engine project

```bash
ibmcloud ce project create --name writing-pulse-project
ibmcloud ce project select  --name writing-pulse-project
```

#### Step 4 â€” Create an IBM Container Registry namespace

```bash
ibmcloud cr login
ibmcloud cr namespace-add writing-pulse-ns
```

#### Step 5 â€” Build and push the Docker image

```bash
# Build for linux/amd64 (required for Code Engine)
docker build --platform linux/amd64 \
    -t au.icr.io/writing-pulse-ns/writing-pulse:v2.0 .

# Push to IBM Container Registry
docker push au.icr.io/writing-pulse-ns/writing-pulse:v2.0
```

#### Step 6 â€” Create the Code Engine application

```bash
ibmcloud ce application create \
    --name writing-pulse-app \
    --image au.icr.io/writing-pulse-ns/writing-pulse:v2.0 \
    --port 8080 \
    --cpu 1 \
    --memory 4G \
    --min-scale 1 \
    --max-scale 3 \
    --env WATSONX_API_KEY=your_api_key \
    --env WATSONX_PROJECT_ID=280ea383-d47b-42ab-a981-b28f66296121 \
    --env WATSONX_ENDPOINT=https://au-syd.ml.cloud.ibm.com \
    --env WATSONX_MODEL_ID=ibm/granite-3-3-8b-instruct
```

#### Step 7 â€” Get your public URL

```bash
ibmcloud ce application get --name writing-pulse-app | grep URL
```

Your app will be live at a URL like:
```
https://writing-pulse-app.xxxxxxxxx.au-syd.codeengine.appdomain.cloud
```

---

### ðŸ–±ï¸ Automated Deployment (Script)

Instead of running each step manually, use the included script:

**Windows (PowerShell):**
```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
.\deploy.ps1
```

**Linux / macOS:**
```bash
chmod +x deploy.sh
./deploy.sh
```

---

### â™»ï¸ Update an Existing Deployment

After changing code:

```bash
# Rebuild and push
docker build --platform linux/amd64 \
    -t au.icr.io/writing-pulse-ns/writing-pulse:v2.1 .
docker push au.icr.io/writing-pulse-ns/writing-pulse:v2.1

# Update the running app (zero-downtime rolling update)
ibmcloud ce application update \
    --name writing-pulse-app \
    --image au.icr.io/writing-pulse-ns/writing-pulse:v2.1
```

---

### ðŸ“Š Monitor & Manage

```bash
# View live logs
ibmcloud ce application logs --name writing-pulse-app --follow

# Check status
ibmcloud ce application get --name writing-pulse-app

# List all revisions
ibmcloud ce application revision list --application writing-pulse-app

# Scale manually
ibmcloud ce application update --name writing-pulse-app --min-scale 2

# Delete (tear down)
ibmcloud ce application delete --name writing-pulse-app
```

---

### ðŸ” Secrets Management (Production Best Practice)

Instead of passing secrets as `--env` flags (visible in CLI history), use IBM Code Engine secrets:

```bash
# Create a secret holding all credentials
ibmcloud ce secret create \
    --name watsonx-credentials \
    --from-literal WATSONX_API_KEY=your_key \
    --from-literal WATSONX_PROJECT_ID=280ea383-d47b-42ab-a981-b28f66296121 \
    --from-literal WATSONX_ENDPOINT=https://au-syd.ml.cloud.ibm.com \
    --from-literal WATSONX_MODEL_ID=ibm/granite-3-3-8b-instruct

# Reference the secret in the app
ibmcloud ce application update \
    --name writing-pulse-app \
    --env-from-secret watsonx-credentials
```

---

## âš™ï¸ Configuration

### Environment Variables

| Variable | Required | Description | Default |
|---|---|---|---|
| `WATSONX_API_KEY` | âœ… | IBM Cloud API key | â€” |
| `WATSONX_PROJECT_ID` | âœ… | watsonx.ai Project ID | `280ea383-...` |
| `WATSONX_ENDPOINT` | No | Regional API endpoint | `https://au-syd.ml.cloud.ibm.com` |
| `WATSONX_MODEL_ID` | No | Foundation model | `ibm/granite-3-3-8b-instruct` |

### IBM Cloud Regions

| Region | Endpoint | ICR Registry |
|---|---|---|
| **Sydney âœ…** | `https://au-syd.ml.cloud.ibm.com` | `au.icr.io` |
| Dallas | `https://us-south.ml.cloud.ibm.com` | `us.icr.io` |
| Frankfurt | `https://eu-de.ml.cloud.ibm.com` | `de.icr.io` |
| Tokyo | `https://jp-tok.ml.cloud.ibm.com` | `jp.icr.io` |

### Models

| Model ID | Type | Notes |
|---|---|---|
| `ibm/granite-3-3-8b-instruct` | IBM Granite | **Primary** â€” fast, IBM-native |
| `meta-llama/llama-3-3-70b-instruct` | Llama | **Automatic fallback** |

---

## ðŸ’» Tech Stack

| Layer | Technology |
|---|---|
| **Primary LLM** | IBM Granite 3.3 8B Instruct via IBM watsonx.ai |
| **Fallback LLM** | Meta Llama 3.3 70B Instruct via IBM watsonx.ai |
| **Frontend** | Streamlit 1.45 with Plotly interactive charts |
| **Container** | Docker (python:3.11-slim) |
| **Cloud Platform** | IBM Cloud Code Engine (serverless containers) |
| **Container Registry** | IBM Cloud Container Registry (ICR) |
| **Agents** | Pure Python â€” no framework overhead |
| **News Feeds** | feedparser â€” 10 public RSS feeds |
| **Sentiment** | Custom lexicon (negation + intensity-aware, zero ML deps) |
| **Voice Input** | SpeechRecognition + Google Speech API (optional) |
| **IAM Auth** | IBM IAM API Key â†’ Bearer Token (auto-refreshed) |
| **Region** | IBM Cloud Sydney (`au-syd`) |

---

## ðŸ›¡ï¸ Responsible AI

| Principle | Implementation |
|---|---|
| **No secret exposure** | Credentials in `.env` / Code Engine secrets â€” never in source or image |
| **Input guardrails** | 17 harmful content categories blocked **before** LLM call |
| **Output guardrails** | LLM responses scanned **after** generation |
| **Human-in-the-loop** | Manual approval gate â€” the AI recommends, humans decide |
| **Source citations** | Numbered citations `[1][2]` in every research summary |
| **Fact-check flags** | Editorial agent flags questionable claims explicitly |
| **Model fallback** | Granite â†’ Llama 3.3 70B automatic failover |

---

## ðŸ”Œ RSS News Sources (10 Feeds)

TechCrunch Â· Wired Â· MIT Technology Review Â· Hacker News Â· Dev.to Â· The Verge Â· Ars Technica Â· VentureBeat Â· InfoQ Â· ZDNet

---

## ðŸ¤ Contributing

1. Fork the repo
2. `git checkout -b feature/your-feature`
3. `git commit -m 'Add your feature'`
4. `git push origin feature/your-feature`
5. Open a [Pull Request](https://github.com/mdivate/Project-No-5/pulls)

---

## ðŸ“„ License

MIT License â€” see [LICENSE](LICENSE) for details.

---

## ðŸ™ Acknowledgements

- [IBM watsonx.ai](https://www.ibm.com/watsonx) â€” Foundation model platform
- [IBM Granite](https://www.ibm.com/granite) â€” Open-source enterprise LLM
- [IBM Code Engine](https://cloud.ibm.com/codeengine) â€” Serverless container platform
- [Streamlit](https://streamlit.io) â€” Python web app framework

---

<div align="center">

**âœï¸ Writing Pulse v2.0**  
Made with â¤ï¸ using IBM watsonx.ai Â· IBM Granite Â· IBM Code Engine Â· Streamlit

</div>
