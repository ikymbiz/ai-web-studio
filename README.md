# ai-web-studio

[English follows below](#english-version)

## 🇯🇵 日本語

### 概要・説明
**AI Web Studio Pro 2026** は、Google Gemini APIを活用してWebブラウザ上で動作するAI駆動型の統合開発環境（IDE）です。
ユーザーはチャットインターフェースを通じてAIと対話し、作成したいアプリの要件を伝えるだけで、完全なHTML/CSS/JSのシングルファイルアプリケーションを自動生成できます。リアルタイムなプレビュー機能、高度なコードエディタ、バックグラウンドでのコード生成、そしてGitHubへの直接インポート/デプロイ機能を備えた強力なツールです。

### 主な機能一覧
- **AIチャット＆プランニング**: カメラ、ギャラリー、ローカルファイルからの画像添付に対応したマルチモーダルチャット。
- **コード自動生成**: Geminiモデル（2.5 Pro, 3 Flashなど）を利用した高精度なコード構築。Service WorkerとIndexedDBを利用したバックグラウンド処理にも対応。
- **リアルタイムプレビュー＆デバッグ**: 生成されたコードを即座に確認し、プレビュー画面から直接AIへ修正（デバッグ）依頼が可能。
- **コードエディタ**: シンタックスハイライト風の専用エディタ。ファイルのアップロード、ローカルへのダウンロード、クリップボードへのコピー機能を搭載。
- **GitHub連携**: GitHub APIを利用し、自分のリポジトリからのファイルインポートや、ワンクリックでのデプロイ（`Deployer.html` 経由）が可能。
- **モバイルフレンドリーUI**: スマートフォンなどのタッチデバイスでも快適に操作できるスワイプナビゲーションによるタブ切り替え機能（CHAT / CODE / PREVIEW / SET）。

### 使用技術・ライブラリ
- HTML5 / CSS3 / Vanilla JavaScript (フレームワークレス設計)
- Google Gemini API (v1beta / ストリーミング生成・マルチモーダル対応)
- Service Worker & IndexedDB (バックグラウンドタスク管理・データ復帰)
- GitHub REST API (リポジトリ検索・ファイルインポート)

### セットアップ・使い方
1. 本プロジェクトの `index.html` をダウンロード、またはリポジトリをクローンします。
2. モダンなWebブラウザで `index.html` を開きます（ローカルサーバー環境推奨）。
3. **設定（SETタブ）**:
   - Google AI Studioで取得した「API KEY」を入力し、「設定を保存」をクリックします。
   - お好みで開発者プロフィール（例：Tailwind CSSを使用等）や、用途に応じたAIモデルを選択できます。
4. **チャット（CHATタブ）**:
   - 作成したいWebアプリのアイデアを入力し、送信ボタン（↑）を押します（必要に応じて画像を添付できます）。
   - AIとの対話で仕様が固まったら、「⚡️コードを作成 (BUILD)」ボタンを押して実装を開始します。
5. **プレビュー＆編集**:
   - 「PREVIEW」タブで生成されたアプリの動作を確認し、必要なら修正メモを送信します。
   - 「CODE」タブからソースコードの確認・手動調整、ローカルへのダウンロード、GitHubへのデプロイを実行します。

### スクリーンショット
![Chat Interface](https://via.placeholder.com/800x450?text=Chat+Interface+Screenshot)
![Preview and Code Editor](https://via.placeholder.com/800x450?text=Preview+and+Code+Editor+Screenshot)

### ライセンス
This project is licensed under the MIT License.

---

<a id="english-version"></a>
## 🇺🇸 English

### Overview & Description
**AI Web Studio Pro 2026** is an AI-driven Integrated Development Environment (IDE) that runs directly in your web browser, powered by the Google Gemini API.
By simply communicating your app requirements to the AI through a chat interface, it automatically generates complete HTML/CSS/JS single-page applications. It is a powerful tool featuring real-time previews, an advanced code editor, background code generation, and direct GitHub import/deploy integrations.

### Key Features
- **AI Chat & Planning**: Multimodal chat with support for image attachments from your camera, gallery, or local files.
- **Automated Code Generation**: High-quality code building using Gemini models (e.g., 2.5 Pro, 3 Flash). Supports background processing using Service Workers and IndexedDB.
- **Real-time Preview & Debugging**: Instantly view the generated web app and request bug fixes or updates directly from the preview screen.
- **Code Editor**: Built-in editor supporting direct file uploads, local downloads, and copy-to-clipboard functionalities.
- **GitHub Integration**: Utilize the GitHub REST API to seamlessly import files from your repositories or deploy your code directly (via `Deployer.html`).
- **Mobile-Friendly UI**: Optimized for touch devices with smooth swipe navigation to switch between tabs (CHAT / CODE / PREVIEW / SET).

### Technologies & Libraries
- HTML5 / CSS3 / Vanilla JavaScript (Zero external framework dependencies)
- Google Gemini API (v1beta / Streaming & Multimodal Support)
- Service Worker & IndexedDB (Background task execution and state recovery)
- GitHub REST API (Repository fetching and file importing)

### Setup & Usage
1. Download the `index.html` file of this project or clone the repository.
2. Open `index.html` in any modern web browser (using a local development server is recommended).
3. **Settings (SET Tab)**:
   - Enter your Gemini "API KEY" obtained from Google AI Studio and click "Save Settings".
   - Optionally, customize your Developer Profile (e.g., "Use Tailwind CSS") and select your preferred AI models for chat and coding.
4. **Chat (CHAT Tab)**:
   - Type your web app idea and click the send button (↑). You can also attach reference images.
   - Once you and the AI have finalized the app's features, click the "⚡️ Generate Code (BUILD)" button.
5. **Preview & Edit**:
   - Check the live application in the "PREVIEW" tab. If adjustments are needed, send a quick memo to the AI.
   - Switch to the "CODE" tab to review or manually tweak the source code, download it, or deploy it directly to GitHub.

### Screenshots
![Chat Interface](https://via.placeholder.com/800x450?text=Chat+Interface+Screenshot)
![Preview and Code Editor](https://via.placeholder.com/800x450?text=Preview+and+Code+Editor+Screenshot)

### License
This project is licensed under the MIT License.