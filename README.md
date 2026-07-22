<h1 align="center">Hi, I'm Hanno 👋</h1>

<p align="center">
  <b>Data Scientist &amp; AI / LLM Builder</b> · Vienna 🇦🇹 → currently roaming Latin America 🌎<br>
  <i>Turning messy data and large language models into things that actually do something.</i>
</p>

<p align="center">
  <a href="https://linkedin.com/in/hannokuegler"><img src="https://img.shields.io/badge/LinkedIn-%230077B5.svg?logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="https://instagram.com/hannokuegler"><img src="https://img.shields.io/badge/Instagram-%23E4405F.svg?logo=Instagram&logoColor=white" alt="Instagram"></a>
  <a href="mailto:hanno.kuegler@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?logo=gmail&logoColor=white" alt="Email"></a>
  <img src="https://komarev.com/ghpvc/?username=hannokuegler&label=Profile%20views&color=0e75b6&style=flat" alt="views">
</p>

---

## 💫 About Me

I'm a **business & data science graduate of WU Vienna** who fell hard for AI — and now builds with it every single day. I love taking a vague idea, a pile of unstructured data, and a good LLM, and turning the three into a working system.

- 🎓 **BSc Business, Economics & Social Sciences @ WU Vienna** — *graduated Feb 2026*
- 🏆 **Top 1% of my cohort:** #13 of 3,067 in the Academic Progress Ranking · **Rector's List (WS 2025)**
- 📈 **204 ECTS in 5 semesters** — finished a semester early
- 🧠 Triple specialization: **Data Science**, **Responsible Management of Information Systems** & **Production Management** *(final grade: Sehr Gut)*
- 🚀 Next up: **Dipl.-Ing. (TU) + MSc (WU)** — going deeper into AI, data & systems
- 🚑 4 years of **emergency leadership** at the Austrian Red Cross
- 🌎 Currently traveling **Latin America** and learning **Spanish** 🇪🇸 (voseo, Colombia-style)

---

## 🤖 My Thing: Building with LLMs

I'm genuinely obsessed with large language models — not just using them, but **building real, personal systems around them**. Most of my AI work isn't a demo that dies after a weekend; it's stuff I use in my own life, daily.

The centerpiece is a **personal AI assistant ecosystem I built on top of Claude** — a set of specialized agents/skills, each with its own memory, data and personality, that automate and supercharge different parts of my life:

| Agent | What it does |
|-------|--------------|
| 🇪🇸 **Marco** | My Spanish tutor & vocab trainer — runs drills, dialogues and spaced-repetition vocab tests (Leitner system), tracks weak spots and progress |
| 🏋️ **Coach** | A fitness & recovery coach that reads my **Garmin** data, knows my athlete profile, and gives data-driven, no-BS training/sleep/recovery calls |
| 🛋️ **Freud** | A dream interpreter running psychoanalytic sessions via free association, building a personal symbol lexicon & dream profile over time |
| 🗣️ **Sokrates** | A daily debate & argumentation sparring partner with scorecards, drills and a fact-check loop |
| 💼 **Business sparring** | A project manager, a brutally honest CFO and an entrepreneur sparring partner for ideas, finances & strategy |

---

## 📦 Open Source

Three tools I pulled out of that private stack, rebuilt from scratch and released. Same three rules for all of them: **local-first** (your data never leaves your machine), **one `pip install`**, and a **zero-config `demo` command** — you see the thing working in ten seconds, no account, no login, no signup.

| Tool | One line | Stack |
|---|---|---|
| ⌚ **[garmindeck](https://github.com/hannokuegler/garmindeck)** | Your Garmin data in a beautiful local dashboard — no cloud, no subscription | Python · FastAPI · SQLite |
| 🗣️ **[blurt](https://github.com/hannokuegler/blurt)** | A voice memo goes in, structured data comes out in three different systems | Python · Whisper · Ollama |
| 📬 **[mailctx](https://github.com/hannokuegler/mailctx)** | Any IMAP inbox as clean, token-cheap Markdown — with an MCP server for Claude | Python · IMAP · MCP |

### ⌚ garmindeck — *your watch data, without the subscription*

You already paid for the watch — then Garmin sold you *Connect+* on top of it. `garmindeck` syncs everything your device ever recorded into a plain **SQLite file on your own disk** and serves it as a fast, interactive dashboard on `localhost`. Steps, sleep phases, resting HR, overnight **HRV**, body battery vs. stress, training load — plus the numbers Garmin buries fifteen taps deep: **race predictions (5K → marathon), training readiness and VO₂max**. Works fully **offline, forever**, even if your account disappears. macOS · Windows · Linux, incremental & resumable sync, MFA supported, `export` to CSV. It's also the data layer my Claude **Coach** agent reads from.

```bash
pip install garmindeck && garmindeck demo   # synthetic data, no login needed
```

### 🗣️ blurt — *voice memos that route themselves*

There are a hundred Whisper wrappers; none of them are a **daemon**. `blurt` watches a folder, transcribes locally, and — the actual point — splits **one rambling memo into multiple intents** and routes each to a **different destination**: the TODO gets appended to your task file, the journal bit written to today's note, the idea POSTed to a webhook. All declarative in `routing.yaml`, zero clicks, and with an **enforced paranoid mode** that makes "provably offline" a guarantee rather than a promise. Speak into your watch on a hike, find structured tickets in your repo when you're back.

```bash
pip install blurt && blurt demo
```

### 📬 mailctx — *the missing IMAP MCP server*

LLMs drown in `<style>` tags, nested quotes and tracking pixels. `mailctx` is a provider-agnostic IMAP engine that strips all of it and emits bounded, token-optimized **Markdown** — **59–98% fewer tokens** on the bundled corpus. Ships an **MCP server**, so Claude Desktop can answer *"what did I miss this week?"* or *"draft a reply to my landlord"* against any mailbox. Hardened for real life: typed transient-vs-auth error handling with retry (born from Gmail EOF drops on travel WLAN), multi-account isolation. And a hard safety boundary — **it can read and draft, it can never send or delete.** For an agent touching your inbox, that constraint *is* the feature.

```bash
pip install "mailctx[mcp]" && mailctx demo
```

---

## 🛠️ More Projects & Research

### 🌎 Gringo Trail — *Automated travel & journaling system*
My Latin-America trip, run like a data product. An Obsidian vault wired up with **custom Claude commands** that turn rough notes into structured travel journals, track the route, and keep everything searchable — automated documentation of a whole continent of travel.

### 📰 dailybot — *Personalized daily digest engine*
An expert-level Python pipeline that fetches news from 8+ live sources (ORF, Tagesschau, BBC, NYT, …), filters by my topics (tech, finance, energy, emergency/rescue, logistics), de-duplicates headlines, pulls **live market data**, lets an **LLM write the summaries**, and emails me a crisp daily briefing — fully config-driven and secrets-safe.

### 🏋️ fitness-coach — *Garmin → AI coaching loop*
The private predecessor of [garmindeck](https://github.com/hannokuegler/garmindeck): pulls my Garmin Connect data daily, keeps a strength-training database, and feeds both to my Claude **Coach** agent for personalized training & recovery calls.

### 📄 roast_my_cv — *An LLM that roasts your CV*
A playful but pointed LLM app (built for WU's *Applications of Data Science: LLMs* course) that reads a CV and roasts — then improves — it.

### ♟️ Chess-Prediction — *Predicting the unpredictable*
Predicting chess game outcomes from Stockfish evaluations, ELO, ACPL and time features — Random Forests, Logistic Regression, PCA & calibration plots in R.

### 🛰️ floodrisk — *Geospatial flood-risk modelling for climate-resilient cities*
A large, multi-month team project from WU Vienna's **Data Science Lab**, built in **real-world collaboration with [Infrared City](https://infrared.city)** — an Austrian startup making AI-powered environmental simulation tools — and supervised by **Univ.-Prof. Dr. Kavita Surana** alongside Infrared City data coaches.

The goal: replace slow, expensive fluid-dynamics flood simulations with a **scalable, data-centric ML approach** that can flag flood-prone urban areas from open data — and ship it as a flood-risk module for the company's planning platform.

- 🌍 **Fused heterogeneous geospatial layers:** Copernicus/Sentinel **satellite imagery**, **digital elevation models (DEMs)**, **OpenStreetMap** vector data and **historical precipitation** records
- 🧪 **Surface classification** (impervious surfaces vs. vegetation) and **spatial risk modelling** with Random Forests, heavy feature engineering & GIS techniques
- 🏙️ Designed to **generalize across cities** with different geographic and demographic profiles
- 🔁 Delivered as a **modular, reproducible end-to-end data pipeline** built to plug straight into Infrared City's AI simulation environment for climate-resilient urban planning

### 🎓 Bachelor's Thesis — *Why Europe's Power Grid Runs Late*
**"Delay Drivers in European Energy Infrastructure: An NLP & Clustering Study"** — WU Vienna, **IDEaS Institute** (Institute for Data, Energy & Sustainability), supervised by **Univ.-Prof. Dr. Kavita Surana** & **Mag. Damiano Alessi**.

Europe can't hit its climate targets if the grid that carries the renewables keeps slipping. So I asked a data question to a very human problem: **why do transmission projects get delayed — and is it the same reason everywhere?** To answer it, I turned years of messy, free-text project reports into structure.

- 📊 **Scope:** the full **ENTSO-E Ten-Year Network Development Plan** — **967 transmission investments across 40 countries (2010–2026)**
- 🔤 **NLP pipeline:** preprocessing → **TF-IDF** + contextual **text embeddings** → **t-SNE** dimensionality reduction
- 🧩 **Unsupervised clustering** with **K-Means**, rigorously benchmarked against **DBSCAN** and **Gaussian Mixture Models**
- 🤖 **LLM-in-the-loop (GPT, LLaMA):** large language models read the unstructured delay-driver texts and turn raw clusters into human-readable narratives
- 💡 **Key finding:** a clean, data-driven split between **Delayed** projects (stuck on *regulatory & permitting* barriers) and **Rescheduled** ones (*technical & renewables-integration* challenges) — a distinction with direct **policy implications for the EU energy transition**

*…plus a long tail of smaller experiments: face recognition, a smart alarm clock, a Morse-code encoder ("Mössi Morser") with wireless transmission, and more.*

---

## 🌱 Currently

- 🔭 Going deeper into **LLMs, agents & AI-driven analytics**
- 📦 Shipping **local-first open source** — [garmindeck](https://github.com/hannokuegler/garmindeck), [blurt](https://github.com/hannokuegler/blurt) & [mailctx](https://github.com/hannokuegler/mailctx) (issues and stars very welcome ⭐)
- 🧩 Building & refining my personal Claude agent ecosystem
- 🇪🇸 Learning **Spanish** while traveling **Latin America**
- 🤝 Open to collaborating on **AI/LLM, data science, energy & sustainability** projects

---

## 💻 Tech Stack

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![R](https://img.shields.io/badge/r-%23276DC3.svg?style=for-the-badge&logo=r&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)
![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white)
![LaTeX](https://img.shields.io/badge/latex-%23008080.svg?style=for-the-badge&logo=latex&logoColor=white)
![Markdown](https://img.shields.io/badge/markdown-%23000000.svg?style=for-the-badge&logo=markdown&logoColor=white)

![Anthropic](https://img.shields.io/badge/Claude-D97757?style=for-the-badge&logo=anthropic&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)
![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-FFD21E?style=for-the-badge)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)
![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi&logoColor=white)
![MCP](https://img.shields.io/badge/MCP-000000?style=for-the-badge&logo=modelcontextprotocol&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-000000?style=for-the-badge&logo=ollama&logoColor=white)

![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![SQLite](https://img.shields.io/badge/sqlite-%2307405e.svg?style=for-the-badge&logo=sqlite&logoColor=white)
![Obsidian](https://img.shields.io/badge/Obsidian-%23483699.svg?style=for-the-badge&logo=obsidian&logoColor=white)
![Raspberry Pi](https://img.shields.io/badge/-Raspberry_Pi-C51A4A?style=for-the-badge&logo=Raspberry-Pi)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)

---

### ✍️ Random Dev Quote
![](https://quotes-github-readme.vercel.app/api?type=horizontal&theme=radical)

---

> ⚡ **Fun fact:** I grew up on a farm raising chickens 🐔 — now I raise models & datasets. At 195 cm I run and powerlift, and remain statistically unlikely to fit into airplane legroom (a real problem on the Gringo Trail).
