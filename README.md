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
    - [Green-Turtle_lora](https://huggingface.co/kota-kawa/llm-jp-3-13b-Green-Turtle_lora) (LoRA)
    - [Wanigame-Turtle](https://huggingface.co/kota-kawa/llm-jp-3-13b-Wanigame-Turtle) (DPO Adapter)
- **AI Management Course (Matsuo Lab & PwC)**
  - Studied corporate AI implementation strategies and challenges through case studies from industry leaders like **DENSO** and **Shimizu Corporation**.
- **Matsuo Lab Specialized AI Courses**
  - **GCI (Global Consumer Intelligence)**: Data science and machine learning foundations.
  - **Deep Learning**: Comprehensive study of neural network architectures and optimization.
  - **Deep Generative Models**: Advanced techniques in generative AI (VAEs, GANs, Diffusion Models).
- **FIT 2025 (Forum on Information Technology)** (Scheduled for Sep 2025)
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
- Last updated: 2026-01-19
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
    - [Green-Turtle_lora](https://huggingface.co/kota-kawa/llm-jp-3-13b-Green-Turtle_lora) (LoRA)
    - [Wanigame-Turtle](https://huggingface.co/kota-kawa/llm-jp-3-13b-Wanigame-Turtle) (DPO Adapter)
- **AI経営講座（松尾研・PwC主催）**
  - **デンソー**や**清水建設**など、大手企業におけるAI活用事例や導入課題について学習。
- **松尾研 各種AI講座受講**
  - **GCI (データサイエンス基礎)**: データ分析および機械学習の基礎を習得。
  - **深層学習 (Deep Learning)**: ニューラルネットワークの基礎から最新の最適化手法までを学習。
  - **深層生成モデル**: 生成AI（VAE, GAN, Diffusion Modelなど）の理論と実装を習得。
- **FIT 2025（第24回情報科学技術フォーラム）**（2025年9月発表予定）
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
- 最終更新：2026-01-19
- ライセンス：All rights reserved（または CC BY 4.0）
</details>
