> 一番下に日本語版もあります

# Resume — Kota Kawagoe

## 📄 Download
- 📄 Resume (PDF): [JP](https://project-kk.com/static/pdf/resume-jp.pdf) | [EN](https://project-kk.com/static/pdf/resume-en.pdf)
- 🌐 Portfolio: <https://project-kk.com/>
- 💼 LinkedIn: <https://www.linkedin.com/in/kota-kawa/>
- ✉️ Email: kota7kawagoe@gmail.com

## 🚀 Live Services
- **ChatCore-AI**: <https://chatcore-ai.com/> (Production AI Chat Platform & Prompt Sharing)
- **FS-QR**: <https://fs-qr.net/> (File Sharing & QR)

### **Looking for: Roles in AI Application Engineering or Backend Systems.**

## 👤 Summary

Software engineer and master's student at Keio University Graduate School of Media and Governance (SFC), researching AI agents while building and operating production web services.

My focus is the system design that connects LLMs to real applications. I work on selecting the right Memory, Skills, Tools, and Agents; safely executing external tools; managing conversational and user context; recovering from LLM and API failures; controlling inference cost and usage; and making AI features reliable in production.

My current work spans two areas:
- **Production AI applications**: Designing, building, and improving deployed services such as [ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI).
- **AI agent research**: Studying Object Routing, which selects executable resource sets from large collections for AI agents, and developing [Marmo-Core](https://github.com/kota-kawa/Marmo-Core), an open-source library for managing Memory, Skills, Tools, and Agents.

Through internships and independently operated services, I have worked across problem discovery, requirements definition, design, implementation, testing, code review, production deployment, and evaluation using real usage data.

## 🧩 Key Projects (recommended order)
### 1) [ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI) — (Production AI Chat Platform)
- Summary: A production AI chat platform built with FastAPI and Next.js and deployed at chatcore-ai.com. Implements streaming responses from multiple LLMs, web research and tool use, Tasks and Skills, persistent context, prompt sharing, and generative UI. Designed for production operation with Redis-backed session management, usage and cost controls, SSE error recovery, testing, and CI/CD.
- Demo: <https://chatcore-ai.com/>
- Tech: Python, FastAPI, Next.js, React, TypeScript, PostgreSQL, Redis, Docker, Nginx, GitHub Actions, OpenAI/Anthropic/Groq APIs.

### 2) [Marmo-Core](https://github.com/kota-kawa/Marmo-Core) — (AI-Agent Resource Kernel)
- Summary: A lightweight Python kernel for registering, retrieving, selecting, and safely executing AI-agent resources. Includes policy-gated execution, audit trails, deterministic mock runs, CLI tooling, and OpenAI-compatible/Anthropic LLM providers.
- Tech: Python, resource registry, policy layer, lexical/HyDE retrieval, CLI, OpenAI/Anthropic APIs.

### 3) [Browser-Agent](https://github.com/kota-kawa/Browser-Agent) — (LLM-powered Browser Automation with Web UI)
- Summary: An LLM-powered browser automation agent wrapping `browser_use` with a **FastAPI** backend and **noVNC** web interface. Supports natural language control and WebArena benchmarking. WebArena Shopping task success rate: 32.6% (N=187; max steps=40; retries=4; same prompt setting).
- Tech: Python, FastAPI, Docker, `browser_use`, noVNC, Gemini/OpenAI/Anthropic.

<details>
  <summary><b>Other Projects (Click to expand)</b></summary>

### [Symphony Agent Conductor](https://github.com/kota-kawa/Symphony-Agent-Conductor) — (Autonomous Orchestration Platform)
- Summary: An autonomous orchestration platform using **LangGraph** to coordinate specialized agents (Browser automation, IoT control, RAG) for seamless interaction between digital tasks and physical device control.
- Tech: Python, Flask, LangGraph, `browser-use`, IoT (Jetson/Pi), OpenAI/Gemini.

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

**Solution**: Rather than having the LLM calculate dates by reasoning, I separated responsibilities: the LLM's role was narrowed to interpreting the user's natural language intent (e.g. identifying "next Friday" as a target weekday), while all actual date arithmetic was delegated to dedicated deterministic functions that always return the correct result. This removed date arithmetic from the model's responsibilities. I also benchmarked 9 models (OpenAI, Anthropic, Gemini, Groq) across 10 tasks; a mid-tier model outperformed several frontier models under the same setup.

### 2. Production Failures — nginx Proxy Behavior and Deployment Readiness
([ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI), [FS-QR](https://github.com/kota-kawa/fs-qr)) | Python / FastAPI / Next.js / Redis / nginx / Docker / GitHub Actions | Solo

Production exposed failures that local development did not: nginx changed how streaming and persistent connections behaved, and the deployment switch sent traffic to an application before it was ready.

**SSE (ChatCore-AI)**: Token-by-token LLM streaming worked locally but arrived as a single block in production. nginx's default response buffering was swallowing the stream. Fixed with `proxy_buffering off` and `X-Accel-Buffering: no`.

**WebSocket (FS-QR)**: Real-time text sync across clients worked locally but WebSocket connections failed to establish in production. nginx defaults to HTTP/1.0, which drops the `Upgrade` header required for the WebSocket handshake. Fixed by adding a `location` block with `proxy_http_version 1.1`, `proxy_set_header Upgrade $http_upgrade`, `proxy_set_header Connection "upgrade"`, and extended timeouts. Also adopted Redis Pub/Sub to broadcast updates across multiple instances.

**Blue-Green deployment (ChatCore-AI)**: Switching nginx traffic when the new Docker container was running occasionally caused brief 500 errors because the application was still starting. Added a deployment health-check loop that waits for a 200 response from the application endpoint before updating nginx and reloading it.

These failures led me to validate streaming and persistent connections through a production-equivalent proxy and to check application readiness before routing traffic to a new instance.

### 3. OSS Internal State Corruption — Residual Events Polluting the Next Task
([Browser-Agent](https://github.com/kota-kawa/Browser-Agent)) | Python / FastAPI / Docker / browser_use / noVNC | Solo

**Challenge**: Designed the system to reuse browser sessions across tasks for efficiency. However, internal state left over from a completed task was interfering with the next task's execution. Ending the session cleanly shut it down entirely, while leaving it as-is caused state to accumulate until a crash — neither option worked.

**Solution**: The library provided no public API to reset its internal state between tasks, so I read through its source code directly to understand the internal structure, then implemented a cleanup routine that ran after each task completed. Since the internals differed across library versions, I also added version-aware fallback logic so the cleanup worked regardless of which version was installed. The experience reinforced the importance of **reading library source code rather than relying solely on documentation** when hitting the edge of a public API.

### 4. Recovering Long LLM Streams Without Losing or Duplicating Output
([ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI)) | Python / FastAPI / SSE / Redis / LLM APIs | Solo

**Challenge**: Long chats involving web research and multiple tool calls could hit output limits or fail mid-stream because of transient API errors. Retrying the whole request risked repeating text already shown to the user or executing tools twice, while partial answers could be lost.

**Solution**: Separated recovery by whether a step had been shown to the user. Buffered each unshown research step per attempt and discarded it before a safe retry. For streamed final answers, passed the generated text back as context and requested only a continuation, with a retry limit. Detected overlap when a model restarted from the beginning to prevent duplicate text. If generation still failed, preserved the partial answer and notified the client with an `incomplete` status.

This led me to design streaming recovery around **what output or side effects have already reached the user or external systems**, as well as whether a request can be retried.

### 5. Provider-Specific Tool Calling Schemas Causing Chat Failures
([ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI)) | Python / FastAPI / OpenAI-compatible APIs / Anthropic / Tool Calling | Solo

**Challenge**: Reusing the same tool definition across LLM providers caused failures when some OpenAI-compatible providers strictly validated generated arguments against JSON Schema. For example, a model could return the common language code `ja` while the search API required `jp`; missing required fields or extra fields could also stop the entire turn.

**Solution**: Relaxed constraints such as `enum` and strict `required` fields in the provider-facing schema, then centralized validation and normalization in the application, including language codes and date ranges, with safe defaults where possible. Classified provider tool-call rejections separately from API failures and retried only the affected step without the tool, allowing the conversation to continue.

This showed that **tool schemas should guide model output, while the application owns authoritative validation and normalization**.

### 6. Low Prompt Cache Hits — Reducing Cost Through Prompt Structure
([ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI)) | LLM APIs / Prompt Engineering / Cost Optimization | Solo

**Challenge**: Long chats repeatedly sent the same history to LLMs, increasing input costs, yet prompt caches from OpenAI, Anthropic, and Groq rarely hit. Dynamic values such as the current time and per-step `TurnState` appeared near the start of the prompt, breaking the matching prefix and invalidating the cache for everything after them.

**Solution**: Reordered prompts as fixed instructions, conversation history, changing turn state, and the latest user input. Kept tool definitions stable within a turn where possible. Encapsulated provider-specific cache behavior in the LLM adapter and included cache read/write price differences in usage tracking.

This reinforced that **LLM cost optimization depends on prompt structure and the placement of changing content, as well as model choice and token count**.

</details>

## 🛠️ Skills
| Category | Technologies |
| :--- | :--- |
| **Programming Languages** | Python, TypeScript, SQL |
| **Web / Application Frameworks** | FastAPI, React, Next.js, Tailwind CSS |
| **Data Stores** | PostgreSQL, Redis |
| **AI / LLM Engineering** | RAG, Multi-Agent Systems, LangChain, LangGraph, browser-use |
| **Infrastructure** | Docker, AWS (EC2, VPC, Systems Manager), Linux, Nginx |
| **Development / Testing** | Git, GitHub Actions, pytest |
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


## 💼 Experience
**GMO Media** — AI Engineering Intern
- **AI butler chat feature**: Added chat while preserving the existing choice-based flow. Owned conversation control, prompt design, and reliability; implemented support for changing goals and missing information, progress display and state recovery, duplicate-submission prevention and retries, and usage and cost limits.
- **Team development and production delivery**: Worked in the production repository on dedicated branches, participated in code reviews, and carried the feature through production deployment.
- **Chat processing concurrency control**: Kept infrastructure unchanged and capped concurrent chat turns. At the limit, released the worker thread and re-enqueued the chat job after 10 seconds, reserving capacity for email delivery and LINE webhooks.
- **Evaluation using real usage data**: Analyzed choice-based AI butler usage and defined, with the team, KPIs/KGIs comparing completion and action-execution rates across choice-based and chat flows. Prepared MySQL aggregation SQL with a 48-hour evaluation rule.

**kubell** — Summer Intern
- **Problem discovery**: Interviewed model users in the construction industry, synthesized their operational challenges, and prioritized the burden and inconsistent quality of field-report entry.
- **Requirements and team development**: Targeted shorter report-writing time by breaking the workflow into four stages and prioritizing user stories. Refined the problem and features through daily sprint reviews, then built and demoed report templates, AI drafts from chat history, voice input, task management with assignees, deadlines, and progress tracking, and AI-generated image descriptions.
- **AI-assisted delivery**: Used AI to accelerate implementation and validation as well as code generation, contributing end-to-end from user-problem discovery and requirements definition through implementation and validation.

**Manaable Inc.** — Software Engineering Intern
- **System design and development**: Joined as an intern after the joint research to bring its findings into production, designing and developing an internal AI agent for the customer support team on **AWS**.
- **Hybrid RAG pipeline**: Converted and structured Jira operations manuals into Markdown, then built a **BM25 + vector search** pipeline. Refined prompts for **gpt-5.1-mini** and delivered natural-language Q&A through a chat UI.
- **Workflow integration and iteration**: Added automatic ticket creation through the Jira API and customer-facing email drafts alongside RAG answers. Worked with the support team in daily discussions, iterating from requirements definition through response-quality improvement.

## 🎓 Education
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

## 🔬 Research

### Object Routing — Current Research
**Research repository:** [Marmo-Core](https://github.com/kota-kawa/Marmo-Core)

I study how AI agents can select a task-relevant set of resources from large catalogs. Memory, Skills, Tools, and Agents are represented through a common resource model. Beyond retrieval relevance, routing must account for whether the selected resources are necessary and can be executed safely, considering dependencies, conflicts, and permissions.

- **Retrieval and ranking:** BM25, embedding, and hybrid retrieval, with HyDE and LLM reranking.
- **Execution-aware selection:** Selecting resources while accounting for dependencies, conflicts, and execution permissions.
- **Fallback decisions:** Abstaining when no suitable resource exists and requesting elevated permissions when required access is missing.
- **Scale:** Hierarchical routing for catalogs of up to 100,000 resources.

### NCSP'26
**2026 RISP International Workshop on Nonlinear Circuits, Communications and Systems**

**Mar 2026 | Honolulu, Hawaii**

Presented research on an **AI Multi-Agent Orchestration System** in an English oral session. Developed a system integrating five specialized agents: **RAG**, **Web Operation**, **IoT**, **Scheduler**, and **Orchestrator**. Combining long- and short-term memory improved the overall evaluation score by about **1.7×**.

→ [Presentation slides](https://project-kk.com/static/research/NCSP-Presentation-EN.pdf)

### RAG System Optimization — Joint Research at Manaable Inc.
**Patent pending | FIT 2025 (Forum on Information Technology)**

The research examined three areas: masking personally identifiable information in Q&A data, validating masked data with multiple LLMs, and evaluating storage formats for RAG. The findings, including improved answer accuracy, were presented at FIT 2025 and led to a co-filed patent.

**FIT 2025 paper (F-029):** [On Database Structures for Retrieval-Augmented Generation in AI Chatbots](https://www.ieice.org/publications/conference-FIT-DVDs/FIT2025/data/html/program/pdf/F-029.pdf)

**Presentation slides:** [FIT 2025 presentation](https://project-kk.com/static/research/FIT発表資料.pdf)

## 🏆 Activities

### Matsuo Lab (The University of Tokyo) Programs & Competitions (2024–2025)
- **LLM Course Final Project & Competition**: Developed fine-tuned models using **LoRA SFT** and **DPO**, achieving a **top 4% (70 / 1800) ranking**. Featured model: [Llama-3.1-8B-Instruct-Freedom_v3](https://huggingface.co/kota-kawa/Llama-3.1-8B-Instruct-Freedom_v3).
- **LLM Competition 2025**: As the team's training data lead, built and published a high-difficulty synthetic dataset for mathematical reasoning ([difficult_math_deepseek_llama](https://huggingface.co/datasets/kota-kawa/difficult_math_deepseek_llama)).
- **Specialized Courses**: Took courses including AI Management (PwC joint), LLM, GCI (Data Science), Deep Learning, and Deep Generative Models.

### Gemini 3 Tokyo Hackathon 2026
Completed a mystery game powered by **Gemini** and **Nano Banana** within the 7-hour time limit. → [Gemini3-Hackathon-Mystery-Game](https://github.com/kota-kawa/Gemini3-Hackathon-Mystery-Game)

## 🌐 Language
- **Japanese**: Native
- **English**: Professional Proficiency (TOEIC 715, 1-year academic study in US)

## 📝 Notes
- Last updated: 2026-09-23
- License: All rights reserved

<details>
  <summary>日本語版（クリックで展開）</summary>

# Resume（職務経歴/履歴書） — 川越 航太

## 📄 ダウンロード
- 📄 Resume（PDF）：[JP](https://project-kk.com/static/pdf/resume-jp.pdf) | [EN](https://project-kk.com/static/pdf/resume-en.pdf)
- 🌐 Portfolio：<https://project-kk.com/>
- 💼 LinkedIn：<https://www.linkedin.com/in/kota-kawa/>
- ✉️ Email：kota7kawagoe@gmail.com

## 🚀 実際に動いているサービス
- **ChatCore-AI**: <https://chatcore-ai.com/> (本番運用AIチャットプラットフォーム & プロンプト共有)
- **FS-QR**: <https://fs-qr.net/> (ファイル共有 & QR)

### **志望：AIアプリケーションエンジニア / バックエンドシステム開発。**

## 👤 サマリー

慶應義塾大学大学院SFCでAIエージェントを研究する傍ら、AIシステムの研究から本番Webサービスの設計・開発・運用まで取り組むソフトウェアエンジニアです。

関心の中心は、LLMそのものだけでなく、LLMを実用的なアプリケーションにつなぐシステム設計です。必要なMemory / Skill / Tool / Agentの選択、安全な外部ツール実行、会話やユーザーコンテキストの管理、LLM・外部APIの障害からの復旧、推論コストや利用量の制御などに取り組み、AI機能を本番環境で安定して運用できる形にします。

現在は、次の2領域を軸に活動しています。
- **本番AIアプリケーション**：[ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI)など、公開・運用中のAIサービスの設計・開発・改善。
- **AIエージェント研究**：大規模なリソース群から実行可能なリソース集合を選択するObject Routingの研究と、Memory / Skill / Tool / Agentを統一的に扱うOSSライブラリ[Marmo-Core](https://github.com/kota-kawa/Marmo-Core)の開発。

インターンや個人サービスを通じて、課題発見・要件定義・設計・実装・テスト・コードレビュー・本番デプロイ・実利用データに基づく評価まで経験しています。

## 🧩 主要プロジェクト（おすすめ順）
### 1) [ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI) — (本番運用AIチャットプラットフォーム)
- 概要：FastAPIとNext.jsで構築し、実際に公開・運用しているAIチャットプラットフォーム。複数LLMのストリーミング応答、Web調査・ツール利用、Task / Skill、永続コンテキスト、プロンプト共有、生成UIを実装。Redisによるセッション管理、利用量・コスト制御、SSE障害時の復旧、テスト、CI/CDまで含め、本番運用を前提に設計・改善。
- デモ：<https://chatcore-ai.com/>
- 技術：Python, FastAPI, Next.js, React, TypeScript, PostgreSQL, Redis, Docker, Nginx, GitHub Actions, OpenAI / Anthropic / Groq.

### 2) [Marmo-Core](https://github.com/kota-kawa/Marmo-Core) — (AIエージェント向けリソースカーネル)
- 概要：AIエージェント向けリソースの登録・検索・選択・安全な実行を担う軽量なPythonカーネル。ポリシーによる実行制御、監査ログ、決定論的なモック実行、CLIツール、OpenAI互換／Anthropic LLMプロバイダーを備える。
- 技術：Python, リソースレジストリ, ポリシーレイヤー, Lexical/HyDE検索, CLI, OpenAI/Anthropic API.

### 3) [Browser-Agent](https://github.com/kota-kawa/Browser-Agent) — (Web UI付きブラウザ自動化エージェント)
- 概要：`browser_use`を**FastAPI**と**noVNC**でラップした、Web UI付きブラウザ自動化エージェント。自然言語による操作とWebArenaベンチマーク評価に対応。WebArena Shoppingタスク成功率: 32.6% (N=187, 最大ステップ数=40, リトライ回数=4, 同一プロンプト設定)。
- 技術：Python, FastAPI, Docker, `browser_use`, noVNC, Gemini/OpenAI/Anthropic.

<details>
  <summary><b>その他のプロジェクト（クリックで展開）</b></summary>

### [Symphony Agent Conductor](https://github.com/kota-kawa/Symphony-Agent-Conductor) — (自律型エージェントオーケストレーション)
- 概要：**LangGraph**を用いた中央オーケストレーターを構築し、ブラウザ操作やIoT制御を行う専門エージェントを協調動作させることで、デジタル作業と物理デバイス制御のシームレスな連携を実現。
- 技術：Python, Flask, LangGraph, `browser-use`, IoT (Jetson/Pi), OpenAI/Gemini.

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

**解決策**: LLMに日付を計算させるのをやめ、役割を分離した。LLMの担当はユーザーの自然言語の意図を読み取ること（「来週の金曜」がどの曜日を指すかを判断すること）に限定し、実際の日付計算は常に正しい結果を返す専用の決定論的な関数群に委ねる設計に変更した。これにより日付計算をモデルの役割から切り離した。また、OpenAI・Anthropic・Gemini・Groqの9モデルで10タスクのベンチマーク評価を実施し、同一条件下で中堅モデルが複数のフロンティアモデルを上回る精度を出した。

### 2. 本番環境で発覚した障害 — nginxの通信設定とデプロイ時の準備確認
([ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI), [FS-QR](https://github.com/kota-kawa/fs-qr)) | Python / FastAPI / Next.js / Redis / nginx / Docker / GitHub Actions | 個人開発

ローカル開発では見つからなかった障害が本番環境で発生した。nginxを経由することでストリーミングと持続接続の動作が変わり、デプロイ時にはアプリケーションの準備完了前に通信を切り替えていた。

**SSE（ChatCore-AI）**: LLMのトークン逐次配信をSSEで実装したところ、本番環境ではレスポンスがバッファリングされ全文一括表示になった。原因はnginxのデフォルトのレスポンスバッファリング。`proxy_buffering off`と`X-Accel-Buffering: no`の追加で解決。

**WebSocket（FS-QR）**: テキストのリアルタイム同期をWebSocketで実装したところ、本番環境でWebSocket接続が確立できなかった。nginxがデフォルトでHTTP/1.0を使用しており、WebSocketハンドシェイクに必要な`Upgrade`ヘッダーが転送されていなかったことが原因。`location`ブロックに`proxy_http_version 1.1`・`proxy_set_header Upgrade $http_upgrade`・`proxy_set_header Connection "upgrade"`・タイムアウト延長を追加して解決。複数インスタンス間のブロードキャストにはRedis Pub/Subを採用した。

**Blue-Greenデプロイ（ChatCore-AI）**: 新しいDockerコンテナの起動を確認してnginxの向き先を切り替えたところ、アプリケーションの起動が完了しておらず、切り替え時に一瞬だけ500エラーが発生した。デプロイスクリプトにアプリケーションのエンドポイントが200を返すまで待つヘルスチェックを追加し、その後にnginxの設定を更新・再読み込みするようにした。

これらの経験から、ストリーミングと持続接続は本番相当のプロキシ構成で検証し、新しいインスタンスへ通信を切り替える前にはアプリケーションの準備完了を確認するようにした。

### 3. OSSの内部状態汚染 — 前のタスクの残留状態が次タスクに干渉する問題
([Browser-Agent](https://github.com/kota-kawa/Browser-Agent)) | Python / FastAPI / Docker / browser_use / noVNC | 個人開発

**苦労したこと**: 効率化のためブラウザセッションをタスク間で使い回す設計を採用したところ、前のタスク終了後にライブラリ内部に残留した状態が次タスクの実行に干渉するという問題が発生した。セッションを完全に終了させると次のタスクが実行できなくなり、そのままにすれば状態が積み上がってクラッシュする。どちらの選択肢も機能しなかった。

**解決策**: ライブラリには内部状態をリセットするための公開APIが存在しなかったため、ソースコードを直接読み込んで内部構造を把握し、タスク終了ごとに状態をリセットするクリーンアップ処理を独自実装した。さらにライブラリのバージョンによって内部構造が異なるため、バージョンに応じて動作を切り替えるフォールバックロジックも追加し、どのバージョンでも正常に動作するようにした。**公開APIの限界に当たったときはドキュメントではなくソースコードを読む** という判断の重要性を学んだ。

### 4. 長時間LLM生成の途中切れ・再試行・重複実行への対処
([ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI)) | Python / FastAPI / SSE / Redis / LLM API | 個人開発

**苦労したこと**: Web検索や複数回のツール利用を伴う長時間のチャットでは、出力上限や一時的なAPI障害により生成が途中で止まることがあった。リクエスト全体を再実行すると、ユーザーに表示済みの文章やツール呼び出しが重複し、途中までの回答が失われる場合もあった。

**解決策**: ユーザーへの表示前後で回復方法を分けた。未表示の調査ステップは試行単位でバッファし、失敗時に破棄して安全に再実行。表示を始めた最終回答は、生成済み本文を履歴として渡して続きだけを回数制限付きで生成し、先頭から再生成された場合は重複部分を検出して除去した。完了できない場合も途中までの本文を保存し、クライアントへ`incomplete`状態を通知した。

ストリーミングの障害回復では、再試行の可否に加え、**ユーザーや外部システムに出た出力・副作用をどこまで戻せるか**を考慮して設計する必要があると学んだ。

### 5. LLMプロバイダごとのTool Calling仕様差によるチャット失敗
([ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI)) | Python / FastAPI / OpenAI互換API / Anthropic / Tool Calling | 個人開発

**苦労したこと**: 同じTool定義を複数プロバイダへ渡したところ、一部のOpenAI互換プロバイダが生成引数をJSON Schemaで厳格に検証し、形式のわずかな違いでチャット全体が失敗した。例えば検索APIが`jp`を要求する言語指定で、モデルが一般的な`ja`を返すと拒否された。必須項目の欠落や余分な項目でも同様にターンが停止する可能性があった。

**解決策**: Adapter層では`enum`や厳格な`required`などの制約を緩め、Tool Schemaをモデルへの誘導として扱った。入力検証・正規化はアプリケーション側に集約し、言語コードや期間指定を整え、不正値には可能な範囲で安全な既定値を適用した。プロバイダによるTool Call拒否は通常のAPI障害と分けて扱い、該当ステップだけToolなしで再実行して会話を継続できるようにした。

この経験から、**モデルへのTool Schemaとアプリケーション側の厳密な入力検証を分離すること**が可用性のために重要だと学んだ。

### 6. Prompt Cacheの低い命中率 — プロンプト構造によるコスト最適化
([ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI)) | LLM API / プロンプト設計 / コスト最適化 | 個人開発

**苦労したこと**: 長い会話では同じ履歴を繰り返しLLMへ送るため入力コストが増える一方、OpenAI・Anthropic・GroqのPrompt Cacheがほとんど命中しなかった。現在時刻や各ステップで変わる`TurnState`をプロンプトの先頭近くに置いていたため、キャッシュが必要とするprefix一致が崩れ、その後の内容も再利用されなかった。

**解決策**: プロンプトを「固定指示 → 会話履歴 → 変化するターン状態 → 最新のユーザー入力」の順に再構成し、可能な範囲で1ターン中のTool定義も固定した。プロバイダごとのキャッシュ方式をLLM Adapter層に集約し、キャッシュ読み書きの料金差も利用量計測に反映した。

この経験から、**LLMのコストはモデルやトークン数だけでなく、変化する情報をプロンプトのどこに置くかにも左右される**と学んだ。

</details>

## 🛠️ スキル
| カテゴリ | 技術 |
| :--- | :--- |
| **プログラミング言語** | Python, TypeScript, SQL |
| **Web / アプリケーションフレームワーク** | FastAPI, React, Next.js, Tailwind CSS |
| **データストア** | PostgreSQL, Redis |
| **AI / LLM エンジニアリング** | RAG, Multi-Agent Systems, LangChain, LangGraph, browser-use |
| **インフラ** | Docker, AWS (EC2, VPC, Systems Manager), Linux, Nginx |
| **開発・テスト** | Git, GitHub Actions, pytest |
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

## 💼 経験
**GMOメディア** — AIエンジニアインターン
- **AI執事のチャット機能**：既存の選択式フローを保ちながらチャット機能を追加。会話制御・プロンプト・堅牢性を担当し、希望変更や情報不足への対応、進捗表示・状態復元、二重送信防止・エラー時の再試行、利用上限・コスト制御を実装。
- **チーム開発・本番リリース**：本番リポジトリで専用ブランチを使ってチーム開発し、コードレビューを経て本番デプロイまで完走。
- **チャット処理の同時実行制御**：インフラ設定を変えず、実行中のチャットターン数に上限を設定。上限到達時はワーカースレッドを解放してジョブを10秒後にキューへ戻し、メール送信・LINE Webhook用の処理枠を確保。
- **実利用データによる効果測定**：選択式AI執事の利用履歴を分析し、選択式とチャット式の完了率・アクション実行率を比較するKPI/KGIをチームで定義。48時間の判定ルールを組み込んだMySQL集計SQLを整備。

**kubell** — サマーインターン
- **課題発見**：建設業のモデルユーザーへのヒアリングから業務課題を整理し、現場報告の入力負担と品質のばらつきを優先課題として特定。
- **要件定義・チーム開発**：「報告書作成時間の最小化」を目標に、報告業務を4段階に分解。ユーザーストーリーと優先度を整理し、日次スプリントのレビューを通じて課題・機能を見直しながら、報告テンプレート、履歴からのAI下書き、音声入力、担当者・期限・進捗を管理するタスク機能、画像へのAI説明付与をチームで開発・デモ。
- **AI活用・一貫開発**：AIをコード生成だけでなく実装・検証の効率化にも活用し、課題発見から要件定義・実装・検証まで一貫して経験。

**Manaable 株式会社** — ソフトウェアエンジニアインターン
- **設計・開発**：共同研究の成果をプロダクト化するためインターンに参加し、AWS上でカスタマーサポート向け社内AIエージェントを設計・開発。
- **ハイブリッドRAG**：Jiraの操作マニュアルをMarkdown化・構造化し、BM25とベクトル検索を組み合わせたパイプラインを構築。`gpt-5.1-mini`のプロンプトを調整し、チャットUIで自然言語の問い合わせに回答。
- **機能拡張・改善**：Jira APIによる問い合わせチケットの自動起票と、RAG回答に添える顧客向けメール文案の生成を実装。サポートチームと毎日議論し、要件定義から応答品質まで反復改善。

## 🎓 学歴
- **慶應義塾大学大学院 湘南藤沢キャンパス（SFC）** — 政策・メディア研究科 サイバーインフォマティクス専攻 修士課程
  - 神奈川県 | 2026年4月 –
- **神奈川工科大学** — 情報学部 情報ネットワークコミュニケーション学科 学士
  - 神奈川県 | 2021年4月 – 2026年3月（うち1年休学）
  - **卒業論文**：[EN](https://project-kk.com/static/research/Graduation-Research-Paper-en.pdf) | [JP](https://project-kk.com/static/research/Graduation-Research-Paper-ja.pdf)
- **University of North Alabama** — 交換留学プログラム修了
  - アラバマ州, 米国 | 2023年6月 – 2024年5月
  - **栄誉**: **成績優秀者（Dean's List）** 選出（2023年秋期、GPA: 3.75/4.0）
  - **実績**: **AI（人工知能）** 授業の最終プロジェクトでクラス**1位**（30人中）。OpenCV・TensorFlowで顔認証ログインシステムを開発。
  - **主要履修科目**: 人工知能 (AI), HCI/UX, デザイン I & II, コンピュータ応用。

## 🔬 研究

### Object Routing（現在の研究）
**研究リポジトリ：** [Marmo-Core](https://github.com/kota-kawa/Marmo-Core)

Memory / Skill / Tool / Agentを共通のリソースモデルで扱い、大規模なカタログからタスク実行に必要なリソース集合を選択するObject Routingを研究しています。検索精度に加え、選択したリソースを安全に実行できるかを、依存関係・競合制約・実行権限まで含めて判断します。

- **候補検索・ランキング**：BM25、Embedding、Hybrid Retrieval、HyDE、LLM Reranking
- **実行可能な集合の選択**：依存関係・競合制約・実行権限を考慮したリソース選択
- **適切な候補がない場合の判断**：該当するリソースがなければ棄権し、必要な権限が不足していれば権限昇格を要求
- **大規模化**：最大10万件規模のカタログを対象とする階層ルーティング

### NCSP'26
**2026 RISP International Workshop on Nonlinear Circuits, Communications and Systems**

**2026年3月 | Honolulu, Hawaii**

「AIマルチエージェント・オーケストレーションシステム」に関する研究成果を英語で口頭発表しました。RAG、Web操作、IoT、Scheduler、Orchestratorの5種類の専門エージェントを統合したシステムを開発し、長期・短期メモリを組み合わせた構成で総合評価スコアを約**1.7倍**に改善しました。

→ [発表資料](https://project-kk.com/static/research/NCSP-Presentation-EN.pdf)

### RAGシステム最適化 — Manaable 株式会社との共同研究
**特許出願中 | FIT 2025（第24回情報科学技術フォーラム）**

Q&Aデータの個人情報マスキング、マスキング済みデータの複数LLMによる検証、RAG向けデータ保存形式の評価を実施しました。回答精度の向上を含む研究成果をFIT 2025で発表し、成果をもとに特許を共同出願しました。

**FIT 2025論文（F-029）：** [RAG として AIChatBot に与えるデータベースの構造に関する一考察](https://www.ieice.org/publications/conference-FIT-DVDs/FIT2025/data/html/program/pdf/F-029.pdf)

**発表資料：** [FIT 2025発表資料](https://project-kk.com/static/research/FIT発表資料.pdf)

## 🏆 活動歴

### 松尾研究室（東京大学）関連プログラム・コンペティション（2024年–2025年）
- **LLM講座 最終プロジェクト & コンペティション**: LoRA SFTおよびDPOを用いたモデルを開発し、コンペティションにて上位4% (70 / 1800) に入賞。開発モデル：[Llama-3.1-8B-Instruct-Freedom_v3](https://huggingface.co/kota-kawa/Llama-3.1-8B-Instruct-Freedom_v3)
- **LLMコンペ2025**: チーム内で学習データ作成を担当し、数学的推論向け高難度合成データセットを構築・公開（[difficult_math_deepseek_llama](https://huggingface.co/datasets/kota-kawa/difficult_math_deepseek_llama)）。
- **専門講座受講**: AI経営講座（PwC共同開催）、LLM講座、GCI (データサイエンス基礎)、深層学習、深層生成モデル。

### Gemini 3 東京ハッカソン 2026
**Gemini** と **Nano Banana** を活用したミステリゲームを、7時間の制限時間以内に完成させました。→ [Gemini3-Hackathon-Mystery-Game](https://github.com/kota-kawa/Gemini3-Hackathon-Mystery-Game)

## 🌐 語学
- **日本語**: ネイティブ
- **英語**: ビジネスレベル (TOEIC 715, 米国大学での1年間の留学経験)

## 📝 補足
- 最終更新：2026-09-23
- ライセンス：All rights reserved
</details>
