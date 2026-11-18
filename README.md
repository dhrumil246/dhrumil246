<div align="center">

# Dhrumil Amin

**Full-Stack & AI Engineer** — I build the systems that sit between a model and a real user.

<sub>Real-time voice AI &nbsp;·&nbsp; Agentic ML systems &nbsp;·&nbsp; Production web platforms</sub>

<br/>

<a href="https://dhrumilamin.me"><img src="https://img.shields.io/badge/Portfolio-161B22?style=for-the-badge&logo=googlechrome&logoColor=4285F4" alt="Portfolio" /></a>
<a href="https://linkedin.com/in/dhrumil-amin-47429a260"><img src="https://img.shields.io/badge/LinkedIn-161B22?style=for-the-badge&logo=linkedin&logoColor=0A66C2" alt="LinkedIn" /></a>
<a href="mailto:dhrumilamin.645@gmail.com"><img src="https://img.shields.io/badge/Email-161B22?style=for-the-badge&logo=gmail&logoColor=EA4335" alt="Email" /></a>
<a href="https://leetcode.com/u/Dhrumil_amin/"><img src="https://img.shields.io/badge/LeetCode-161B22?style=for-the-badge&logo=leetcode&logoColor=FFA116" alt="LeetCode" /></a>

<br/><br/>

<table>
<tr>
<td align="center" width="25%"><b>🥈 2× Runners-up</b><br/><sub>IBM Bob AI Hackathon 2026<br/>InnoTech 3.0</sub></td>
<td align="center" width="25%"><b>~190 ms</b><br/><sub>voice start latency, benchmarked<br/>in Hindi · English · Gujarati</sub></td>
<td align="center" width="25%"><b>0.923 macro-F1</b><br/><sub>custom CNN, 9 wafer<br/>defect classes</sub></td>
<td align="center" width="25%"><b>6 roles · 1 API</b><br/><sub>multi-tenant platform<br/>shipped in production</sub></td>
</tr>
</table>

</div>

---

### `$ whoami`

I'm a third-year B.Tech Computer Science student at **CHARUSAT** (CGPA 8.44/10) who likes the unglamorous part of AI: making a model behave inside a product. That means streaming audio over a phone line without dead air, refusing to answer when the input is garbage, and citing evidence instead of sounding confident.

My work runs on two tracks that keep merging:

- **AI systems** — PyTorch models trained from scratch, agent tool servers over the **Model Context Protocol**, real-time speech pipelines (STT → LLM → TTS) in **Python + FastAPI**, and the evaluation harnesses that tell me whether any of it actually works.
- **Full-stack platforms** — TypeScript, Next.js, Node.js, relational schemas, Socket.IO / SSE real-time layers, and deployment I do myself: Docker, NGINX, PM2 on a plain VPS.

**How I work:** measure before building, write down the negative results, and ship the guardrail alongside the feature.

> Open to **AI engineering** and **full-stack** internships.

---

### Featured Work

<table>
<tr>
<td valign="top" width="50%">

#### 🎙️ Vaani — वाणी
<sub><code>Real-time voice AI</code> &nbsp;·&nbsp; <code>Lead developer, voice service</code> &nbsp;·&nbsp; <code>Top 7, Chaos2Commit</code></sub>

An AI sales agent that finds leads, enriches and scores them, then **places real outbound phone calls** where an AI voice agent holds a live conversation in **Gujarati, Hindi or English** — switching mid-call when the prospect does, transcribing every turn and writing the outcome back to the pipeline.

- Built the call pipeline: **Twilio Media Streams → Sarvam streaming STT → LLM → Sarvam TTS**, μ-law 8 kHz end to end with zero resampling
- Benchmarked before building: **~716 ms** STT finalisation (p50) and **~190 ms** TTS start across 108 phone-codec utterances in 3 languages
- **Honest barge-in** — when the caller interrupts, only audio they actually heard enters the model's context
- Fixed issues only real calls expose: language-specific silence windows (500 ms EN / 800 ms Indic) and per-language model routing for fluent Hindi
- **Live human handoff mid-call** — the agent answers in the caller's language and rings a teammate with a spoken summary. Mentors asked for it at evaluation, and it was working on real calls the next morning
- **970+ automated tests** and dozens of real phone calls; Next.js 16 app + always-on FastAPI worker on a shared Supabase Postgres contract, plus an Android / iOS app

<sub><code>Python</code> <code>FastAPI</code> <code>WebSockets</code> <code>Twilio</code> <code>Sarvam AI</code> <code>Next.js 16</code> <code>Supabase</code></sub><br/>
<sub><a href="https://github.com/dhrumil246/Vaani-AI">Code</a> &nbsp;·&nbsp; team of 3</sub>

</td>
<td valign="top" width="50%">

#### 🔬 YieldGuard
<sub><code>Agentic ML</code> &nbsp;·&nbsp; <code>🥈 Runners-up, IBM Bob AI Hackathon 2026</code> &nbsp;·&nbsp; <code>🥈 Runners-up, InnoTech 3.0 (Development)</code></sub>

An agentic root-cause assistant for **semiconductor wafer-yield failures**. It classifies wafer-map defects, scores sensor anomalies, and ranks root causes **with cited evidence** — and refuses to answer when the input is invalid or too novel.

- Trained a **ResNet-style CNN from scratch** (615K params) on WM-811K: **0.923 macro-F1**, up from 0.858 by fixing class-imbalance handling and adding 8-view symmetry TTA
- Built a **14-tool MCP server** orchestrated by IBM Bob; hypotheses without cited evidence are stripped server-side. Agent scored **16/18** on our end-to-end eval suite
- **Conformal prediction** on CMP process data raised excursion detection **34.7% → 93.9%** at 94% measured coverage, with an abstention gate
- Input-validation layer rejects **8/8 adversarial inputs** — added after the model labelled an empty array with 100% confidence
- Ran the model over **all 811,457 wafers** in WM-811K, most never labelled by a human, and found it confidently labels unseen patterns (e.g. tester-induced stripes) — now building out-of-distribution "I haven't seen this" detection
- Rejected two approaches with evidence: a ViT (0.698 F1 at 3× the params) and self-training on unlabelled wafers (pseudo-labels only reliable on classes it already handled)

<sub><code>PyTorch</code> <code>scikit-learn</code> <code>MCP</code> <code>IBM Bob</code> <code>Gemini</code> <code>FastAPI</code> <code>Next.js</code></sub><br/>
<sub><a href="https://github.com/Parva-28/bob-ai-hackathon-DuckDuckGo">Code</a> &nbsp;·&nbsp; team of 4 · ~80% of commits</sub>

</td>
</tr>
<tr>
<td valign="top" width="50%">

#### 🌾 EGE Agritech
<sub><code>Production</code> &nbsp;·&nbsp; <code>Internship · MCT IT Solutions</code></sub>

Multi-tenant agricultural supply-chain platform. Turborepo monorepo with a Node/Express/Prisma/MySQL API serving **6 user roles** across 6 React + Vite apps and a React Native client — harvest-to-delivery lifecycle, quality control, shortfall resolution and automated wallet payouts, with Socket.IO pushing live state to every role. Deployed to a VPS behind NGINX with role-based subdomains.

<sub><code>Node.js</code> <code>Express</code> <code>Prisma</code> <code>MySQL</code> <code>Redis</code> <code>Turborepo</code> <code>Socket.IO</code> <code>Docker</code></sub>

</td>
<td valign="top" width="50%">

#### ⚡ QuizzX
<sub><code>Real-time backend</code></sub>

Classroom quiz backend built for **100+ concurrent participants** — live leaderboards, team competitions and academic-integrity proctoring. Dual SSE streams keep leaderboard updates **under 100 ms**; Redis caching falls back to in-memory automatically. JWT auth, rate limiting, versioned REST endpoints, tab-switch / fullscreen anti-cheat.

<sub><code>Express</code> <code>PostgreSQL (Neon)</code> <code>Redis</code> <code>SSE</code></sub><br/>
<sub><a href="https://quizzx.tech">quizzx.tech</a></sub>

</td>
</tr>
</table>

<details>
<summary><b>More projects</b></summary>
<br/>

**AI Resume Analyzer** — Parses a resume and returns *structured* feedback (skill coverage, experience alignment, ATS compatibility) as schema-shaped output the React UI renders field by field. `React` `Node.js` `LLM pipeline` — [Code](https://github.com/dhrumil246/AI-Resume-Analyzer) · [Live](https://ai-resume-analyzer-pnui.onrender.com)

**Smart Business Document Generator** — OCR digitises scanned paperwork, an AI layer extracts the fields that matter, and the app emits quotations, minutes of meeting and work orders as PDFs. `React` `OCR` `AI summarisation` — [Code](https://github.com/dhrumil246/quotmatex)

**GlobeTrotter** — TypeScript travel planner; finalist at the National-Level ODOO Hackathon 2025. — [Code](https://github.com/dhrumil246/GlobeTrotter_Odoo)

**C++ Data Analyzer** — CLI for CSV datasets: descriptive statistics, frequency and correlation analysis, filtering and export. — [Code](https://github.com/dhrumil246/CPP-DataAnalyzer)

**GSAP Animation Showcase** — Timeline and scroll-triggered motion work, built for performance. — [Live](https://gsapprojectdhrumil.netlify.app)

**IEEE CHARUSAT SB Website** — Official student branch site in Next.js with animated UI and performance tuning.

</details>

---

### Toolbox

<table>
<tr>
<td><b>AI / ML</b></td>
<td>
<img src="https://img.shields.io/badge/PyTorch-161B22?style=flat-square&logo=pytorch&logoColor=EE4C2C" />
<img src="https://img.shields.io/badge/scikit--learn-161B22?style=flat-square&logo=scikitlearn&logoColor=F7931E" />
<img src="https://img.shields.io/badge/NumPy-161B22?style=flat-square&logo=numpy&logoColor=4DABCF" />
<img src="https://img.shields.io/badge/pandas-161B22?style=flat-square&logo=pandas&logoColor=E70488" />
<img src="https://img.shields.io/badge/MCP-161B22?style=flat-square&logo=anthropic&logoColor=D97757" />
<img src="https://img.shields.io/badge/Gemini-161B22?style=flat-square&logo=googlegemini&logoColor=8E75B2" />
<img src="https://img.shields.io/badge/IBM_watsonx-161B22?style=flat-square&logo=ibm&logoColor=0F62FE" />
<img src="https://img.shields.io/badge/Sarvam_AI_(STT%2FTTS)-161B22?style=flat-square&logo=soundcharts&logoColor=FF6B6B" />
</td>
</tr>
<tr>
<td><b>Languages</b></td>
<td>
<img src="https://img.shields.io/badge/Python-161B22?style=flat-square&logo=python&logoColor=3776AB" />
<img src="https://img.shields.io/badge/TypeScript-161B22?style=flat-square&logo=typescript&logoColor=3178C6" />
<img src="https://img.shields.io/badge/JavaScript-161B22?style=flat-square&logo=javascript&logoColor=F7DF1E" />
<img src="https://img.shields.io/badge/C++-161B22?style=flat-square&logo=cplusplus&logoColor=00599C" />
<img src="https://img.shields.io/badge/Java-161B22?style=flat-square&logo=openjdk&logoColor=F89820" />
<img src="https://img.shields.io/badge/SQL-161B22?style=flat-square&logo=mysql&logoColor=4479A1" />
</td>
</tr>
<tr>
<td><b>Backend</b></td>
<td>
<img src="https://img.shields.io/badge/FastAPI-161B22?style=flat-square&logo=fastapi&logoColor=009688" />
<img src="https://img.shields.io/badge/Node.js-161B22?style=flat-square&logo=nodedotjs&logoColor=5FA04E" />
<img src="https://img.shields.io/badge/Express-161B22?style=flat-square&logo=express&logoColor=white" />
<img src="https://img.shields.io/badge/WebSockets-161B22?style=flat-square&logo=socketdotio&logoColor=white" />
<img src="https://img.shields.io/badge/Twilio-161B22?style=flat-square&logo=twilio&logoColor=F22F46" />
<img src="https://img.shields.io/badge/Prisma-161B22?style=flat-square&logo=prisma&logoColor=white" />
<img src="https://img.shields.io/badge/JWT-161B22?style=flat-square&logo=jsonwebtokens&logoColor=D63AFF" />
</td>
</tr>
<tr>
<td><b>Frontend</b></td>
<td>
<img src="https://img.shields.io/badge/Next.js-161B22?style=flat-square&logo=nextdotjs&logoColor=white" />
<img src="https://img.shields.io/badge/React-161B22?style=flat-square&logo=react&logoColor=61DAFB" />
<img src="https://img.shields.io/badge/React_Native-161B22?style=flat-square&logo=react&logoColor=61DAFB" />
<img src="https://img.shields.io/badge/Tailwind_CSS-161B22?style=flat-square&logo=tailwindcss&logoColor=06B6D4" />
<img src="https://img.shields.io/badge/Vite-161B22?style=flat-square&logo=vite&logoColor=646CFF" />
<img src="https://img.shields.io/badge/GSAP-161B22?style=flat-square&logo=greensock&logoColor=88CE02" />
</td>
</tr>
<tr>
<td><b>Data</b></td>
<td>
<img src="https://img.shields.io/badge/PostgreSQL-161B22?style=flat-square&logo=postgresql&logoColor=4169E1" />
<img src="https://img.shields.io/badge/Supabase-161B22?style=flat-square&logo=supabase&logoColor=3FCF8E" />
<img src="https://img.shields.io/badge/MySQL-161B22?style=flat-square&logo=mysql&logoColor=4479A1" />
<img src="https://img.shields.io/badge/MongoDB-161B22?style=flat-square&logo=mongodb&logoColor=47A248" />
<img src="https://img.shields.io/badge/Redis-161B22?style=flat-square&logo=redis&logoColor=FF4438" />
</td>
</tr>
<tr>
<td><b>Infra</b></td>
<td>
<img src="https://img.shields.io/badge/Docker-161B22?style=flat-square&logo=docker&logoColor=2496ED" />
<img src="https://img.shields.io/badge/NGINX-161B22?style=flat-square&logo=nginx&logoColor=009639" />
<img src="https://img.shields.io/badge/PM2-161B22?style=flat-square&logo=pm2&logoColor=white" />
<img src="https://img.shields.io/badge/Turborepo-161B22?style=flat-square&logo=turborepo&logoColor=EF4444" />
<img src="https://img.shields.io/badge/Git-161B22?style=flat-square&logo=git&logoColor=F05032" />
</td>
</tr>
</table>

---

### Experience

<table>
<tr>
<td valign="top"><b>Full-Stack Developer Intern</b><br/><sub>MCT IT Solutions · Ahmedabad</sub></td>
<td valign="top" align="right"><sub>May 2026 – Jun 2026</sub></td>
</tr>
<tr>
<td colspan="2"><sub>Built and deployed EGE Agritech end to end — API design, real-time layer, and production infrastructure on a VPS with PM2, NGINX, and Dockerised MySQL &amp; Redis.</sub></td>
</tr>
<tr><td colspan="2"></td></tr>
<tr>
<td valign="top"><b>Webmaster</b><br/><sub>IEEE CHARUSAT Student Branch</sub></td>
<td valign="top" align="right"><sub>2025 – 2026</sub></td>
</tr>
<tr>
<td colspan="2"><sub>Designed, deployed and maintained the official student branch website in Next.js, owning content updates and releases through the term.</sub></td>
</tr>
</table>

---

### Recognition

| | |
|---|---|
| 🥈 **Runners-up (2nd place)** | IBM Bob AI Hackathon 2026 — YieldGuard |
| 🥈 **Runners-up, Development track** | InnoTech 3.0 — YieldGuard |
| 📞 **Top 7** | Chaos2Commit (FUTURRIZON × CHARUSAT), AI Sales Agent challenge — Vaani |
| 🏁 **National finalist** | ODOO Hackathon 2025 · MSBC DataQuest 2025 · Reckon 7.0 2026 |
| 🎓 **NPTEL Elite** | Programming in Modern C++ |
| 🧩 **230+ problems** | Solved on LeetCode |
| 🤖 **Lead Organizer** | Institute-level Line-Following Robot Race |

---

<div align="center">

<a href="https://leetcode.com/u/Dhrumil_amin/">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://leetcard.jacoblin.cool/Dhrumil_Amin?theme=dark&amp;font=JetBrains%20Mono&amp;ext=heatmap" />
  <img src="https://leetcard.jacoblin.cool/Dhrumil_Amin?theme=light&amp;font=JetBrains%20Mono&amp;ext=heatmap" alt="LeetCode progress" width="500" />
</picture>
</a>

<br/><br/>

<sub><b>Measure before building. Ship the guardrail with the feature.</b></sub><br/>
<sub>Open to AI engineering &amp; full-stack internships —
<a href="mailto:dhrumilamin.645@gmail.com">email</a> ·
<a href="https://linkedin.com/in/dhrumil-amin-47429a260">LinkedIn</a> ·
<a href="https://dhrumilamin.me">portfolio</a></sub>

</div>
