> 一番下に日本語版もあります

# Resume — Kota Kawagoe

## Download
- 📄 Resume (PDF): [JP](https://project-kk.com/static/pdf/resume-jp.pdf) | [EN](https://project-kk.com/static/pdf/resume-en.pdf)
- 🌐 Portfolio: <https://project-kk.com/>
- 💼 LinkedIn: <https://www.linkedin.com/in/kota-kawa/>
- ✉️ Email: kota7kawagoe@gmail.com

## Live Services
- **ChatCore-AI**: <https://chatcore-ai.com/> (AI Chat & Prompt Sharing)
- **FS-QR**: <https://fs-qr.net/> (File Sharing & QR)
- **Yorozu Madoguchi**: <https://chat.project-kk.com/> (AI Concierge (Multi-Agent))

### **Looking for: Roles in AI Application Engineering or Backend Systems.**

## Summary

Software Engineer aiming to bring **Autonomous AI Agents** into real-world deployment by leveraging frontend and backend development experience.

**Core Strength: AI × Design × English**

My strength lies in the combination of AI, design, and English communication. These three elements allow me to transform technology into tangible solutions at a high level.

**Beyond Engineering: A Business-Minded Builder**

My value isn't just writing code — it's thinking through the business behind it: where real-world demand exists, what it costs to run and sustain a service, and how to turn that into a viable product. This makes me well-suited to launching new ventures from zero to one, owning the full range from **hackathon-speed prototyping to stable, reliable production operation** (as shown by my live services still running today).

**Experience:**
- Developed a **Multi-Agent Orchestration System** (integrating Browser-Agent, **IoT-Agent**, etc.) to bridge digital tasks with real-world physical feedback.
- Optimized **long/short-term memory** management, improving task success rates by **1.7x**.
- Presented research findings in an English oral session at **NCSP'26** (Honolulu, Hawaii).

## Key Projects (recommended order)
### 1) [Browser-Agent](https://github.com/kota-kawa/Browser-Agent) — (LLM-powered Browser Automation with Web UI)
- Summary: An LLM-powered browser automation agent wrapping `browser_use` with a **FastAPI** backend and **noVNC** web interface. Supports natural language control and WebArena benchmarking. WebArena Shopping task success rate: 32.6% (N=187; max steps=40; retries=4; same prompt setting).
- Tech: Python, FastAPI, Docker, `browser_use`, noVNC, Gemini/OpenAI/Anthropic.

### 2) [ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI) — (AI Chat & Prompt Sharing)
- Summary: An AI chat application built with FastAPI and Next.js. Features email authentication, Groq/Gemini API integration, and prompt sharing/search capabilities.
- Demo: <https://chatcore-ai.com/>
- Tech: Python (FastAPI), Next.js, PostgreSQL, Docker, Groq/Gemini API.

### 3) [Symphony Agent Conductor](https://github.com/kota-kawa/Symphony-Agent-Conductor) — (Autonomous Orchestration Platform)
- Summary: An autonomous orchestration platform using **LangGraph** to coordinate specialized agents (Browser automation, IoT control, RAG) for seamless interaction between digital tasks and physical device control.
- Tech: Python, Flask, LangGraph, `browser-use`, IoT (Jetson/Pi), OpenAI/Gemini.

<details>
  <summary><b>Other Projects (Click to expand)</b></summary>

### [Scheduler Agent](https://github.com/kota-kawa/Scheduler-Agent) — (AI Schedule Assistant)
- Summary: A chat-first scheduling assistant with timeline views that can use OpenAI, Gemini, or Anthropic models to manage routines and tasks.
- Tech: Python, PostgreSQL, Vite, Docker.

### [IoT Agent](https://github.com/kota-kawa/IoT-Agent) — (Conversational IoT Control Platform)
- Summary: A chat-controlled IoT platform with a web dashboard and camera snapshots, supporting Jetson, Raspberry Pi, and Pico W devices via LLM-based intent understanding. This project serves as a **precursor to Physical AI** — running a **local LLM on an edge device** (NVIDIA Jetson Orin Nano) to enable autonomous, low-latency intelligence at the physical layer.
- Tech: Python, Node.js, Docker, OpenAI/Gemini, Local LLM (Jetson Orin Nano).

### [Life-Style-Agent](https://github.com/kota-kawa/Life-Style-Agent) — (RAG-Powered Lifestyle Assistant)
- Summary: A multi-domain lifestyle RAG agent with MCP support, a web chat UI, and conversation analysis for proactive assistance.
- Tech: FastAPI, FAISS, LangChain/LlamaIndex, Embeddings, Docker.

### [Gemini3-Hackathon-Mystery-Game](https://github.com/kota-kawa/Gemini3-Hackathon-Mystery-Game) — (AI-powered Mystery Detective Game) `Gemini 3 Tokyo Hackathon 2026`
- Summary: An interactive locked-room mystery game where **Gemini 3** acts as Game Master, dynamically generating unique cases and responding to player questions. Built with **Nano Banana** at the **Gemini 3 Tokyo Hackathon 2026**.
- Tech: FastAPI, React, Gemini, Nano Banana, Docker.

### [Yorozu Madoguchi](https://github.com/kota-kawa/yorozu_madoguchi) — (AI Concierge (Multi-Agent)) `Meta Llama Ideathon 2024`
- Summary: A chat-based travel planner that turns conversations into personalized itineraries with a simple demo UI. Developed at the **Meta Llama Ideathon 2024**.
- Demo: <https://chat.project-kk.com/>
- Tech: Python, Docker.

### [FS-QR](https://github.com/kota-kawa/fs-qr) — (File Sharing & QR)
- Summary: A self-hosted file and note sharing tool with QR-based quick transfer, passworded group rooms, and real-time shared notes.
- Demo: <https://fs-qr.net/>
- Tech: FastAPI, Docker.
</details>

<details>
  <summary><b>Development Challenges (Click to expand)</b></summary>

### 1. LLM Agent Hallucinations on Date Calculation
([Scheduler-Agent](https://github.com/kota-kawa/Scheduler-Agent)) | Python / FastAPI / PostgreSQL / React / TypeScript / OpenAI・Anthropic・Gemini・Groq / Docker | Solo

**Challenge**: The LLM agent frequently miscalculated dates and weekdays. For example, "Schedule lunch next Friday" would often be saved on the wrong day. Since LLMs are probabilistic text generators, even deterministic calculations like "how many days until next Friday" can vary with subtle differences in context. Prompt engineering alone hit a clear ceiling.

**Solution**: Rather than having the LLM calculate dates by reasoning, I separated responsibilities: the LLM's role was narrowed to interpreting the user's natural language intent (e.g. identifying "next Friday" as a target weekday), while all actual date arithmetic was delegated to dedicated deterministic functions that always return the correct result. This made date handling reliable regardless of which model was used. Validated via a benchmark of 9 models (OpenAI, Anthropic, Gemini, Groq) across 10 tasks — a mid-tier model outperformed several frontier models, confirming that **reliability through design beats relying solely on model capability**.

### 2. Production-Only nginx Proxy Bugs — SSE Buffering & WebSocket Upgrade
([ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI), [FS-QR](https://github.com/kota-kawa/fs-qr)) | Python / FastAPI / Next.js / Redis / nginx / Docker | Solo

Encountered two separate production failures caused by the same root pattern: **nginx sits between client and server in production but is bypassed in local dev**, making the bugs invisible until deployment.

**SSE (ChatCore-AI)**: Token-by-token LLM streaming worked locally but arrived as a single block in production. nginx's default response buffering was swallowing the stream. Fixed with `proxy_buffering off` and `X-Accel-Buffering: no`.

**WebSocket (FS-QR)**: Real-time text sync across clients worked locally but WebSocket connections failed to establish in production. nginx defaults to HTTP/1.0, which drops the `Upgrade` header required for the WebSocket handshake. Fixed by adding a `location` block with `proxy_http_version 1.1`, `proxy_set_header Upgrade $http_upgrade`, `proxy_set_header Connection "upgrade"`, and extended timeouts. Also adopted Redis Pub/Sub to broadcast updates across multiple instances.

Hitting the same class of bug twice — different protocols, different projects — made the underlying pattern stick: **always validate streaming and persistent-connection features behind a production-equivalent nginx proxy, not just locally**.

### 3. OSS Internal State Corruption — Residual Events Polluting the Next Task
([Browser-Agent](https://github.com/kota-kawa/Browser-Agent)) | Python / FastAPI / Docker / browser_use / noVNC | Solo

**Challenge**: Designed the system to reuse browser sessions across tasks for efficiency. However, internal state left over from a completed task was interfering with the next task's execution. Ending the session cleanly shut it down entirely, while leaving it as-is caused state to accumulate until a crash — neither option worked.

**Solution**: The library provided no public API to reset its internal state between tasks, so I read through its source code directly to understand the internal structure, then implemented a cleanup routine that ran after each task completed. Since the internals differed across library versions, I also added version-aware fallback logic so the cleanup worked regardless of which version was installed. The experience reinforced the importance of **reading library source code rather than relying solely on documentation** when hitting the edge of a public API.

### 4. LLM-Generated Content Self-Contradiction — Dual-LLM Verification Loop
([Gemini3-Hackathon-Mystery-Game](https://github.com/kota-kawa/Gemini3-Hackathon-Mystery-Game)) | Python / FastAPI / React / Gemini / Nano Banana / Docker | Solo (7-hour hackathon)

**Challenge**: Had Gemini generate the mystery case (characters, alibis, evidence, timeline), then act as Game Master responding to player questions. The problem: Gemini would contradict its own generated case — for example, accurately revealing the culprit's alibi, or having a lying character speak the truth — making the game unsolvable.

**Solution**: Within the 7-hour hackathon constraint, implemented a two-stage response pipeline: generate the answer first, then pass it through a separate verification step where a second LLM call cross-checks the answer against the original case data and corrects any contradictions before delivery. Also added automatic retry logic on case generation to reject structurally malformed outputs. The key insight: **LLMs cannot reliably self-censor based on structured data they generated earlier in the same context** — a verification layer outside the generation call is necessary.

### 5. Shell Script Execute Permission Error Causing GitHub Actions CD Failure
([ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI)) | GitHub Actions / Docker / Linux / Bash | Solo

**Challenge**: The automated deployment pipeline via GitHub Actions kept failing at the step that invoked the deploy script (`./deploy.sh`). The script ran without issue when executed manually on the server with `bash deploy.sh`, so the error was not caught during local testing. The CI/CD runner was exiting with a "Permission denied" error, and the root cause was not immediately obvious because the file existed and the content was correct.

**Solution**: The issue was that the execute permission bit (`+x`) had not been set in git's index — only the file content was tracked, not the permission. Running `chmod +x deploy.sh` locally changes the filesystem but is not recorded by git unless explicitly staged with `git update-index --chmod=+x deploy.sh`. After staging and committing that change, GitHub Actions correctly inherited the execute bit and the deployment succeeded. The distinction between **filesystem permissions and git-tracked permissions** is easy to miss precisely because local `bash script.sh` invocations bypass the execute bit entirely, making the problem invisible until the CI runner tries direct execution.

### 6. Face-Recognition Login Accuracy — The Bottleneck Was the Data, Not Model Capacity
ResNet / TensorFlow / Keras / Python | Solo (AI coursework project during study abroad)

**Challenge**: Built a face-recognition login system with ResNet and TensorFlow, but recognition accuracy fell short of expectations. My first instinct was that the model lacked representational power, so I **added hidden layers to increase network capacity**. Accuracy barely improved — and increasing capacity against a limited dataset risked overfitting, pushing in the wrong direction entirely.

**Solution**: I reframed the plateau as a problem of **insufficient training data volume and diversity**, not model expressiveness. By applying data augmentation — rotating the face images and adjusting their brightness — I introduced variation in camera angle and lighting conditions into the training set. The model became robust to those variations and recognition accuracy improved. The lesson: **don't equate "low accuracy" with "make the model bigger"** — first determine whether the bottleneck lies on the model side (expressiveness) or the data side (volume and diversity).

### 7. Blue-Green Deployment Timing Issue — Momentary 500 Errors During Switch
([ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI)) | GitHub Actions / Docker / nginx / Linux | Solo

**Challenge**: Implemented Blue-Green deployment using GitHub Actions and nginx to achieve zero-downtime updates. However, during the deployment switch, users occasionally encountered 500 errors for a split second. The automation script was switching the nginx traffic to the new "Green" environment before the container's application process was fully ready to accept connections, even though the container itself was "running" from Docker's perspective.

**Solution**: Identified that the health check within the deployment script was too superficial (only checking if the container was up) or missing a sufficient "warm-up" wait. I improved the deployment flow by adding a robust health check loop that polls the specific application endpoint (e.g., `/health`) of the new container. Only after receiving a successful 200 OK response from the application itself does the script update the nginx configuration and reload the service. This ensured that traffic is only routed to fully initialized instances, eliminating the momentary 500 errors. The experience highlighted that **"container ready" does not mean "application ready"** and reinforced the need for application-level health validation in CI/CD pipelines.

</details>

## Skills
| Category | Technologies |
| :--- | :--- |
| **Programming Languages** | Python, TypeScript, SQL |
| **Web / Application Frameworks** | FastAPI, React, Next.js, Tailwind CSS, PostgreSQL, Redis |
| **AI / LLM Engineering** | RAG, Multi-Agent Systems, LangChain, LangGraph, browser-use |
| **Infrastructure** | Docker, AWS (EC2, VPC, Systems Manager), Linux, Nginx, Git, GitHub Actions, pytest |
| **IoT / Hardware** | NVIDIA Jetson Orin Nano, Raspberry Pi 4/Pico W |
| **AI Tools** | Codex, Claude Code, NotebookLM, Antigravity, Gemini, ChatGPT, Claude |

<details>
<summary><strong>How I Use AI Tools</strong></summary>

I integrate AI tools across the full workflow — from research to documentation to implementation:

| Phase | Tool | How I Use It |
| :--- | :--- | :--- |
| **Research & Learning** | NotebookLM | Ingest papers, technical docs, and lecture materials to generate concise summaries and structured study notes. Quickly grasp unfamiliar domains before diving into implementation. |
| **Documentation & Presentation** | Claude | Draft and iteratively refine PowerPoint slides, Word documents, and technical reports. Use it as a writing partner to improve clarity, structure, and persuasiveness of deliverables. |
| **Coding & Development** | Codex, Claude Code, Antigravity | Accelerate development with AI-assisted coding — from scaffolding new features and debugging complex issues to writing tests and refactoring. Leverage agentic coding tools for multi-file changes across full-stack projects. |
| **Ideation & Problem Solving** | Gemini, ChatGPT, Claude | Brainstorm architecture decisions, explore design trade-offs, and validate technical approaches through conversational reasoning. |

</details>


## Experience
**EdTech Company** — Joint Researcher / Project Lead
- **Lead Researcher for RAG System Optimization**: In the joint research team's development process, we divided the work into three steps: masking personally identifiable information in Q&A data, validating consecutive masked data by comparing results across multiple LLMs, and evaluating data storage formats for RAG. Each step was assigned to one team member. As project lead, I applied my prior experience developing RAG chat systems to support each member's implementation, design, and validation direction across the project. I also used GitHub to version-control code and experiment details, reviewed each member's changes, and aligned the team's overall implementation direction.
- **Patent Pending**: Co-filed a patent based on findings from this research.
- **Publication**: Presented research findings at **FIT 2025 (Forum on Information Technology)**, demonstrating measurable improvements in response reliability. → [Presentation Slides](https://project-kk.com/static/research/FIT発表資料.pdf)

**EdTech Company** — Software Engineering Intern (2 months)
- After completing the joint research, joined as an intern to bring its findings into production; designed and developed an in-house AI agent system for the customer support team on **AWS**.
- Converted and **structured** Jira operations manuals into Markdown, then built a **hybrid RAG pipeline** (BM25 + vector search) with **gpt-5.1-mini**; iterated on **prompt design** to deliver accurate natural language Q&A via a chat UI.
- Extended beyond simple RAG chat to a full **customer support agent** with: automatic Jira ticket creation via Jira API integration, and auto-generation of customer-facing email drafts alongside RAG answers.
- Ran daily discussions with the customer support team to iteratively refine **requirements and response quality** end-to-end.
- **Branch-based workflow & PR reviews**: Developed each feature on a dedicated `feature/*` or `fix/*` branch; opened **Pull Requests** with clear descriptions before merging, and acted as reviewer for teammates' PRs — leaving structured feedback to maintain code quality and consistency across the codebase.

## Education
- **Keio University Graduate School, SFC (Shonan Fujisawa Campus)** — M.S. in Cyber Informatics, Graduate School of Media and Governance
  - Kanagawa, Japan | Apr 2026 –
- **Kanagawa Institute of Technology** — B.S. in Information Network and Communication, Faculty of Information Technology
  - Kanagawa, Japan | Apr 2021 – Mar 2026 (including 1 year leave of absence)
  - **Graduation Research**: [EN](https://project-kk.com/static/research/Graduation-Research-Paper-en.pdf) | [JP](https://project-kk.com/static/research/Graduation-Research-Paper-ja.pdf)
- **University of North Alabama** — International Exchange Program
  - Alabama, USA | Jun 2023 – May 2024
  - **Honors**: **Dean's List** (Fall 2023, GPA: 3.75/4.0).
  - **Achievement**: **1st out of 30** in the **AI (Artificial Intelligence)** course final project — built a face recognition login system using OpenCV & TensorFlow.
  - **Relevant Coursework**: Artificial Intelligence, Intro to HCI/UX, Design I & II, Applied Computer Science.

## Activities
- **Matsuo Lab (The University of Tokyo) Programs & Competitions** (2024 - 2025)
  - **LLM Course Final Project & Competition**: Developed fine-tuned models using **LoRA SFT** and **DPO**, achieving a **top 4% (70 / 1800) ranking**. Featured model: [Llama-3.1-8B-Instruct-Freedom_v3](https://huggingface.co/kota-kawa/Llama-3.1-8B-Instruct-Freedom_v3).
  - **LLM Competition 2025**: As the team's training data lead, built and published a high-difficulty synthetic dataset for mathematical reasoning ([difficult_math_deepseek_llama](https://huggingface.co/datasets/kota-kawa/difficult_math_deepseek_llama)).
  - **Specialized Courses**: Took courses including AI Management (PwC joint), LLM, GCI (Data Science), Deep Learning, and Deep Generative Models.
- **NCSP'26 (2026 RISP International Workshop on Nonlinear Circuits, Communications and Systems)** (Mar 2026)
  - Presented research on an **AI Multi-Agent Orchestration System** in an English oral session (Honolulu, Hawaii).
  - Developed a system integrating 5 specialized agents: **RAG**, **Web Operation**, **IoT**, **Scheduler**, and **Orchestrator**.
  - Presentation Material: → [NCSP-Presentation-EN.pdf](https://project-kk.com/static/research/NCSP-Presentation-EN.pdf)
- **Gemini 3 Tokyo Hackathon 2026** (2026)
  - Completed a mystery game powered by **Gemini** and **Nano Banana** within the 7-hour time limit. → [Gemini3-Hackathon-Mystery-Game](https://github.com/kota-kawa/Gemini3-Hackathon-Mystery-Game)
- **Meta Llama Ideathon 2024** (Sep 2024)
  - **Participant** in Meta's official AI hackathon in Tokyo.
  - Developed a generative AI prototype leveraging Llama 3 models. → [Yorozu Madoguchi](https://github.com/kota-kawa/yorozu_madoguchi)

## Language
- **Japanese**: Native
- **English**: Professional Proficiency (TOEIC 715, 1-year academic study in US)

## Notes
- Last updated: 2026-06-15
- License: All rights reserved

<details>
  <summary>日本語版（クリックで展開）</summary>

# Resume（職務経歴/履歴書） — 川越 航太

## ダウンロード
- 📄 Resume（PDF）：[JP](https://project-kk.com/static/pdf/resume-jp.pdf) | [EN](https://project-kk.com/static/pdf/resume-en.pdf)
- 🌐 Portfolio：<https://project-kk.com/>
- 💼 LinkedIn：<https://www.linkedin.com/in/kota-kawa/>
- ✉️ Email：kota7kawagoe@gmail.com

## 実際に動いているサービス
- **ChatCore-AI**: <https://chatcore-ai.com/> (AIチャット & プロンプト共有)
- **FS-QR**: <https://fs-qr.net/> (ファイル共有 & QR)
- **よろず窓口**: <https://chat.project-kk.com/> (AIコンシェルジュ（マルチエージェント）)

### **志望：AIアプリケーションエンジニア / バックエンドシステム開発。**

## サマリー

これまでのフロントエンド/バックエンド開発経験を活かし、**自律型AIエージェント**の社会実装を目指すソフトウェアエンジニア。

**強み：AI × デザイン × 英語**

AIとデザイン、そして英語でのコミュニケーション。これら3つの要素を高い次元で組み合わせ、技術を形にできることが私の強みです。

**エンジニアリングを超えて：ビジネス視点を持つ開発者**

私の価値は、ただコードを書くことではなく、その先にあるビジネスを考えられることにあります。世の中のどこに本当の需要があるのか、サービスの運用・維持にどれだけのコストがかかるのか、それをいかに成立するプロダクトへ落とし込むかまでを見据えます。だからこそゼロからの**新規事業の立ち上げ**を得意とし、**ハッカソン的な素早いプロトタイピングから、安定した本番運用まで**を一気通貫で担えます（現在も稼働を続ける各サービスがその実績です）。

**エピソード：**
- **マルチエージェント・オーケストレーションシステム**を開発（Browser-Agentや**IoT-Agent**等を統合）。Web完結に留まらず、ハードウェアを介した実世界へのフィードバックまでを実現。
- **長期・短期メモリの最適化**により、タスク成功率を**1.7倍**に改善。
- 国際会議 **NCSP'26**（ハワイ）にて、本成果を英語で口頭発表。

## 主要プロジェクト（おすすめ順）
### 1) [Browser-Agent](https://github.com/kota-kawa/Browser-Agent) — (Web UI付きブラウザ自動化エージェント)
- 概要：`browser_use`を**FastAPI**と**noVNC**でラップした、Web UI付きブラウザ自動化エージェント。自然言語による操作とWebArenaベンチマーク評価に対応。WebArena Shoppingタスク成功率: 32.6% (N=187, 最大ステップ数=40, リトライ回数=4, 同一プロンプト設定)。
- 技術：Python, FastAPI, Docker, `browser_use`, noVNC, Gemini/OpenAI/Anthropic.

### 2) [ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI) — (AIチャット & プロンプト共有)
- 概要：FastAPIとNext.jsを用いたAIチャットアプリ。メール認証、Groq/Gemini API連携に加え、ユーザー間でプロンプトを共有・検索できる機能を搭載。
- デモ：<https://chatcore-ai.com/>
- 技術：Python (FastAPI), Next.js, PostgreSQL, Docker, Groq/Gemini API.

### 3) [Symphony Agent Conductor](https://github.com/kota-kawa/Symphony-Agent-Conductor) — (自律型エージェントオーケストレーション)
- 概要：**LangGraph**を用いた中央オーケストレーターを構築し、ブラウザ操作やIoT制御を行う専門エージェントを協調動作させることで、デジタル作業と物理デバイス制御のシームレスな連携を実現。
- 技術：Python, Flask, LangGraph, `browser-use`, IoT (Jetson/Pi), OpenAI/Gemini.

<details>
  <summary><b>その他のプロジェクト（クリックで展開）</b></summary>

### [Scheduler Agent](https://github.com/kota-kawa/Scheduler-Agent) — (AIスケジュール管理アシスタント)
- 概要：チャットで日々のルーティンやタスクを管理し、タイムライン表示にも対応するスケジュール管理アプリ。
- 技術：Python, PostgreSQL, Vite, Docker.

### [IoT Agent](https://github.com/kota-kawa/IoT-Agent) — (会話型IoT制御プラットフォーム)
- 概要：チャット指示でデバイス制御を行い、ダッシュボードやカメラ撮影を備えたIoT管理プラットフォーム。Jetson/Raspberry Pi/Pico Wに対応。**NVIDIA Jetson Orin Nano** 上でローカルLLMを動作させ、低遅延かつオフライン対応のエッジインテリジェンスを実現。このアーキテクチャは **Physical AI の前身** にあたる取り組みである。
- 技術：Python, Node.js, Docker, OpenAI/Gemini, ローカルLLM（Jetson Orin Nano）.

### [Life-Style-Agent](https://github.com/kota-kawa/Life-Style-Agent) — (生活支援RAGエージェント)
- 概要：生活領域の多分野知識をRAGで統合し、MCP対応・会話分析機能を備えた生活支援AI。
- 技術：FastAPI, FAISS, LangChain/LlamaIndex, Embeddings, Docker.

### [Gemini3-Hackathon-Mystery-Game](https://github.com/kota-kawa/Gemini3-Hackathon-Mystery-Game) — (AI駆動ミステリー探偵ゲーム) `Gemini 3 東京ハッカソン 2026`
- 概要：**Gemini 3** がゲームマスターとなり、密室殺人事件をダイナミックに生成するインタラクティブなミステリーゲーム。**Nano Banana** を活用し、**Gemini 3 東京ハッカソン 2026** にて開発。
- 技術：FastAPI, React, Gemini, Nano Banana, Docker.

### [よろず窓口](https://github.com/kota-kawa/yorozu_madoguchi) — (AIコンシェルジュ（マルチエージェント）) `Meta Llama Ideathon 2024`
- 概要：AIとのチャット相談から旅行プランを自動生成するシンプルなデモアプリ。**Meta Llama Ideathon 2024** にて開発。
- デモ：<https://chat.project-kk.com/>
- 技術：Python, Docker.

### [FS-QR](https://github.com/kota-kawa/fs-qr) — (ファイル共有 & QR)
- 概要：QRによる即時共有、合言葉付きのグループ共有、リアルタイム共有ノートを備えたセルフホスト型のファイル/メモ共有ツール。
- デモ：<https://fs-qr.net/>
- 技術：FastAPI, Docker.
</details>

<details>
  <summary><b>開発で苦労した点（クリックで展開）</b></summary>

### 1. LLMエージェントの日付計算ハルシネーション対策
([Scheduler-Agent](https://github.com/kota-kawa/Scheduler-Agent)) | Python / FastAPI / PostgreSQL / React / TypeScript / OpenAI・Anthropic・Gemini・Groq / Docker | 個人開発

**苦労したこと**: LLMエージェントが日付・曜日の計算を頻繁に誤るという問題が発生した。「来週の金曜日にランチを入れて」と指示しても、別の日に登録されるケースが多発した。LLMは確率的なテキスト生成をベースにしており、「今日から何日後が来週の金曜か」という決定論的な計算でさえ文脈のゆれで答えがぶれる。プロンプト改善だけでは限界があり、根本的な設計変更が必要と判断した。

**解決策**: LLMに日付を計算させるのをやめ、役割を分離した。LLMの担当はユーザーの自然言語の意図を読み取ること（「来週の金曜」がどの曜日を指すかを判断すること）に限定し、実際の日付計算は常に正しい結果を返す専用の決定論的な関数群に委ねる設計に変更した。これによりどのモデルを使っても日付処理が安定するようになった。OpenAI・Anthropic・Gemini・Groqの9モデルで10タスクのベンチマーク評価を実施し、中堅モデルが複数のフロンティアモデルを上回る精度を出せることも確認。**「モデルの性能だけに頼らず、設計で信頼性を担保する」** という判断の正しさを実証できた。

### 2. 本番環境特有のnginxプロキシ問題 — SSEバッファリングとWebSocketアップグレード
([ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI), [FS-QR](https://github.com/kota-kawa/fs-qr)) | Python / FastAPI / Next.js / Redis / nginx / Docker | 個人開発

異なるプロジェクトで同じ根本パターンの障害を2度経験した。**ローカル開発ではnginxを経由しないため発覚せず、本番デプロイ後に初めて顕在化する問題**という共通構造だった。

**SSE（ChatCore-AI）**: LLMのトークン逐次配信をSSEで実装したところ、本番環境ではレスポンスがバッファリングされ全文一括表示になった。原因はnginxのデフォルトのレスポンスバッファリング。`proxy_buffering off`と`X-Accel-Buffering: no`の追加で解決。

**WebSocket（FS-QR）**: テキストのリアルタイム同期をWebSocketで実装したところ、本番環境でWebSocket接続が確立できなかった。nginxがデフォルトでHTTP/1.0を使用しており、WebSocketハンドシェイクに必要な`Upgrade`ヘッダーが転送されていなかったことが原因。`location`ブロックに`proxy_http_version 1.1`・`proxy_set_header Upgrade $http_upgrade`・`proxy_set_header Connection "upgrade"`・タイムアウト延長を追加して解決。複数インスタンス間のブロードキャストにはRedis Pub/Subを採用した。

異なるプロトコル・異なるプロジェクトで同じクラスのバグを踏んだことで、**ストリーミングや持続接続の機能は本番相当のnginx構成で検証する**という習慣が身についた。

### 3. OSSの内部状態汚染 — 前のタスクの残留状態が次タスクに干渉する問題
([Browser-Agent](https://github.com/kota-kawa/Browser-Agent)) | Python / FastAPI / Docker / browser_use / noVNC | 個人開発

**苦労したこと**: 効率化のためブラウザセッションをタスク間で使い回す設計を採用したところ、前のタスク終了後にライブラリ内部に残留した状態が次タスクの実行に干渉するという問題が発生した。セッションを完全に終了させると次のタスクが実行できなくなり、そのままにすれば状態が積み上がってクラッシュする。どちらの選択肢も機能しなかった。

**解決策**: ライブラリには内部状態をリセットするための公開APIが存在しなかったため、ソースコードを直接読み込んで内部構造を把握し、タスク終了ごとに状態をリセットするクリーンアップ処理を独自実装した。さらにライブラリのバージョンによって内部構造が異なるため、バージョンに応じて動作を切り替えるフォールバックロジックも追加し、どのバージョンでも正常に動作するようにした。**公開APIの限界に当たったときはドキュメントではなくソースコードを読む** という判断の重要性を学んだ。

### 4. LLMが自分で生成した内容に矛盾する問題 — 二重LLM検証ループ
([Gemini3-Hackathon-Mystery-Game](https://github.com/kota-kawa/Gemini3-Hackathon-Mystery-Game)) | Python / FastAPI / React / Gemini / Nano Banana / Docker | 個人開発（7時間ハッカソン）

**苦労したこと**: Geminiにミステリーの事件データ（登場人物・アリバイ・証拠・タイムライン）を生成させ、そのデータをもとにゲームマスターとして回答させたところ、Geminiが自分で生成した事件と矛盾した回答を返す問題が多発した。例えば犯人のアリバイを正確に話してしまう、嘘つき設定のキャラクターが正直に答えてしまうなど、ゲームとして成立しなくなるケースが続出した。

**解決策**: 7時間というハッカソンの制約の中で、二段構えの回答パイプラインを実装した。①まず通常通り回答を生成し、②別のLLM呼び出しで回答と事件データを照合して矛盾を検出・修正してからプレイヤーに届ける。また、事件データ生成時に構造的に不正な出力を自動的に検出してやり直す仕組みも追加した。この経験から、**LLMは同じコンテキスト内で自分が生成した情報を参照して自己検閲することが苦手** であり、生成と検証を別の呼び出しに分離する設計が有効だという知見を得た。

### 5. デプロイ用シェルスクリプトの実行権限問題によるGitHub Actions CDの失敗
([ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI)) | GitHub Actions / Docker / Linux / Bash | 個人開発

**苦労したこと**: GitHub Actionsによる自動デプロイパイプラインが、デプロイスクリプト（`./deploy.sh`）の呼び出しステップで毎回失敗するという問題が発生した。ローカルで`bash deploy.sh`と実行すると問題なく動作するためエラーの原因が掴めず、CIランナー上での"Permission denied"エラーを見てもすぐにはピンとこなかった。

**解決策**: 原因は、実行権限（`+x`）のビットがgitのインデックスに記録されていなかったことだった。ローカルで`chmod +x deploy.sh`を実行してもgitはファイルの内容だけを追跡しており、権限ビットは`git update-index --chmod=+x deploy.sh`で明示的にステージングしなければgitに反映されない。この変更をコミットすることで、GitHub ActionsのランナーにもCHMOD後の実行権限が正しく継承され、デプロイが成功するようになった。ローカルでの`bash script.sh`実行は実行権限ビットをそもそも要求しないため問題が顕在化せず、**「ファイルシステムのパーミション」と「gitが追跡するパーミション」の違い**がCIランナーによる直接実行で初めて露見するという構造を学んだ。

### 6. 顔認証ログインの精度不足 — モデルの容量ではなく学習データがボトルネックだった
ResNet / TensorFlow / Keras / Python | 個人開発（留学先のAI授業プロジェクト）

**苦労したこと**: ResNetとTensorFlowで顔認証ログインシステムを構築したが、認証精度が想定より上がらなかった。最初の打ち手として**モデルの表現力が足りないと考え、隠れ層を追加してネットワークの容量を増やした**。しかし精度はほとんど改善せず、むしろ限られた学習データに対して容量だけを増やすことは過学習を招きかねない逆効果の方向だった。

**解決策**: 精度の頭打ちはモデルの表現力ではなく**学習データの量と多様性の不足**側にあると切り分けた。顔画像を回転させたり明るさを調整したりしてデータ拡張（Data Augmentation）を行い、撮影角度や照明条件のばらつきを学習データに与えたところ、モデルがそれらの変動に対して頑健になり認証精度が向上した。この経験から、**「精度が低い＝モデルを大きくする」と短絡せず、ボトルネックがモデル側（表現力）にあるのかデータ側（量・多様性）にあるのかをまず切り分ける**という判断の重要性を学んだ。

### 7. Blue-Greenデプロイの切り替えタイミング不備による瞬間的な500エラー
([ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI)) | GitHub Actions / Docker / nginx / Linux | 個人開発

**苦労したこと**: ゼロダウンタイムでの更新を目指し、GitHub Actionsとnginxを組み合わせたBlue-Greenデプロイを導入した。しかし、デプロイの切り替え時に一瞬だけ500エラーが発生するという問題に直面した。原因を調査したところ、Dockerコンテナ自体は起動しているものの、その内部でアプリケーションプロセスが完全に立ち上がりリクエストを受け付けられる状態になる前に、nginxの向き先を新しい（Green）環境に切り替えてしまっていたことが判明した。

**解決策**: デプロイスクリプトに、アプリケーションレベルでのヘルスチェック待ち処理を追加した。単にコンテナの起動を待つのではなく、アプリケーションが提供する特定のヘルスチェックエンドポイント（`/health`など）に対してポーリングを行い、実際に200 OKが返ってくることを確認してからnginxの向き先を切り替えるようにフローを改善した。これにより、完全に準備が整ったインスタンスのみにトラフィックが流れるようになり、切り替え時のエラーを完全に解消できた。**「コンテナの起動」と「アプリケーションの準備完了」は別物である**という教訓を得るとともに、CI/CDパイプラインにおける実用的なヘルスチェックの重要性を再認識した。

</details>

## スキル
| カテゴリ | 技術 |
| :--- | :--- |
| **プログラミング言語** | Python, TypeScript, SQL |
| **Web / アプリケーションフレームワーク** | FastAPI, React, Next.js, Tailwind CSS, PostgreSQL, Redis |
| **AI / LLM エンジニアリング** | RAG, Multi-Agent Systems, LangChain, LangGraph, browser-use |
| **インフラ** | Docker, AWS (EC2, VPC, Systems Manager), Linux, Nginx, Git, GitHub Actions, pytest |
| **IoT / ハードウェア** | NVIDIA Jetson Orin Nano, Raspberry Pi 4/Pico W |
| **AIツール** | Codex, Claude Code, NotebookLM, Antigravity, Gemini, ChatGPT, Claude |

<details>
<summary><strong>AIツールの活用方法</strong></summary>

リサーチからドキュメント作成、実装まで、ワークフロー全体にAIツールを統合して活用しています：

| フェーズ | ツール | 活用方法 |
| :--- | :--- | :--- |
| **リサーチ・学習** | NotebookLM | 論文や技術ドキュメント、講義資料を取り込み、要約や構造化されたノートを生成。未知の分野も実装前に素早くキャッチアップ。 |
| **資料作成・プレゼン** | Claude | パワーポイントスライドやWordドキュメント、技術レポートの作成・改善を反復的に実施。構成・明瞭さ・説得力の向上にライティングパートナーとして活用。 |
| **コーディング・開発** | Codex, Claude Code, Antigravity | 新機能のスキャフォールディング、複雑なデバッグ、テスト作成、リファクタリングまでAI支援コーディングで開発を加速。エージェント型コーディングツールを活用し、フルスタックプロジェクトの複数ファイルにまたがる変更を効率的に実施。 |
| **アイデア出し・問題解決** | Gemini, ChatGPT, Claude | アーキテクチャの意思決定、設計トレードオフの検討、技術的アプローチの妥当性検証を対話的に実施。 |

</details>

## 経験
**教育系IT企業** — 共同研究員 / プロジェクトリーダー
- **RAGシステム最適化の共同研究**: 共同研究のチーム開発では、Q&Aデータの個人情報部分のマスキング、連続した複数のマスキング済みデータを複数LLMで比較する検証、RAG用データ保存形式の検討という3ステップに分け、それぞれを1人ずつ担当して開発を進めた。自分はプロジェクトリードとして、これまでのRAGチャット開発の経験を活かし、3人それぞれの実装・設計・検証方針を横断的にサポートした。GitHubを使ってコードと実験内容をバージョン管理し、各担当の変更内容を確認しながら、チーム全体の実装方針をそろえた。
- **特許出願中**: 本研究の成果をもとに特許を共同出願。
- **研究成果の発表**: FIT 2025（第24回情報科学技術フォーラム）にて本研究の成果を発表し、回答精度の向上を実証。 → [発表資料](https://project-kk.com/static/research/FIT発表資料.pdf)

**教育系IT企業** — ソフトウェアエンジニアインターン（2か月）
- 共同研究終了後、その成果を実際のプロダクトに落とし込むためにインターンとして参加。カスタマーサポートチーム向けの社内AIエージェントシステムを**AWS上**で設計・開発。
- Jira上に蓄積された操作マニュアルをMarkdown形式に**変換・構造化**し、BM25とベクトル検索を組み合わせた**ハイブリッド検索RAGパイプライン**を構築。**gpt-5.1-mini**を用いた**プロンプト設計**を重ね、チャットUIから自然言語で問い合わせに回答できるシステムを実装。
- 単純なRAGチャットにとどまらず、Jira API連携による問い合わせチケットの自動起票、RAG回答に加えた顧客向けメール文案の自動生成まで機能を拡張した**カスタマーサポートエージェント**として開発。
- 実際にカスタマーサポートチームに使ってもらいながら、毎日ディスカッションを重ねて**要件定義から応答品質の改善**までを反復的に実施。
- **ブランチ戦略・PRレビュー**: 機能ごとに `feature/*` / `fix/*` ブランチを切って開発し、変更内容を明記した **Pull Request** を通じてコードレビューを実施。レビュアーとしてもチームメンバーのPRに構造的なフィードバックを行い、マージ前のコード品質と実装方針の一貫性を担保した。

## 学歴
- **慶應義塾大学大学院 湘南藤沢キャンパス（SFC）** — 政策・メディア研究科 サイバーインフォマティクス専攻 修士課程
  - 神奈川県 | 2026年4月 –
- **神奈川工科大学** — 情報学部 情報ネットワークコミュニケーション学科 学士
  - 神奈川県 | 2021年4月 – 2026年3月（うち1年休学）
  - **卒業論文**：[EN](https://project-kk.com/static/research/Graduation-Research-Paper-en.pdf) | [JP](https://project-kk.com/static/research/Graduation-Research-Paper-ja.pdf)
- **University of North Alabama** — 交換留学プログラム修了
  - アラバマ州, 米国 | 2023年6月 – 2024年5月
  - **栄誉**: **成績優秀者（Dean's
  List）** 選出（2023年秋期、GPA: 3.75/4.0）
  - **実績**: **AI（人工知能）** 授業の最終プロジェクトでクラス**1位**（30人中）。OpenCV・TensorFlowで顔認証ログインシステムを開発。
  - **主要履修科目**: 人工知能 (AI), HCI/UX, デザイン I & II, コンピュータ応用。

## 活動歴
- **松尾研究室（東京大学）関連プログラム・コンペティション** (2024年 - 2025年)
  - **LLM講座 最終プロジェクト & コンペティション**: LoRA SFTおよびDPOを用いたモデルを開発し、コンペティションにて上位4% (70 / 1800) に入賞。開発モデル：[Llama-3.1-8B-Instruct-Freedom_v3](https://huggingface.co/kota-kawa/Llama-3.1-8B-Instruct-Freedom_v3)
  - **LLMコンペ2025**: チーム内で学習データ作成を担当し、数学的推論向け高難度合成データセットを構築・公開（[difficult_math_deepseek_llama](https://huggingface.co/datasets/kota-kawa/difficult_math_deepseek_llama)）。
  - **専門講座受講**: AI経営講座（PwC共同開催）、LLM講座、GCI (データサイエンス基礎)、深層学習、深層生成モデル。
- **NCSP'26 (2026 RISP International Workshop on Nonlinear Circuits, Communications and Systems)**（2026年3月）
  - ハワイ・ホノルルで開催された国際会議にて、「AIマルチエージェント・オーケストレーションシステム」に関する研究成果を英語で口頭発表。
  - 5種の専門エージェント（**RAG**、**Web操作**、**IoT**、**Scheduler**、**Orchestrator**）を統合した自律型システムを開発。
  - 発表した資料：→ [NCSP-Presentation-EN.pdf](https://project-kk.com/static/research/NCSP-Presentation-EN.pdf)
- **Gemini 3 東京ハッカソン 2026** (2026年)
  - **Gemini** と **Nano Banana** を活用したミステリゲームを、7時間の制限時間以内に完成させた。→ [Gemini3-Hackathon-Mystery-Game](https://github.com/kota-kawa/Gemini3-Hackathon-Mystery-Game)
- **Meta Llama Ideathon 2024** (2024年9月)
  - Meta社主催のAIハッカソンに参加。
  - Llama 3 モデルを活用した生成AIプロトタイプを開発。→ [よろず窓口](https://github.com/kota-kawa/yorozu_madoguchi)

## 語学
- **日本語**: ネイティブ
- **英語**: ビジネスレベル (TOEIC 715, 米国大学での1年間の留学経験)

## 補足
- 最終更新：2026-06-15
- ライセンス：All rights reserved
</details>
