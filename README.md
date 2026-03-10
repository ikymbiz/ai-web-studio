# ai-web-studio

## 🇯🇵 日本語

### 概要
AI Web Studio Pro 2026は、Gemini AIモデルを活用して、チャットベースでWebアプリケーション（HTML/CSS/JS）の設計・生成・プレビュー・デプロイを行うことができるオールインワンのブラウザベース開発環境です。モバイル対応のUIを備え、画像添付による視覚的要件定義（Vibe Coding）や、バックグラウンドでのコード生成、GitHubとのシームレスな連携をサポートしています。

### 主な機能一覧
- **AIチャットアシスタント:** アプリの要件定義からコード生成のプランニングまで、AIと対話しながら進めることができます。
- **マルチモーダル入力:** カメラ、画像ギャラリー、ファイルから画像を添付し、手書きのモックアップやデザイン画像から直接コードを生成可能です。
- **リアルタイムプレビュー＆エディタ:** 生成されたコードを内蔵のコードエディタで確認・編集し、「PREVIEW」タブで即座に動作確認ができます。
- **バックグラウンド生成:** Service WorkerとIndexedDBを活用し、タブを切り替えても裏側でコード生成タスクを継続します。
- **GitHub連携:** GitHubのトークンを利用して、ご自身のリポジトリから直接ファイルをインポートしたり、生成したコードを直接デプロイ（Deployer.html連携）することが可能です。
- **柔軟なモデル選択:** 要件定義用（CHAT）とコード生成用（BUILD）で、Gemini 2.5 Flash/ProやGemini 3 Previewなど、最適なモデルを個別に選択できます。
- **ファイル操作機能:** 生成されたコードのダウンロード、クリップボードへのコピー、および既存ローカルファイルのアップロード機能を提供します。

### 使用技術・ライブラリ
- **フロントエンド:** HTML5, CSS3, Vanilla JavaScript (フレームワーク不使用)
- **バックグラウンド処理:** Service Worker (Blob URL方式), IndexedDB
- **API通信:** Gemini API (SSEストリーミング対応), GitHub REST API
- **プロキシ:** Cloudflare Workers (APIキー未設定時のフォールバック通信用)
- **フォント:** Fira Code (コードエディタ用)

### セットアップ・使い方
1. **起動:** 本HTMLファイルをモダンブラウザで開きます（Service Workerを有効にするため、ローカルサーバー環境 `http://localhost...` での実行を推奨します）。
2. **設定:** 「SET」タブを開き、必要に応じてGoogle GeminiのAPIキーと、開発者プロファイル（好みのコーディングスタイルなど）を入力して保存します。
3. **要件を伝える:** 「CHAT」タブで、AIに作りたいアプリのアイデアを入力します。必要に応じて「＋」ボタンから画像を添付してください。
4. **生成開始:** 仕様が固まったらAIが提示する「⚡️ コードを作成 (BUILD)」ボタンを押し、コードを生成します。
5. **プレビューと修正:** 「PREVIEW」タブで生成されたアプリの動作を確認します。修正が必要な場合は、画面下のデバッグパネルから修正指示を送信してください。
6. **保存・デプロイ:** 「CODE」タブから、完成したコードをダウンロードするか、「🚀 GitHub Deploy」ボタンからデプロイプロセスに進みます。

### スクリーンショット
![Chat Interface](https://via.placeholder.com/800x450?text=Chat+Interface)
![Code Editor & Preview](https://via.placeholder.com/800x450?text=Code+Editor+%26+Preview)

### ライセンス
MIT License

---

## 🇬🇧 English

### Overview
AI Web Studio Pro 2026 is an all-in-one, browser-based development environment that leverages Gemini AI models to design, generate, preview, and deploy web applications (HTML/CSS/JS) via a conversational interface. It features a mobile-friendly UI and supports multimodal visual requirement definition (Vibe Coding), background code generation, and seamless GitHub integration.

### Features
- **AI Chat Assistant:** Discuss project requirements and formulate a build plan through natural conversation with the AI.
- **Multimodal Inputs:** Attach images directly from your camera, gallery, or local files to generate code from hand-drawn mockups or design screenshots.
- **Real-time Preview & Editor:** View and manually tweak the generated code in the built-in code editor, and instantly test the results in the "PREVIEW" tab.
- **Background Generation:** Utilizes Service Workers and IndexedDB to keep the code generation running in the background, even if you switch tabs or minimize the browser.
- **GitHub Integration:** Import files directly from your GitHub repositories and seamlessly deploy your generated code (integrated with Deployer.html) using a GitHub Personal Access Token.
- **Flexible AI Models:** Select the most appropriate Gemini models (e.g., Gemini 2.5 Flash/Pro, Gemini 3 Preview) separately for the chatting phase and the code-building phase.
- **File Management:** Download the generated source code locally, copy it to the clipboard, or upload existing local files for further AI-assisted editing.

### Technologies
- **Frontend:** HTML5, CSS3, Vanilla JavaScript (No frameworks used)
- **Background Processing:** Service Worker (Blob URL), IndexedDB
- **APIs:** Gemini API (with SSE streaming support), GitHub REST API
- **Proxy:** Cloudflare Workers (used as a fallback when no API key is provided)
- **Typography:** Fira Code (used for the code editor)

### Setup & Usage
1. **Launch:** Open the HTML file in any modern web browser (Running on a local server environment like `http://localhost...` is recommended to enable Service Workers).
2. **Configuration:** Navigate to the "SET" tab. Enter your Google Gemini API Key and a Developer Profile (your preferred coding guidelines), then click save.
3. **Define Requirements:** In the "CHAT" tab, describe the application you want to build. Use the "+" button to attach reference images if necessary.
4. **Generate Code:** Once the requirements are finalized, click the "⚡️ Generate Code (BUILD)" button provided by the AI to start generating the source code.
5. **Preview & Refine:** Check the generated application in the "PREVIEW" tab. If you need adjustments, use the debug panel at the bottom to send feedback/correction requests to the AI.
6. **Save & Deploy:** Go to the "CODE" tab to download your completed code, or click "🚀 GitHub Deploy" to start the deployment process.

### Screenshots
![Chat Interface](https://via.placeholder.com/800x450?text=Chat+Interface)
![Code Editor & Preview](https://via.placeholder.com/800x450?text=Code+Editor+%26+Preview)

### License
MIT License