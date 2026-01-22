# resume

# Resume — <Your Name>

## Download
- 📄 Resume (PDF): [JP](./resume_ja.pdf) | [EN](./resume_en.pdf)
- 🌐 Portfolio: <https://project-kk.com/>
- 📝 Blog: <https://blog.project-kk.com/>
- 📘 Zenn: <https://zenn.dev/kota_kawa>
- 🐦 X (Twitter): <https://x.com/project_kk_ai>
- 💼 LinkedIn: <https://www.linkedin.com/in/kota-kawagoe-0a22263a7/>
- ✉️ Email: kota7kawagoe@gmail.com

## Summary
Software Engineer focused on **Autonomous AI Agents** and **Privacy-First RAG Systems**.

**Core Strength: End-to-End Problem Solving**
I excel at organizing surrounding challenges and user needs, translating them into intuitive UI/UX designs even when requirements are ambiguous, and leading development through to implementation. 

**Experience:**
In my university lab, I independently identified operational inefficiencies, gathered requirements from peers, and developed custom tools. I continuously refined these through user feedback, demonstrating a proactive approach to system improvement and user-centric development.

**Technical Strengths:**
Multi-Agent Architecture (LangGraph), Secure Personal Knowledge Management, Full-Stack Python Development.

Looking for: Roles in AI Application Engineering or Backend Systems.

## Key Projects (recommended order)
### 1) [Symphony Agent Conductor](https://github.com/kota-kawa/Symphony-Agent-Conductor) — <Autonomous Orchestration Platform>
- Summary: An autonomous orchestration platform using **LangGraph** to coordinate specialized agents (Browser automation, IoT control, RAG) for seamless interaction between digital tasks and physical device control.
- Tech: Python, Flask, LangGraph, `browser-use`, IoT (Jetson/Pi), OpenAI/Gemini.

### 2) [MemoScribe](https://github.com/kota-kawa/MemoScribe) — <Personal Life Secretary with RAG>
- Summary: A self-hosted **Django** application acting as a personal life secretary. Features local RAG, PII masking, and strict "evidence-based" citations to ensure secure, private assistance without hallucination.
- Tech: Django 5, PostgreSQL (pgvector), Celery, Redis, OpenAI.

### 3) [Browser-Agent](https://github.com/kota-kawa/Browser-Agent) — <LLM-powered Browser Automation with Web UI>
- Summary: An LLM-powered browser automation agent wrapping `browser_use` with a **FastAPI** backend and **noVNC** web interface. Supports natural language control, real-time visualization, and WebArena benchmarks.
- Tech: Python, FastAPI, Docker, `browser_use`, noVNC, Gemini/OpenAI/Anthropic.

<details>
  <summary><b>Other Projects (Click to expand)</b></summary>

- **File-Sharing & Collab Tool**: A self-hosted file sharing and collaborative editing tool built with **FastAPI**. Features instant mobile transfer via QR codes, password-protected group sharing, and real-time synchronized notes via WebSockets for privacy-focused information sharing.
  - Tech: FastAPI, MySQL, Redis, WebSockets, SQLAlchemy, Docker, APScheduler.
- **Personal RAG Secretary**: A self-hosted personal secretary application built with **Django**. Features local RAG, PII masking, and evidence-based responses to provide accurate knowledge management and assistance while protecting privacy.
  - Tech: Python 3.12, Django 5, PostgreSQL (pgvector), Celery, Redis, OpenAI API, Docker.
- **AI Knowledge Platform**: An integrated platform for AI chat, prompt sharing, and note management built with **FastAPI** and **Next.js**. It features advanced dialogue via Gemini API, community prompt sharing, and personal note functions to balance knowledge sharing with individual productivity.
  - Tech: FastAPI, Next.js, PostgreSQL, Gemini API (OpenAI SDK), Docker, Tailwind CSS.
- **Multi-Purpose AI Agent Platform**: A versatile AI agent platform built with **Flask** and **React 19**. Provides domain-optimized AI chat for travel, health, work, and learning, featuring content moderation via Llama Guard and strict security management (CSRF/CSP) for a secure interaction and planning environment.
  - Tech: Flask, React 19, PostgreSQL, Redis, OpenAI/Groq API (Llama Guard), Docker.
</details>

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
- **Kanagawa Institute of Technology** — Bachelor of Science (Expected)
  - Kanagawa, Japan | Apr 2021 – Mar 2026
- **University of North Alabama** — International Exchange Program
  - Alabama, USA | Jun 2023 – May 2024
  - **Honors**: **Dean's List** (Fall 2023, GPA: 3.75/4.0).
  - **Achievement**: Ranked **1st in class** for the final project in the **Artificial Intelligence** course.
  - **Design Portfolio**: [project-kk.com/design](https://project-kk.com/design) (Works from Design I & II, Layout and Design)
  - **Relevant Coursework**: Artificial Intelligence, Intro to HCI/UX, Design I & II, Layout and Design, Computer Skills for Problem Solving.

## Achievements & Activities
- **Matsuo Lab LLM Competition 2025** (2025)
  - Responsible for dataset creation within the team, focusing on high-difficulty mathematical reasoning.
  - Leveraged an **H100 cluster** to generate a high-difficulty synthetic dataset using DeepSeek and Llama models.
  - Achieved measurable performance gains after fine-tuning, demonstrating the effectiveness of the high-quality, small-scale dataset.
  - Dataset: [difficult_math_deepseek_llama](https://huggingface.co/datasets/kota-kawa/difficult_math_deepseek_llama)
- **Matsuo Lab LLM Course Final Project & Competition**
  - Completed a comprehensive course covering LLM fundamentals (pre-training) to AI agent applications.
  - Developed fine-tuned models/adapters using **LoRA SFT** and **DPO** as the final project, achieving a **top 5% ranking** in the competition.
  - **Llama-3.1-8B-Instruct-Freedom_v3**: Llama 3.1 based model trained with LoRA SFT and DPO. [Link](https://huggingface.co/kota-kawa/Llama-3.1-8B-Instruct-Freedom_v3)
  - **llm-jp-3-13b Adapters**: Released adapters for Japanese LLMs.
    - [MataMata-Turtle_lora](https://huggingface.co/kota-kawa/llm-jp-3-13b-MataMata-Turtle_lora) (LoRA)
    - [Wanigame-Turtle](https://huggingface.co/kota-kawa/llm-jp-3-13b-Wanigame-Turtle) (DPO Adapter)

<details>
  <summary><b>Matsuo Lab Specialized AI Courses</b></summary>

- **AI Management Course (Matsuo Lab & PwC)**
  - Studied corporate AI implementation strategies and challenges through case studies from industry leaders like **DENSO** and **Shimizu Corporation**.
- **Matsuo Lab Specialized AI Courses**
  - **LLM (Large Language Model) Course**: Comprehensive study of LLM fundamentals (pre-training) to AI agent applications.
  - **GCI (Global Consumer Intelligence)**: Data science and machine learning foundations.
  - **Deep Learning**: Comprehensive study of neural network architectures and optimization.
  - **Deep Generative Models**: Advanced techniques in generative AI (VAEs, GANs, Diffusion Models).
</details>

- **FIT 2025 (Forum on Information Technology)** (Sep 2025)
  - Presented research on **RAG (Retrieval-Augmented Generation)**.
  - Conducted as part of a joint research project with **Manable Inc.**
- **Meta Llama Ideathon 2024** (Sep 2024)
  - Selected participant for Meta's official AI hackathon in Tokyo.
  - Developed a generative AI prototype leveraging Llama 3 models.
- **Technical Workshops**
  - Participated in 1-day technical programs at **GMO Internet** and **NTT DATA INTELLILINK**.

## Education
- **Japanese**: Native
- **English**: Professional Proficiency (TOEIC 715, 1-year academic study in US)

## Notes
- Personal data such as full address/phone is intentionally omitted.
- Last updated: 2026-01-21
- License: All rights reserved (or CC BY 4.0)

<details>
  <summary>日本語版（クリックで展開）</summary>

# Resume（職務経歴/履歴書） — <Your Name>

## ダウンロード
- 📄 Resume（PDF）：[JP](./resume_ja.pdf) | [EN](./resume_en.pdf)
- 🌐 Portfolio：<https://project-kk.com/>
- 📝 Blog：<https://blog.project-kk.com/>
- 📘 Zenn：<https://zenn.dev/kota_kawa>
- 🐦 X (Twitter)：<https://x.com/project_kk_ai>
- 💼 LinkedIn：<https://www.linkedin.com/in/kota-kawagoe-0a22263a7/>
- ✉️ Email：kota7kawagoe@gmail.com

## サマリー
**自律型AIエージェント**と**プライバシー重視のRAGシステム**に注力するソフトウェアエンジニア。

**強み：課題発見から実装までの完遂力**
周囲の課題・需要を整理し、ユーザーが迷わず使える形に落とし込んで実装まで持っていけます。
要件が曖昧な状態からでも、ユーザー行動を想定してUI/導線を設計し、機能実装までを一貫して行うことができます。

**エピソード：**
大学の研究室内では、自ら必要性を感じて周囲にヒアリングを行い、潜在的な要求を具体化。実際にツールとして実装し、フィードバックを受けて改善するサイクルを回すことで、環境改善に貢献しました。

**技術的強み：**
マルチエージェントアーキテクチャ設計 (LangGraph)、セキュアな個人知識管理 (PKM)、Pythonフルスタック開発。

志望：AIアプリケーションエンジニア / バックエンドシステム開発。

## 主要プロジェクト（おすすめ順）
### 1) [Symphony Agent Conductor](https://github.com/kota-kawa/Symphony-Agent-Conductor) — <自律型エージェントオーケストレーション>
- 概要：**LangGraph**を用いた中央オーケストレーターを構築し、ブラウザ操作やIoT制御を行う専門エージェントを協調動作させることで、デジタル作業と物理デバイス制御のシームレスな連携を実現。
- 技術：Python, Flask, LangGraph, `browser-use`, IoT (Jetson/Pi), OpenAI/Gemini.

### 2) [MemoScribe](https://github.com/kota-kawa/MemoScribe) — <RAG搭載・個人用秘書アプリ>
- 概要：**Django**製のセルフホスト型個人用秘書アプリ。ローカルRAG、個人情報(PII)マスキング、根拠提示機能を備え、プライバシーを保護しつつ正確な知識管理とアシスタント機能を提供。
- 技術：Django 5, PostgreSQL (pgvector), Celery, Redis, OpenAI.

### 3) [Browser-Agent](https://github.com/kota-kawa/Browser-Agent) — <Web UI付きブラウザ自動化エージェント>
- 概要：`browser_use`を**FastAPI**と**noVNC**でラップした、Web UI付きブラウザ自動化エージェント。自然言語による操作、リアルタイム可視化、WebArenaベンチマーク評価が可能。
- 技術：Python, FastAPI, Docker, `browser_use`, noVNC, Gemini/OpenAI.

<details>
  <summary><b>その他のプロジェクト（クリックで展開）</b></summary>

**ファイル共有・共同編集ツール**
- **概要**: **FastAPI**製のセルフホスト型ファイル共有・共同編集ツール。QRコードを用いた即時モバイル転送、パスワード保護されたグループ共有、WebSocketによるリアルタイム同期ノート機能を備え、プライバシー重視の円滑な情報共有を実現。
- **技術**: FastAPI, MySQL, Redis, WebSockets, SQLAlchemy, Docker, APScheduler.

**個人用RAG秘書アプリ**
- **概要**: **Django**製のセルフホスト型個人用秘書アプリ。ローカルRAG、個人情報(PII)マスキング、根拠提示機能を備え、プライバシーを保護しつつ正確な知識管理とアシスタント機能を提供。
- **技術**: Python 3.12, Django 5, PostgreSQL (pgvector), Celery, Redis, OpenAI API, Docker.

**AIナレッジプラットフォーム**
- **概要**: **FastAPI**と**Next.js**を組み合わせた、AIチャット・プロンプト共有・メモ管理の統合プラットフォーム。Gemini APIによる高度な対話機能に加え、ユーザー間でのプロンプト共有や個人用メモ機能を備え、知識共有と個人の生産性向上を両立。
- **技術**: FastAPI, Next.js, PostgreSQL, Gemini API (OpenAI SDK), Docker, Tailwind CSS.

**多目的AIエージェントプラットフォーム**
- **概要**: **Flask**と**React 19**製の多目的AIエージェントプラットフォーム。旅行・健康・仕事・学習の各専門ドメインに最適化されたAIチャットを提供し、Llama Guardによるコンテンツ検閲や厳格なセキュリティヘッダー管理（CSRF/CSP）を備えた安全な対話・プランニング環境を実現。
- **技術**: Flask, React 19, PostgreSQL, Redis, OpenAI/Groq API (Llama Guard), Docker.
</details>

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
- **神奈川工科大学** — 学士（卒業見込）
  - 神奈川県 | 2021年4月 – 2026年3月
- **University of North Alabama** — 交換留学プログラム修了
  - アラバマ州, 米国 | 2023年6月 – 2024年5月
  - **栄誉**: **Dean's List** 選出（2023年秋期、GPA: 3.75/4.0）
  - **実績**: **Artificial Intelligence（人工知能）** 授業の最終プロジェクトにて、クラス内 **1位** の評価を獲得。
  - **デザイン成果物**: [project-kk.com/design](https://project-kk.com/design)（Design I & II, Layout and Design での制作物）
  - **主要履修科目**: 人工知能 (AI), HCI/UX, デザイン I & II, レイアウトデザイン, コンピュータ問題解決。

## 受賞・活動歴
- **松尾研 LLMコンペ2025** (2025年)
  - チーム内でデータセット作成を担当。
  - **H100クラスタ**を活用し、DeepSeekやLlamaモデルを用いた高難易度の数学的推論用合成データセットを構築。
  - 小規模なデータセットながら、学習後のモデル性能向上を実現し、データの質の重要性を実証。
  - 公開データセット: [difficult_math_deepseek_llama](https://huggingface.co/datasets/kota-kawa/difficult_math_deepseek_llama)
- **松尾研 LLM講座 最終プロジェクト & コンペティション**
  - LLMの基礎（事前学習）からAIエージェントとしての活用までを包括的に学習・修了。
  - 最終プロジェクトとして**LoRA SFT**および**DPO**を用いたモデルを開発し、コンペティションにて**上位5%**に入賞。
  - **Llama-3.1-8B-Instruct-Freedom_v3**: Llama 3.1をベースにSFTとDPOを適用したモデル。[Link](https://huggingface.co/kota-kawa/Llama-3.1-8B-Instruct-Freedom_v3)
  - **llm-jp-3-13b アダプタ**: 国産LLM向けのアダプタを公開。
    - [MataMata-Turtle_lora](https://huggingface.co/kota-kawa/llm-jp-3-13b-MataMata-Turtle_lora) (LoRA)
    - [Wanigame-Turtle](https://huggingface.co/kota-kawa/llm-jp-3-13b-Wanigame-Turtle) (DPO Adapter)

<details>
  <summary><b>松尾研 各種AI講座受講（詳細）</b></summary>

- **AI経営講座（松尾研・PwC主催）**
  - **デンソー**や**清水建設**など、大手企業におけるAI活用事例や導入課題について学習。
- **松尾研 各種AI講座受講**
  - **LLM (大規模言語モデル) 講座**: LLMの基礎（事前学習）からAIエージェントとしての活用までを包括的に学習。
  - **GCI (データサイエンス基礎)**: データ分析および機械学習の基礎を習得。
  - **深層学習 (Deep Learning)**: ニューラルネットワークの基礎から最新の最適化手法までを学習。
  - **深層生成モデル**: 生成AI（VAE, GAN, Diffusion Modelなど）の理論と実装を習得。
</details>

- **FIT 2025（第24回情報科学技術フォーラム）**（2025年9月発表）
  - **RAG（検索拡張生成）**に関する研究成果を発表。
  - **マナブル株式会社**との共同研究として実施。
- **Meta Llama Ideathon 2024** (2024年9月)
  - Meta社主催のAIハッカソンに選抜参加。
  - Llama 3 モデルを活用した生成AIプロトタイプを開発。
- **技術ワークショップ / 1-day インターン**
  - **GMOインターネットグループ**、**NTTデータ先端技術**などの技術体験プログラムに参加。

## 語学
- **日本語**: ネイティブ
- **英語**: ビジネスレベル (TOEIC 715, 米国大学での1年間の留学経験)

## 補足
- 住所/電話などの個人情報は意図的に省略しています。
- 最終更新：2026-01-21
- ライセンス：All rights reserved（または CC BY 4.0）
</details>
