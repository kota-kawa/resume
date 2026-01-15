# resume

# Resume — <Your Name>

## Download
- 📄 Resume (PDF): [JP](./resume_ja.pdf) | [EN](./resume_en.pdf)
- 🌐 Portfolio: <https://project-kk.com/>
- 💼 LinkedIn: <URL>
- ✉️ Email: <you@example.com>

## Summary
Software Engineer focused on **Autonomous AI Agents** and **Privacy-First RAG Systems**.
Strengths: Multi-Agent Architecture (LangGraph), Secure Personal Knowledge Management, Full-Stack Python Development.
Looking for: Roles in AI Application Engineering or Backend Systems.

## Key Projects (recommended order)
### 1) Multi-Agent System — <Autonomous Orchestration Platform>
- Problem: Complex tasks require coordination between specialized agents (Web, IoT, Scheduling) which is hard to manage manually.
- Solution: Built a central orchestrator using **LangGraph** to coordinate distinct agents (Browser automation, IoT control, RAG).
- Result: Achieved seamless interaction between digital web tasks and physical device control.
- Repo: `Multi-Agent/`
- Tech: Python, Flask, LangGraph, `browser-use`, IoT (Jetson/Pi), OpenAI/Gemini.
- How to run:
  - `cd Multi-Agent-Platform`
  - `docker compose up --build`
  - open: `http://localhost:5050`

### 2) MemoScribe — <Personal Life Secretary with RAG>
- Problem: Using AI for personal knowledge management carries privacy risks and "hallucination" issues.
- Solution: Developed a self-hosted **Django** app with local RAG, PII masking, and strict "evidence-based" citations.
- Result: Secure, private personal assistance with verifiable answers from own notes/docs.
- Repo: `MemoScribe/`
- Tech: Django 5, PostgreSQL (pgvector), Celery, Redis, OpenAI.
- How to run:
  - `cp .env.example .env`
  - `docker compose up --build`
  - open: `http://localhost:8000`

### 3) fs-qr — <Frictionless Local File Sharing>
- Problem: Sharing files between devices on a local network often requires login or cloud upload.
- Solution: Created a **FastAPI** service for instant file/note sharing via QR codes and ephemeral rooms.
- Result: Instant, secure local transfer without account registration.
- Repo: `fs-qr/`
- Tech: Python, FastAPI, SQLAlchemy, Docker, Jinja2.
- How to run:
  - `docker compose up --build`
  - open: `http://localhost:5000`

## Skills (ship-ready)
- **AI/Agents**: Multi-Agent Systems (LangGraph), RAG (LangChain/LlamaIndex, FAISS/pgvector), Browser Automation (`browser-use`), LLM Integration.
- **Backend**: Python (Flask, Django, FastAPI), Microservices Architecture, REST/GraphQL.
- **Frontend**: React (Vite), Jinja2 (SSR), CSS (BEM), Modern JS.
- **Infra/DevOps**: Docker (Compose), `uv` (Package Management), PostgreSQL, Redis, CI/CD pipelines.
- **Quality**: `pytest`, `ruff`, `black`, PII Masking/Security-first design.

## Experience
- <Company/Team> — <role> (YYYY-MM–YYYY-MM)
  - <impact bullet 1>
  - <impact bullet 2>

## Education
- <University> — <Degree> (YYYY–YYYY)

## Notes
- Personal data such as full address/phone is intentionally omitted.
- Last updated: YYYY-MM-DD
- License: All rights reserved (or CC BY 4.0)

<details>
  <summary>日本語版（クリックで展開）</summary>

# Resume（職務経歴/履歴書） — <Your Name>

## ダウンロード
- 📄 Resume（PDF）：[JP](./resume_ja.pdf) | [EN](./resume_en.pdf)
- 🌐 Portfolio：<URL>
- 💼 LinkedIn：<URL>
- ✉️ Email：<you@example.com>

## サマリー
**自律型AIエージェント**と**プライバシー重視のRAGシステム**に注力するソフトウェアエンジニア。
強み：マルチエージェントアーキテクチャ設計 (LangGraph)、セキュアな個人知識管理 (PKM)、Pythonフルスタック開発。
志望：AIアプリケーションエンジニア / バックエンドシステム開発。

## 主要プロジェクト（おすすめ順）
### 1) Multi-Agent System — <自律型エージェントオーケストレーション>
- 課題：Web操作、IoT制御、スケジュール管理など、異なるドメインのタスクを統合的に自動化する難しさ。
- 解決：**LangGraph**を用いた中央オーケストレーターを構築し、ブラウザ操作や物理デバイス制御を行う専門エージェントを協調動作させるシステムを開発。
- 成果：デジタル作業と物理的なデバイス制御のシームレスな連携を実現。
- Repo: `Multi-Agent/`
- 技術：Python, Flask, LangGraph, `browser-use`, IoT (Jetson/Pi), OpenAI/Gemini.
- 動かし方：
  - `cd Multi-Agent-Platform`
  - `docker compose up --build`
  - open：`http://localhost:5050`

### 2) MemoScribe — <RAG搭載・個人用秘書アプリ>
- 課題：個人の知識やメモをAIに活用させる際のプライバシーリスクと、ハルシネーション（嘘）の問題。
- 解決：**Django**製のセルフホスト型アプリを開発。ローカルRAG、PII（個人情報）マスキング、そして回答の根拠を必ず提示する機能を実装。
- 成果：プライバシーを守りつつ、自分の過去の記録に基づいた正確なアシスタント機能を実現。
- Repo: `MemoScribe/`
- 技術：Django 5, PostgreSQL (pgvector), Celery, Redis, OpenAI.
- 動かし方：
  - `cp .env.example .env`
  - `docker compose up --build`
  - open：`http://localhost:8000`

### 3) fs-qr — <ローカル完結型・高速ファイル共有>
- 課題：クラウドを経由せずに、近くのデバイスと素早くファイルを共有したい（ログイン不要で）。
- 解決：**FastAPI**を用いた、QRコード生成と使い捨てルームによるファイル共有サービスを構築。
- 成果：アカウント登録不要で、セキュアかつ瞬時にローカルネットワーク内での共有が可能に。
- Repo: `fs-qr/`
- 技術：Python, FastAPI, SQLAlchemy, Docker, Jinja2.
- 動かし方：
  - `docker compose up --build`
  - open：`http://localhost:5000`

## スキル（実装して出せる）
- **AI/Agents**: マルチエージェントシステム (LangGraph), RAG (LangChain/LlamaIndex, FAISS/pgvector), ブラウザ自動化 (`browser-use`), LLM連携.
- **Backend**: Python (Flask, Django, FastAPI), マイクロサービスアーキテクチャ, REST/GraphQL.
- **Frontend**: React (Vite), Jinja2 (SSR), CSS (BEM), Modern JS.
- **Infra/DevOps**: Docker (Compose), `uv` (パッケージ管理), PostgreSQL, Redis, CI/CDパイプライン.
- **Quality**: `pytest`, `ruff`, `black`, PIIマスキング/セキュリティ・バイ・デザイン.

## 経験
- <Company/Team> — <role>（YYYY-MM–YYYY-MM）
  - <成果1>
  - <成果2>

## 学歴
- <University> — <Degree>（YYYY–YYYY）

## 補足
- 住所/電話などの個人情報は意図的に省略しています。
- 最終更新：YYYY-MM-DD
- ライセンス：All rights reserved（または CC BY 4.0）
</details>
