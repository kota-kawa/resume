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
- Summary: A chat-controlled IoT platform with a web dashboard and camera snapshots, supporting Jetson, Raspberry Pi, and Pico W devices via LLM-based intent understanding.
- Tech: Python, Node.js, Docker, OpenAI/Gemini.

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

**Solution**: Extracted all date/weekday logic into a dedicated set of deterministic tools (`_DATE_CALC_TOOLS` in `scheduler_tools.py`) and had the LLM call them instead of reasoning directly:
- `calc_week_weekday` — returns the exact date of a weekday N weeks ahead
- `calc_nearest_weekday` — finds the nearest specified weekday from a reference date
- `calc_date_offset` — returns the date N days before/after a reference

This created a clear separation of concerns: the LLM handles natural language interpretation (mapping "next Friday" to a weekday number and week offset), while deterministic code handles the actual calculation. Validated via a benchmark of 9 models (OpenAI, Anthropic, Gemini, Groq) across 10 tasks — a mid-tier model (Qwen3 32B) outperformed several frontier models, confirming that **reliability through design beats relying solely on model capability**.

### 2. SSE Streaming Not Working in Production
([ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI)) | Python / FastAPI / Next.js / nginx / Docker | Solo

**Challenge**: Implemented SSE (Server-Sent Events) for token-by-token LLM streaming. Worked perfectly locally, but in production all tokens arrived buffered and displayed at once.

**Solution**: nginx's default response buffering was the culprit. Local dev bypassed nginx, making this a production-only issue. Fixed by adding `proxy_buffering off` and `X-Accel-Buffering: no` to the nginx config. Also added a blue-green deployment setup (`nginx_bootstrap` container) to `docker-compose.yml` for more robust production config management.

### 3. WebSocket Real-Time Sync Not Working in Production
([FS-QR](https://github.com/kota-kawa/fs-qr)) | Python / FastAPI / Redis / nginx | Solo

**Challenge**: Implemented real-time text sync across clients via WebSocket. Worked locally but WebSocket connections failed to establish in production.

**Solution**: nginx defaults to HTTP/1.0, which does not forward the `Upgrade` header required for the WebSocket handshake. Added a `location` block with:
- `proxy_http_version 1.1` — enables HTTP/1.1 and the `Upgrade` header
- `proxy_set_header Upgrade $http_upgrade` — forwards the WebSocket upgrade request
- `proxy_set_header Connection "upgrade"` — explicitly signals connection upgrade
- `proxy_read_timeout 3600` / `proxy_send_timeout 3600` — maintains long-lived connections

Used Redis Pub/Sub to broadcast updates across multiple instances. Shared a key pattern with the SSE issue: **production-only bugs caused by nginx sitting between client and server, invisible in local dev**.

</details>

## Skills
| Category | Technologies |
| :--- | :--- |
| **Programming Languages** | Python, TypeScript, SQL |
| **Web / Application Frameworks** | FastAPI, React, Next.js, Tailwind CSS, PostgreSQL, Redis |
| **AI / LLM Engineering** | RAG, Multi-Agent Systems, LangChain, LangGraph, browser-use |
| **Infrastructure** | Docker, AWS (EC2, VPC, Systems Manager), Linux, Nginx, Git, GitHub Actions, pytest |
| **IoT / Hardware** | NVIDIA Jetson Orin Nano, Raspberry Pi 4/Pico W |

## Experience
**EdTech Company** — Joint Researcher / Project Lead
- **Lead Researcher for RAG System Optimization**: Led a team of three in a joint research project focused on building robust, privacy-first RAG systems for corporate knowledge management (improved RAG accuracy 1.75× by structuring data).
- **Intern (2 months)**: Built a RAG-based chat system on AWS through repeated communication with internal team members, iteratively refining requirements, data structuring, prompt design, and response quality to deliver a practical and reliable system.
- **Publication**: Presented research findings at **FIT 2025 (Forum on Information Technology)**, demonstrating measurable improvements in response reliability. → [Presentation Slides](https://project-kk.com/static/research/FIT発表資料.pdf)

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
- Last updated: 2026-04-15
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
- 概要：チャット指示でデバイス制御を行い、ダッシュボードやカメラ撮影を備えたIoT管理プラットフォーム。Jetson/Raspberry Pi/Pico Wに対応。
- 技術：Python, Node.js, Docker, OpenAI/Gemini.

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

**解決策**: 日付・曜日計算を専用の決定論的ツール群（`scheduler_tools.py` の `_DATE_CALC_TOOLS`）に切り出し、LLMにはそのツールを呼び出させる設計に変更した。
- `calc_week_weekday` — 「N週後の〇曜日」を正確に返す
- `calc_nearest_weekday` — 基準日から最寄りの指定曜日を探す
- `calc_date_offset` — N日後・前の日付を返す

LLMは自然言語の解釈（曜日番号・week_offsetへの変換）のみを担い、実際の計算はコードが行う明確な役割分担を実現した。OpenAI・Anthropic・Gemini・Groqの9モデルで10タスクのベンチマーク評価を実施し、中堅モデル（Qwen3 32B）が複数のフロンティアモデルを上回る精度を出せることも確認。**「モデルの性能だけに頼らず、設計で信頼性を担保する」** という判断の正しさを実証できた。

### 2. 本番環境でSSEストリーミングが動作しない問題
([ChatCore-AI](https://github.com/kota-kawa/ChatCore-AI)) | Python / FastAPI / Next.js / nginx / Docker | 個人開発

**苦労したこと**: LLMの応答をSSEでトークン逐次配信するストリーミング機能を実装した際、ローカルでは正常に動作したが、本番環境ではレスポンスがバッファリングされ全文が届いてから一括表示される問題が発生した。

**解決策**: 原因はnginxのデフォルトのレスポンスバッファリングだった。ローカルではnginxを経由しないため本番特有の問題として顕在化していなかった。`proxy_buffering off` および `X-Accel-Buffering: no` の設定を追加することで解決。また `docker-compose.yml` にnginxのblue-greenデプロイ構成（`nginx_bootstrap`コンテナ）を組み込み、本番環境の構成管理も整備した。

### 3. 本番環境でWebSocketによるリアルタイム共有が動作しない問題
([FS-QR](https://github.com/kota-kawa/fs-qr)) | Python / FastAPI / Redis / nginx | 個人開発

**苦労したこと**: テキストをWebSocketで複数クライアント間にリアルタイム同期する機能を実装した際、ローカルでは正常に動作したが、本番環境ではWebSocket接続が確立できない問題が発生した。

**解決策**: nginxがデフォルトでHTTP/1.0を使用しており、WebSocketのハンドシェイクに必要な`Upgrade`ヘッダーがバックエンドに転送されていなかったことが原因。`location`ブロックに以下を設定して解決した。
- `proxy_http_version 1.1` — HTTP/1.1を有効化しUpgradeヘッダーを使用可能に
- `proxy_set_header Upgrade $http_upgrade` — WebSocketのUpgradeリクエストを転送
- `proxy_set_header Connection "upgrade"` — 接続のアップグレードを明示
- `proxy_read_timeout 3600` / `proxy_send_timeout 3600` — 長時間接続の維持

複数インスタンス間のブロードキャストにはRedis Pub/Subを採用。SSEの問題と共通して **「ローカルではnginxを経由しないため発覚しない本番特有の問題」** というパターンを学んだ。

</details>

## スキル
| カテゴリ | 技術 |
| :--- | :--- |
| **プログラミング言語** | Python, TypeScript, SQL |
| **Web / アプリケーションフレームワーク** | FastAPI, React, Next.js, Tailwind CSS, PostgreSQL, Redis |
| **AI / LLM エンジニアリング** | RAG, Multi-Agent Systems, LangChain, LangGraph, browser-use |
| **インフラ** | Docker, AWS (EC2, VPC, Systems Manager), Linux, Nginx, Git, GitHub Actions, pytest |
| **IoT / ハードウェア** | NVIDIA Jetson Orin Nano, Raspberry Pi 4/Pico W |

## 経験
**教育系IT企業** — 共同研究員 / プロジェクトリーダー
- **RAGシステム最適化の共同研究**: 3名のチームリーダーとして、企業内ナレッジを活用するための堅牢でプライバシーに配慮したRAGシステムの構築に従事（データの構造化によりRAG精度を1.75倍に向上）。
- **インターン（2か月）**: 社内メンバーとのコミュニケーションを繰り返しながら、AWS上にRAGベースのチャットシステムを構築。要件定義、データ構造化、プロンプト設計、応答品質の改善を反復的に行い、実用性の高いシステムを実現した。
- **研究成果の発表**: FIT 2025（第24回情報科学技術フォーラム）にて本研究の成果を発表し、回答精度の向上を実証。 → [発表資料](https://project-kk.com/static/research/FIT発表資料.pdf)

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
- 最終更新：2026-04-15
- ライセンス：All rights reserved
</details>
