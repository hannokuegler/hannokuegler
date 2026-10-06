<h1 align="center">Hi, I'm Hanno 👋</h1>

<p align="center">
  <b>AI Engineer</b> · agents, LLM systems &amp; data · Vienna 🇦🇹<br>
  <i>I build AI systems that actually run — not demos that die after a weekend.</i>
</p>

<p align="center">
  <a href="https://linkedin.com/in/hannokuegler"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:hanno.kuegler@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>
  <a href="https://instagram.com/hannokuegler"><img src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white" alt="Instagram"></a>
  <a href="https://constellate-vert.vercel.app"><img src="https://img.shields.io/badge/Live_demo-Constellate-6E40C9?style=for-the-badge&logo=vercel&logoColor=white" alt="Constellate live demo"></a>
</p>

---

## 💫 About Me

I take a vague idea, a pile of messy data and a good model — and turn the three into a working system. Most of what I build runs every day: on my own server, against my own data, with the boring parts (scheduling, tests, monitoring, backups) taken seriously.

- 🎓 **Now:** double master's — **MSc Digital Economy @ WU Vienna** + **Dipl.-Ing. Business Informatics @ TU Wien**
- 🤖 **Building:** a self-hosted multi-agent system on Claude, and local-first open-source tools pulled out of it
- 🏁 **Hackathons:** Hack-Nation 7th Global AI Hackathon 2026 with [Constellate](https://github.com/hannokuegler/constellate) · **next up: WU hackathon on Oct 24**
- 🏆 **BSc @ WU Vienna** — top 1% of my cohort (#10 of 3,067), **202 ECTS in 5 semesters**, Rector's List, specialized in **Data Science**
- 🚑 **Off-screen:** paramedic at the Austrian Red Cross since 2022 · 211 days backpacking Latin America · Spanish 🇪🇸

---

## 🆕 Latest

### 🧬 [Constellate](https://github.com/hannokuegler/constellate) — *fast help and information for people with rare diseases*

> Built in **24 hours** at the **Hack-Nation 7th Global AI Hackathon** · Challenge 05 *"AI Atlas for the World's Rare Diseases"* (Buffalo Initiative × OpenAI) · Vienna Hub · with [@Reczec](https://github.com/Reczec) and Osman

A family gets a rare diagnosis with no approved treatment — and within weeks has to become its own research team. Constellate gives them **fast, sourced answers**: which community shares the same disease mechanism, which studies and registries already exist, and what they can send to researchers this week.

- 🕸️ **Evidence-graded knowledge graph** that sorts rare diseases by **mechanism and phenotype instead of name** — built from HPO, MONDO, Orphanet, ClinVar, ClinicalTrials.gov, Europe PMC, NIH RePORTER, Open Targets & Reactome
- 🔎 Every edge carries **source, date, evidence level and counter-evidence** — nothing comes from model memory
- 🃏 **Action Cards** say what transfers from a related disease, what differs and what needs expert review — every sentence cites an edge
- 🕳️ **Honest Gap:** no supported lead? It says so and shows what was searched, instead of making something up

`Python pipeline → static JSON → Next.js on Vercel` · OpenAI at exactly three points: *Extract, Reconcile, Explain* · **[▶ Try the live demo](https://constellate-vert.vercel.app)** (no login)

### 🔐 [TU VPN](https://github.com/hannokuegler/tu_vpn) — *one click into the TU Wien network*

An unofficial macOS menu-bar app for the TU Wien VPN — built in my first week at TU, because nobody wants the Cisco client. One click to connect, **MFA once per ~5-day session**, two profiles (TU-only or full tunnel for library papers), credentials in the **macOS Keychain**, survives sleep and Wi-Fi changes. Swift/AppKit on top of [openconnect](https://www.infradead.org/openconnect/), universal binary, CI and a checksum-verified installer.

```bash
curl -fsSL https://raw.githubusercontent.com/hannokuegler/tu_vpn/main/install.sh | bash
```

---

## 🏗️ Landa — my self-hosted, agent-driven automation platform

A private system of ~20 scheduled pipelines around a Markdown knowledge base, running on my own **NixOS server**. It writes my morning report, keeps my calendar and tasks in sync, tracks my training and answers my emails.

| | |
|---|---|
| ⚙️ **Architecture** | `systemd` timers → shell runners → headless **Claude Code** (`claude -p`) with custom skills → typed Python scripts. The model decides, deterministic code executes. |
| 🧑‍💼 **Multi-agent org** | An orchestrator turns ideas into written work orders for role agents (engineering, operations, admin). A **blind reviewer** sees only the order and the test commands — never the builder's report — and has to verify the result before it counts. |
| 🔀 **Dev workflow** | Every code change: branch → tests → pull request → review → merge → server deploy. |
| 📊 **Data layer** | Garmin sync every 30 min into SQLite, iCloud **CalDAV**, IMAP mail, local **Whisper** transcription of voice memos. |
| 📬 **Mail assistant** | I email a question from my phone; an agent searches notes, mail and training data and replies with sources — on an **open-weight model**, cheap enough to poll every 2 minutes. |
| 🛡️ **Ops** | Nightly **restic** backups, a self-healing network watchdog (reconnect → USB reset → reboot), automated check of every public hostname against certificate-transparency logs. |

---

## 📦 Open Source

Three tools pulled out of Landa, rebuilt from scratch and released. Same rules for all of them: **local-first** (your data never leaves your machine), **one `pip install`**, and a **zero-config `demo` command** — see it working in ten seconds, no account, no login.

| Tool | What it does | Stack |
|---|---|---|
| ⌚ **[garmindeck](https://github.com/hannokuegler/garmindeck)** | Your Garmin data in a beautiful local dashboard — race predictions, HRV, readiness. No cloud, no subscription | Python · FastAPI · SQLite |
| 🗣️ **[blurt](https://github.com/hannokuegler/blurt)** | A local daemon that splits one rambling voice memo into tasks, notes and ideas — and routes each to its own destination | Python · Whisper · Ollama |
| 📬 **[mailctx](https://github.com/hannokuegler/mailctx)** | Any IMAP inbox as clean, token-cheap Markdown (59–98% fewer tokens), with an MCP server for Claude. Reads and drafts — never sends | Python · IMAP · MCP |

<details>
<summary><b>Install & details</b></summary>

<br>

**⌚ garmindeck** syncs everything your watch ever recorded into a plain SQLite file and serves it as an interactive dashboard on `localhost` — sleep phases, resting HR, overnight HRV, body battery, training load, race predictions (5K → marathon), training readiness and VO₂max. Works fully offline, incremental and resumable, MFA supported.

```bash
pip install git+https://github.com/hannokuegler/garmindeck && garmindeck demo
```

**🗣️ blurt** watches a folder, transcribes locally and splits one memo into multiple intents: the TODO goes to your task file, the journal bit to today's note, the idea to a webhook. Declarative `routing.yaml`, plus an enforced paranoid mode that makes "provably offline" a guarantee.

```bash
pip install git+https://github.com/hannokuegler/blurt && blurt demo
```

**📬 mailctx** strips `<style>` tags, nested quotes and tracking pixels and emits bounded Markdown, so Claude Desktop can answer *"what did I miss this week?"* against any mailbox. Typed transient-vs-auth error handling with retry, multi-account isolation — and a hard safety boundary: it can never send or delete.

```bash
pip install "mailctx[mcp] @ git+https://github.com/hannokuegler/mailctx" && mailctx demo
```

</details>

---

## 🔬 Research & Projects

| Project | What it is |
|---|---|
| 🎓 **Bachelor's thesis** — *Why Europe's power grid runs late* | NLP & clustering over the full **ENTSO-E Ten-Year Network Development Plan** — **967 transmission projects in 40 countries**. TF-IDF + embeddings → t-SNE → K-Means (vs. DBSCAN, GMM), with LLMs turning clusters into narratives. Finding: *delayed* projects stall on permitting, *rescheduled* ones on technical integration. WU **IDEaS Institute**. |
| 🛰️ **floodrisk** — *flood risk for climate-resilient cities* | Multi-month project with the Austrian startup **[Infrared City](https://infrared.city)**: replacing costly fluid-dynamics simulations with ML on Sentinel imagery, elevation models, OpenStreetMap and precipitation data — built as a module for their planning platform. |
| ♟️ **[Chess-Prediction](https://github.com/hannokuegler/Chess-Prediction)** | Predicting game outcomes from Stockfish evaluations, ELO, ACPL and time features — Random Forests, logistic regression, PCA and calibration in R. |
| 📰 **dailybot** | News from 8+ sources, filtered by topic, de-duplicated, summarized by an LLM and mailed as a daily briefing with live market data. |
| 🌎 **Gringo Trail** | My 211-day Latin-America trip run like a data product: an Obsidian vault with custom Claude commands that turned voice memos and notes into a searchable journal across 13 countries. |
| 📄 **[roast_my_cv](https://github.com/hannokuegler/roast_my_cv)** | An LLM app that roasts your CV — and then improves it. Built for WU's *Applications of Data Science: LLMs*. |

---

## 🌱 Currently

- 🎓 First semester of the **WU + TU double master's**
- 🏁 Getting ready for the **WU hackathon on Oct 24** — round two after Hack-Nation
- 🧩 Hardening Landa: more tests, better observability, cheaper models where they're good enough
- 🤝 Open to working on **AI agents, health-tech, data science, energy & sustainability** — and always up for a hackathon team

---

## 🛠️ Tech Stack

**AI & data**<br>
![Claude](https://img.shields.io/badge/Claude-D97757?style=for-the-badge&logo=anthropic&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)
![MCP](https://img.shields.io/badge/MCP-000000?style=for-the-badge&logo=modelcontextprotocol&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-000000?style=for-the-badge&logo=ollama&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Hugging_Face-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)
![pandas](https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)

**Languages & frameworks**<br>
![Python](https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Swift](https://img.shields.io/badge/Swift-F54A2A?style=for-the-badge&logo=swift&logoColor=white)
![R](https://img.shields.io/badge/R-276DC3?style=for-the-badge&logo=r&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi&logoColor=white)
![LaTeX](https://img.shields.io/badge/LaTeX-008080?style=for-the-badge&logo=latex&logoColor=white)

**Infrastructure**<br>
![NixOS](https://img.shields.io/badge/NixOS-5277C3?style=for-the-badge&logo=nixos&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Docker](https://img.shields.io/badge/Docker-0db7ed?style=for-the-badge&logo=docker&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-07405e?style=for-the-badge&logo=sqlite&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05033?style=for-the-badge&logo=git&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Obsidian](https://img.shields.io/badge/Obsidian-483699?style=for-the-badge&logo=obsidian&logoColor=white)

---

<p align="center"><sub>⚡ Grew up on a farm raising chickens 🐔 — now I raise models and datasets. 195 cm, runs and powerlifts, statistically unlikely to fit into airplane legroom.</sub></p>
