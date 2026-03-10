# ai-web-studio

## 🇯🇵 日本語

### プロジェクト名
AI Web Studio Pro 2026

### 概要・説明
AI Web Studio Pro 2026 は、ブラウザ上で完結するAI駆動型のフルスタックWeb開発スタジオです。
自然言語によるチャットベースの指示や画像（UIモックアップ等）の添付を通じて、Gemini AIが要件定義からコーディングまでを自動で行います。チャット、コードエディタ、リアルタイムプレビューをシームレスに行き来し、スピーディーなWebアプリ開発を実現します。
モバイル対応のUIやService Workerを利用したバックグラウンド生成機能など、モダンで実用的な機能が搭載されています。

### 主な機能一覧
- **AIチャットによる要件定義**: 自然言語で作りたいアプリを指示し、AIと機能のプランをすり合わせます。
- **マルチモーダル対応**: カメラ撮影、ギャラリー、ファイルから画像を添付し、画像に基づいたUI/コード生成が可能です。
- **高度なコード生成**: Google Gemini API (2.5 Flash/Pro, 3.0 Flash/Pro等) を活用し、単一ファイル(HTML/CSS/JS)に最適化されたコードを出力します。
- **統合されたエディタ＆プレビュー**: 生成されたコードを直接編集し、リアルタイムでプレビューを確認できます。
- **バックグラウンド生成 (Service Worker)**: タブを閉じてもバックグラウンドでコード生成を継続し、IndexedDBを利用して進捗と結果を復元します。
- **GitHub連携**: GitHubリポジトリからのファイルインポートや、ワンクリックでのデプロイ準備をサポートしています。
- **マルチデバイス対応**: スワイプジェスチャーによるタブ切り替えに対応した、モバイルフレンドリーなPWAライクの設計です。

### 使用技術・ライブラリ
- HTML5, CSS3, Vanilla JavaScript (フロントエンド)
- Google Gemini API (AI推論・コード生成)
- GitHub REST API (ソースコードのインポート)
- Service Worker & IndexedDB (バックグラウンド処理と状態キャッシュ)
- Cloudflare Workers (APIプロキシ通信)

### セットアップ・使い方
#### セットアップ
1. 本プロジェクトのHTMLファイル（`index.html`など）をダウンロード、またはホスティング環境に配置します。
2. ファイルを任意のモダンWebブラウザ（Chrome, Safari, Edgeなど）で開きます。
3. （推奨）「SET (設定)」タブを開き、ご自身の **Google Gemini APIキー** を入力してください。未入力の場合はデフォルトのプロキシサーバー経由で動作します。

#### 使い方
1. **チャットで指示**: 「CHAT」タブで、作成したいWebアプリのアイデアを入力し、送信します（例: 「ダークモード対応の計算機アプリを作りたい」）。必要に応じて左下の「＋」ボタンから画像を添付します。
2. **プランの確認と生成**: AIが要件を整理して返答します。内容に問題がなければ、チャット内に表示される「⚡️コードを作成 (BUILD)」ボタンをクリックします。
3. **プレビューと修正**: コード生成が完了すると「PREVIEW」タブで実際の動作を確認できます。修正したい場合は、画面下部のデバッグパネルから追加の指示を出力します。
4. **エクスポート/デプロイ**: 「CODE」タブから、ソースコードのダウンロード（Download）、クリップボードへのコピー（Copy）、またはGitHubへのデプロイ（🚀 GitHub Deploy）が可能です。

### スクリーンショット
> [ここにチャット画面のスクリーンショットを挿入]
> 
> [ここにコードエディタ画面のスクリーンショットを挿入]
> 
> [ここにプレビュー画面のスクリーンショットを挿入]

### ライセンス
MIT License

---

## 🇬🇧 English

### Project Name
AI Web Studio Pro 2026

### Overview & Description
AI Web Studio Pro 2026 is an AI-driven, full-stack web development studio that runs entirely in your browser.
By simply providing natural language instructions or attaching UI mockups, the integrated Gemini AI handles everything from requirement planning to coding. It offers a seamless experience with an integrated chat interface, code editor, and real-time preview, enabling rapid web application prototyping and development.
Packed with modern features such as a mobile-friendly UI and background code generation via Service Workers, it is designed for maximum productivity.

### Key Features
- **AI-Powered Requirement Planning**: Describe the app you want to build using natural language, and let the Gemini AI structure the plan.
- **Multimodal Inputs**: Attach images via camera, gallery, or file upload to generate code based on visual UI mockups.
- **Advanced Code Generation**: Utilizes Google Gemini API (2.5 Flash/Pro, 3.0 Flash/Pro, etc.) to output optimized single-file applications (HTML/CSS/JS).
- **Integrated Editor & Preview**: Edit the generated code on the fly and immediately see the results in the real-time preview tab.
- **Background Generation**: Leverages Service Workers to keep generating code even if you close the tab, restoring the state seamlessly using IndexedDB.
- **GitHub Integration**: Import files directly from GitHub repositories and easily transition to the deployment phase.
- **Mobile-Friendly UI**: Optimized for mobile devices with swipe gestures for intuitive tab navigation.

### Technologies & Libraries
- HTML5, CSS3, Vanilla JavaScript (No heavy frameworks)
- Google Gemini API (AI reasoning & code generation)
- GitHub REST API (Repository imports)
- Service Worker & IndexedDB (Background tasks & state persistence)
- Cloudflare Workers (API proxy communication)

### Setup & Usage
#### Setup
1. Download the main HTML file of this project (e.g., `index.html`) or host it on your preferred server.
2. Open the file in any modern web browser (Chrome, Safari, Edge, etc.).
3. (Optional) Navigate to the "SET" (Settings) tab and enter your **Google Gemini API Key**. If left blank, the app will use a default proxy server to function.

#### Usage
1. **Chat & Instruct**: In the "CHAT" tab, type in your web app idea (e.g., "Create a calculator app with dark mode") and send it. You can also attach images using the "+" button.
2. **Review & Build**: The AI will respond with a development plan. Once you agree with the specifications, click the "⚡️ Generate Code (BUILD)" button that appears in the chat log.
3. **Preview & Debug**: Once generation is complete, check your app's functionality in the "PREVIEW" tab. Use the debug panel at the bottom to request specific modifications.
4. **Export & Deploy**: Go to the "CODE" tab to copy the code to your clipboard, download it as an `.html` file, or initiate a deployment to GitHub.

### Screenshots
> [Insert screenshot of the Chat screen here]
> 
> [Insert screenshot of the Code Editor screen here]
> 
> [Insert screenshot of the Preview screen here]

### License
MIT License