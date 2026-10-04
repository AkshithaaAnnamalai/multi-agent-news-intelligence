# Multi-Agent Personalized News Intelligence and Briefing System

## Overview

The **Multi-Agent Personalized News Intelligence and Briefing System** is an AI-based news application that collects, analyzes, selects, verifies, and presents personalized news articles based on the user's interests.

The system uses multiple specialized AI agents and a locally hosted **Qwen 2.5 3B** model through **Ollama** to create a personalized daily news briefing.

## Key Features

* 📰 Collects current news from Google News RSS
* 🎯 Personalizes news according to user interests
* 🧠 Uses multiple specialized AI agents
* 📊 Analyzes and ranks news articles by relevance
* 🔍 Screens articles to determine whether additional verification is required
* ✍️ Generates concise news briefings
* 🔔 Sends a Windows desktop notification when the briefing is ready
* 🔄 Learns from user interactions such as opening, liking, and disliking articles
* 🌐 Provides an interactive HTML/CSS/JavaScript news dashboard

## Multi-Agent Architecture

The system consists of the following agents:

1. **News Researcher Agent** – Collects current news from Google News RSS.
2. **News Analyst Agent** – Analyzes the relevance of collected articles.
3. **Article Selection Agent** – Selects the most relevant articles while maintaining topic diversity.
4. **Verification Agent** – Screens headlines and identifies articles that may require additional verification.
5. **Briefing Writer Agent** – Generates concise personalized briefing content.
6. **Notification Agent** – Sends a Windows desktop notification when the briefing is ready.

### Personalization

The system maintains a persistent user interest profile.

User interactions affect topic scores:

* Article opened → **+0.2**
* Article liked → **+0.5**
* Article disliked → **−0.4**

The learned interest profile is stored in:

```text
user_interest_profile.json
```

The updated interests are used during subsequent news collection and article selection.

## Technologies Used

* Python
* Jupyter Notebook
* Ollama
* Qwen 2.5 3B
* LangChain
* Requests
* BeautifulSoup
* Google News RSS
* HTML
* CSS
* JavaScript
* Plyer
* JSON

## System Workflow

```text
User Interests
      ↓
User Interest Model
      ↓
News Researcher Agent
      ↓
News Analyst Agent
      ↓
Article Selection Agent
      ↓
Verification Agent
      ↓
Briefing Writer Agent
      ↓
Personalized News Briefing
      ↓
Dashboard + Desktop Notification
      ↓
User Feedback
      ↓
Updated Interest Profile
      ↓
Next Briefing
```

## Requirements

* Python 3.10 or later
* Jupyter Notebook / JupyterLab
* Ollama
* Qwen 2.5 3B model

Install the required Python packages:

```bash
pip install langchain langgraph langchain-ollama requests beautifulsoup4 plyer
```

Install the Qwen model using Ollama:

```bash
ollama pull qwen2.5:3b
```

## How to Run

1. Install Python and Jupyter Notebook/JupyterLab.
2. Install Ollama.
3. Download the Qwen 2.5 3B model:

```bash
ollama pull qwen2.5:3b
```

4. Install the required Python packages.
5. Open the project `.ipynb` file in Jupyter.
6. Make sure Ollama is running.
7. Run the notebook cells in order.
8. The system collects and processes current news.
9. The final personalized briefing is displayed through the dashboard.
10. A Windows desktop notification is generated when the briefing is ready.

## Project Structure

```text
multi-agent-news-intelligence/
│
├── Multi-Agent Personalized News Intelligence and Briefing System.ipynb
├── user_interest_profile.json
└── README.md
```

## Limitations

The Verification Agent currently **screens articles to determine whether additional verification may be required**. It does not independently fact-check an article by retrieving and comparing information from a second source.

The system also depends on the availability of Google News RSS and the local Ollama model.

**Academic Year:** 2026–2027

