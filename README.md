# Resume — Kota Kawagoe

## Download
- 📄 Resume (PDF): [JP](./pdf/レジュメ-jp.pdf) | [EN](./pdf/resume-en.pdf)
- 🌐 Portfolio: <https://project-kk.com/>
- 📝 Blog: <https://blog.project-kk.com/>
- 🐦 X (Twitter): <https://x.com/project_kk_ai>
- 💼 LinkedIn: <https://www.linkedin.com/in/kota-kawagoe-0a22263a7/>
- ✉️ Email: kota7kawagoe@gmail.com

### **Looking for: Roles in AI Application Engineering or Backend Systems.**

## Summary

Software Engineer aiming to bring **Autonomous AI Agents** into real-world deployment by leveraging frontend and backend development experience.

**Core Strength: AI × Design × English**
My strength lies in the combination of AI, design, and English communication.

> From ambiguous requirements, I organize user needs, design intuitive UI/UX, and lead development through to implementation — end to end.

**Experience:**
In my university lab, I independently identified operational inefficiencies, gathered requirements from peers, and developed necessary Web services. By iterating on these based on user feedback, I successfully improved work efficiency.

**Technical Strengths:**
Multi-Agent Architecture (LangGraph), Secure Personal Knowledge Management, Full-Stack Python Development.

## Key Projects (recommended order)
### 1) [Symphony Agent Conductor](https://github.com/kota-kawa/Symphony-Agent-Conductor) — (Autonomous Orchestration Platform)
- Summary: An autonomous orchestration platform using **LangGraph** to coordinate specialized agents (Browser automation, IoT control, RAG) for seamless interaction between digital tasks and physical device control.
- Tech: Python, Flask, LangGraph, `browser-use`, IoT (Jetson/Pi), OpenAI/Gemini.

### 2) [MemoScribe](https://github.com/kota-kawa/MemoScribe) — (Personal Life Secretary with RAG)
- Summary: A self-hosted **Django** application acting as a personal life secretary. Features local RAG, PII masking, and strict "evidence-based" citations to ensure secure, private assistance without hallucination.
- Tech: Django 5, PostgreSQL (pgvector), Celery, Redis, OpenAI.

### 3) [Browser-Agent](https://github.com/kota-kawa/Browser-Agent) — (LLM-powered Browser Automation with Web UI)
- Summary: An LLM-powered browser automation agent wrapping `browser_use` with a **FastAPI** backend and **noVNC** web interface. Supports natural language control, real-time visualization, and WebArena benchmarks.
- Tech: Python, FastAPI, Docker, `browser_use`, noVNC, Gemini/OpenAI/Anthropic.

<details>
  <summary><b>Other Projects (Click to expand)</b></summary>

### [Strike Chat](https://github.com/kota-kawa/Strike_Chat) — (AI Chat & Prompt Sharing)
- Summary: An AI chat application built with FastAPI and Next.js. Features email authentication, Groq/Gemini API integration, and prompt sharing/search capabilities.
- Tech: Python (FastAPI), Next.js, PostgreSQL, Docker, Groq/Gemini API.

### [FS-QR](https://github.com/kota-kawa/fs-qr) — (File Sharing & QR)
- Summary: A self-hosted file and note sharing tool with QR-based quick transfer, passworded group rooms, and real-time shared notes.
- Tech: FastAPI, Docker.

### [Yorozu Madoguchi](https://github.com/kota-kawa/yorozu_madoguchi) — (AI Travel Planning Chat App)
- Summary: A chat-based travel planner that turns conversations into personalized itineraries with a simple demo UI.
- Tech: Python, Docker.

### [IoT Agent](https://github.com/kota-kawa/IoT-Agent) — (Conversational IoT Control Platform)
- Summary: A chat-controlled IoT platform with a web dashboard and camera snapshots, supporting Jetson, Raspberry Pi, and Pico W devices via LLM-based intent understanding.
- Tech: Python, Node.js, Docker, OpenAI/Gemini.

### [Scheduler Agent](https://github.com/kota-kawa/Scheduler-Agent) — (AI Schedule Assistant)
- Summary: A chat-first scheduling assistant with timeline views that can use OpenAI, Gemini, or Anthropic models to manage routines and tasks.
- Tech: Python, PostgreSQL, Vite, Docker.

### [Life-Style-Agent](https://github.com/kota-kawa/Life-Style-Agent) — (RAG-Powered Lifestyle Assistant)
- Summary: A multi-domain lifestyle RAG agent with MCP support, a web chat UI, and conversation analysis for proactive assistance.
- Tech: FastAPI, FAISS, LangChain/LlamaIndex, HuggingFace Embeddings, Docker.

### [Ikutoku-sai](https://github.com/kota-kawa/Ikutoku-sai) — (University Festival Website)
- Summary: The official website for the university festival (Ikutoku-sai). Built with Next.js (App Router) to provide event schedules, campus maps, and real-time announcements.
- Tech: Next.js, React, TypeScript.
</details>

## Skills (ship-ready)
| Category | Skills |
| :--- | :--- |
| **AI/Agents** | Multi-Agent Systems (LangGraph), RAG (LangChain/LlamaIndex, FAISS/pgvector), Browser Automation (`browser-use`), MCP (Model Context Protocol) |
| **Backend** | Python (Flask, Django, FastAPI), Microservices Architecture, Celery (Async Tasks), REST/GraphQL |
| **Frontend** | React (Vite/Next.js), TypeScript, Tailwind CSS, Jinja2 (SSR) |
| **Infra/DevOps** | Docker (Compose), `uv` (Package Management), PostgreSQL/MySQL, Redis, CI/CD pipelines |
| **Quality** | `pytest`, `ruff`, `black`, PII Masking/Security-first design |

## Experience
**Manable Inc.** — Joint Researcher / Project Lead
- **Lead Researcher for RAG System Optimization**: Led a team of three in a joint research project focused on building robust, privacy-first RAG systems for corporate knowledge management.
- **Publication**: Presented research findings at **FIT 2025 (Forum on Information Technology)**, demonstrating measurable improvements in response reliability.

## Education
- **Kanagawa Institute of Technology** — B.S. in Information Network and Communication, Faculty of Information Technology (Expected)
  - Kanagawa, Japan | Apr 2021 – Mar 2026
- **University of North Alabama** — International Exchange Program
  - Alabama, USA | Jun 2023 – May 2024
  - **Honors**: **Dean's List** (Fall 2023, GPA: 3.75/4.0).
  - **Achievement**: Ranked **1st in class** for the final project in the **Artificial Intelligence** course.
  - **Design Portfolio**: [project-kk.com/design](https://project-kk.com/design) (Works from Design I & II)
  - **Relevant Coursework**: Artificial Intelligence, Intro to HCI/UX, Design I & II, Applied Computer Science.

## Achievements & Activities
- **Matsuo Lab LLM Competition 2025** (2025)
  - Responsible for dataset creation within the team, building a high-difficulty synthetic dataset for mathematical reasoning using DeepSeek and Llama models.
  - Achieved measurable performance gains after fine-tuning, demonstrating the effectiveness of the high-quality, small-scale dataset.
  - Dataset: [difficult_math_deepseek_llama](https://huggingface.co/datasets/kota-kawa/difficult_math_deepseek_llama)
- **Matsuo Lab LLM Course Final Project & Competition**
  - Completed a comprehensive course covering LLM fundamentals (pre-training) to AI agent applications.
  - Developed fine-tuned models/adapters using **LoRA SFT** and **DPO** as the final project, achieving a **top 5% ranking** in the competition.
  - **Llama-3.1-8B-Instruct-Freedom_v3**: Llama 3.1 based model trained with LoRA SFT and DPO. [Link](https://huggingface.co/kota-kawa/Llama-3.1-8B-Instruct-Freedom_v3)

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
- **Gemini 3 Tokyo Hackathon 2026** (2026)
  - Completed a mystery game powered by **Gemini** and **Nano Banana** within the 7-hour time limit.
- **Meta Llama Ideathon 2024** (Sep 2024)
  - Selected participant for Meta's official AI hackathon in Tokyo.
  - Developed a generative AI prototype leveraging Llama 3 models.

## Language
- **Japanese**: Native
- **English**: Professional Proficiency (TOEIC 715, 1-year academic study in US)

## Notes
- Personal data such as full address/phone is intentionally omitted.
- Last updated: 2026-02-22
- License: All rights reserved

<details>
  <summary>日本語版（クリックで展開）</summary>

# Resume（職務経歴/履歴書） — 川越 航太

## ダウンロード
- 📄 Resume（PDF）：[JP](./pdf/レジュメ-jp.pdf) | [EN](./pdf/resume-en.pdf)
- 🌐 Portfolio：<https://project-kk.com/>
- 📝 Blog：<https://blog.project-kk.com/>
- 🐦 X (Twitter)：<https://x.com/project_kk_ai>
- 💼 LinkedIn：<https://www.linkedin.com/in/kota-kawagoe-0a22263a7/>
- ✉️ Email：kota7kawagoe@gmail.com

### **志望：AIアプリケーションエンジニア / バックエンドシステム開発。**

## サマリー

これまでのフロントエンド/バックエンド開発経験を活かし、**自律型AIエージェント**の社会実装を目指すソフトウェアエンジニア。

**強み：AI × デザイン × 英語**
AIとデザインと英語でのコミュニケーションの３つの組み合わせが自分の強みです。

> 要件が曖昧な状態からでも、ユーザー行動を想定してUI/導線を設計し、機能実装までを一貫して完遂できます。

**エピソード：**
大学の研究室内では、自ら必要性を感じて周囲にヒアリングを行い、潜在的な要求を具体化。実際に必要とされているWebサービスを開発し、フィードバックを受けて改善するサイクルを回すことで、作業の効率化を実現しました。

**技術領域：**
マルチエージェントアーキテクチャ設計 (LangGraph)、セキュアな個人知識管理 (PKM)、Pythonフルスタック開発。

## 主要プロジェクト（おすすめ順）
### 1) [Symphony Agent Conductor](https://github.com/kota-kawa/Symphony-Agent-Conductor) — (自律型エージェントオーケストレーション)
- 概要：**LangGraph**を用いた中央オーケストレーターを構築し、ブラウザ操作やIoT制御を行う専門エージェントを協調動作させることで、デジタル作業と物理デバイス制御のシームレスな連携を実現。
- 技術：Python, Flask, LangGraph, `browser-use`, IoT (Jetson/Pi), OpenAI/Gemini.

### 2) [MemoScribe](https://github.com/kota-kawa/MemoScribe) — (RAG搭載・個人用秘書アプリ)
- 概要：**Django**製のセルフホスト型個人用秘書アプリ。ローカルRAG、個人情報(PII)マスキング、根拠提示機能を備え、プライバシーを保護しつつ正確な知識管理とアシスタント機能を提供。
- 技術：Django 5, PostgreSQL (pgvector), Celery, Redis, OpenAI.

### 3) [Browser-Agent](https://github.com/kota-kawa/Browser-Agent) — (Web UI付きブラウザ自動化エージェント)
- 概要：`browser_use`を**FastAPI**と**noVNC**でラップした、Web UI付きブラウザ自動化エージェント。自然言語による操作、リアルタイム可視化、WebArenaベンチマーク評価が可能。
- 技術：Python, FastAPI, Docker, `browser_use`, noVNC, Gemini/OpenAI.

<details>
  <summary><b>その他のプロジェクト（クリックで展開）</b></summary>

### [Strike Chat](https://github.com/kota-kawa/Strike_Chat) — (AIチャット & プロンプト共有)
- 概要：FastAPIとNext.jsを用いたAIチャットアプリ。メール認証、Groq/Gemini API連携に加え、ユーザー間でプロンプトを共有・検索できる機能を搭載。
- 技術：Python (FastAPI), Next.js, PostgreSQL, Docker, Groq/Gemini API.

### [FS-QR](https://github.com/kota-kawa/fs-qr) — (ファイル共有 & QR)
- 概要：QRによる即時共有、合言葉付きのグループ共有、リアルタイム共有ノートを備えたセルフホスト型のファイル/メモ共有ツール。
- 技術：FastAPI, Docker.

### [よろず窓口](https://github.com/kota-kawa/yorozu_madoguchi) — (AI旅行プランニングチャットアプリ)
- 概要：AIとのチャット相談から旅行プランを自動生成するシンプルなデモアプリ。
- 技術：Python, Docker.

### [IoT Agent](https://github.com/kota-kawa/IoT-Agent) — (会話型IoT制御プラットフォーム)
- 概要：チャット指示でデバイス制御を行い、ダッシュボードやカメラ撮影を備えたIoT管理プラットフォーム。Jetson/Raspberry Pi/Pico Wに対応。
- 技術：Python, Node.js, Docker, OpenAI/Gemini.

### [Scheduler Agent](https://github.com/kota-kawa/Scheduler-Agent) — (AIスケジュール管理アシスタント)
- 概要：チャットで日々のルーティンやタスクを管理し、タイムライン表示にも対応するスケジュール管理アプリ。
- 技術：Python, PostgreSQL, Vite, Docker.

### [Life-Style-Agent](https://github.com/kota-kawa/Life-Style-Agent) — (生活支援RAGエージェント)
- 概要：生活領域の多分野知識をRAGで統合し、MCP対応・会話分析機能を備えた生活支援AI。
- 技術：FastAPI, FAISS, LangChain/LlamaIndex, HuggingFace Embeddings, Docker.

### [Ikutoku-sai](https://github.com/kota-kawa/Ikutoku-sai) — (幾徳祭公式サイト)
- 概要：大学祭（幾徳祭）の公式サイトをNext.js (App Router) で開発。イベントスケジュール、キャンパスマップ、リアルタイムなアナウンス機能などを提供。
- 技術：Next.js, React, TypeScript.
</details>

## スキル（実装して出せる）
| カテゴリ | スキル |
| :--- | :--- |
| **AI/Agents** | マルチエージェントシステム (LangGraph), RAG (LangChain/LlamaIndex, FAISS/pgvector), ブラウザ自動化 (`browser-use`), MCP (Model Context Protocol) |
| **Backend** | Python (Flask, Django, FastAPI), マイクロサービスアーキテクチャ, Celery (非同期タスク), REST/GraphQL |
| **Frontend** | React (Vite/Next.js), TypeScript, Tailwind CSS, Jinja2 (SSR) |
| **Infra/DevOps** | Docker (Compose), `uv` (パッケージ管理), PostgreSQL/MySQL, Redis, CI/CDパイプライン |
| **Quality** | `pytest`, `ruff`, `black`, PIIマスキング/セキュリティ・バイ・デザイン |

## 経験
**マナブル株式会社** — 共同研究員 / プロジェクトリーダー
- **RAGシステム最適化の共同研究**: 3名のチームリーダーとして、企業内ナレッジを活用するための堅牢でプライバシーに配慮したRAGシステムの構築に従事。
- **研究成果の発表**: FIT 2025（第24回情報科学技術フォーラム）にて本研究の成果を発表。

## 学歴
- **神奈川工科大学** — 情報学部 情報ネットワークコミュニケーション学科 学士（卒業見込）
  - 神奈川県 | 2021年4月 – 2026年3月
- **University of North Alabama** — 交換留学プログラム修了
  - アラバマ州, 米国 | 2023年6月 – 2024年5月
  - **栄誉**: **Dean's List** 選出（2023年秋期、GPA: 3.75/4.0）
  - **実績**: **Artificial Intelligence（人工知能）** 授業の最終プロジェクトにて、クラス内 **1位** の評価を獲得。
  - **デザイン成果物**: [project-kk.com/design](https://project-kk.com/design)（Design I & II での制作物）
  - **主要履修科目**: 人工知能 (AI), HCI/UX, デザイン I & II, コンピュータ応用。

## 受賞・活動歴
- **松尾研 LLMコンペ2025** (2025年)
  - チーム内でデータセット作成を担当し、DeepSeekやLlamaモデルを用いた高難易度の数学的推論向け合成データセットを構築。
  - 小規模なデータセットながら、学習後のモデル性能向上を実現し、データの質の重要性を実証。
  - 公開データセット: [difficult_math_deepseek_llama](https://huggingface.co/datasets/kota-kawa/difficult_math_deepseek_llama)
- **松尾研 LLM講座 最終プロジェクト & コンペティション**
  - LLMの基礎（事前学習）からAIエージェントとしての活用までを包括的に学習・修了。
  - 最終プロジェクトとして**LoRA SFT**および**DPO**を用いたモデルを開発し、コンペティションにて上位5%に入賞。
  - **Llama-3.1-8B-Instruct-Freedom_v3**: Llama 3.1をベースにSFTとDPOを適用したモデル。[Link](https://huggingface.co/kota-kawa/Llama-3.1-8B-Instruct-Freedom_v3)

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
  - RAG（検索拡張生成）に関する研究成果を発表。
  - **マナブル株式会社**との共同研究として実施。
- **Gemini 3 東京ハッカソン 2026** (2026年)
  - **Gemini** と **Nano Banana** を活用したミステリゲームを、7時間の制限時間以内に完成させた。
- **Meta Llama Ideathon 2024** (2024年9月)
  - Meta社主催のAIハッカソンに選抜参加。
  - Llama 3 モデルを活用した生成AIプロトタイプを開発。

## 語学
- **日本語**: ネイティブ
- **英語**: ビジネスレベル (TOEIC 715, 米国大学での1年間の留学経験)

## 補足
- 住所/電話などの個人情報は意図的に省略しています。
- 最終更新：2026-02-22
- ライセンス：All rights reserved
</details>
