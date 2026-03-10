# ai-web-studio

## 概要・説明 / Overview & Description

**[JA]**  
AI Web Studio Pro 2026 は、ブラウザ上で完結する次世代のAI駆動型Web開発スタジオ（SPA）です。Google Gemini APIの強力な生成能力を活用し、自然言語のプロンプトや画像（手書きのモックアップなど）から、即座に実用的なHTML/CSS/JavaScriptコードを自動生成します。
チャットベースの要件定義から、コード編集、リアルタイムプレビュー、さらにはGitHubからのインポートやデプロイに至るまで、開発に必要なすべてのプロセスをシームレスに統合した画期的なツールです。

**[EN]**  
AI Web Studio Pro 2026 is a next-generation, AI-driven web development studio (SPA) that runs entirely within your browser. By leveraging the powerful generative capabilities of the Google Gemini API, it instantly auto-generates functional HTML/CSS/JavaScript code from natural language prompts or images (such as hand-drawn mockups).
It is a revolutionary tool that seamlessly integrates the entire development workflow—from chat-based requirements definition and code editing to real-time previews, and even importing/deploying via GitHub.

---

## 主な機能一覧 / Key Features

**[JA]**
- **AI対話型プランニング:** Gemini API（3 Flash, 2.5 Pro, Deep Research等）を使用して、対話形式でWebアプリの要件を定義します。
- **マルチモーダル対応:** カメラ撮影、画像ギャラリー、ファイル添付から視覚的なアイデアをAIにインプット可能です。
- **高機能コードエディタ & リアルタイムプレビュー:** 生成されたコードをエディタで確認・編集でき、プレビュー画面に即座に反映されます。
- **バックグラウンド生成 (Service Worker):** タブを閉じてもService WorkerとIndexedDBにより裏側でコード生成が継続します。
- **プレビューからのクイックデバッグ:** プレビュー画面から気になった点を直接メモしてAIに修正依頼（リファクタリング）が可能です。
- **GitHub連携機能:** GitHub APIを利用し、既存リポジトリからコードをインポートしたり、デプロイメントの準備を行うことができます。
- **モバイルフレンドリーUI:** スワイプジェスチャーによる直感的なタブ切り替えなど、スマートフォンやタブレットでの利用に最適化されています。

**[EN]**
- **AI-Powered Planning:** Define web app requirements interactively using the Gemini API (supports 3 Flash, 2.5 Pro, Deep Research, etc.).
- **Multimodal Inputs:** Feed visual ideas to the AI by taking photos, selecting from a gallery, or attaching files.
- **Advanced Code Editor & Real-Time Preview:** Review and edit generated code in the editor, with changes instantly reflected in the preview window.
- **Background Generation (Service Worker):** Code generation continues in the background using Service Workers and IndexedDB, even if you close the tab.
- **Quick Debugging from Preview:** Spot an issue in the preview? Instantly send a quick memo to the AI for automatic bug fixing or refactoring.
- **GitHub Integration:** Use the GitHub API to seamlessly import code from your existing repositories or prepare it for deployment.
- **Mobile-Friendly UI:** Fully optimized for mobile devices and tablets, featuring intuitive swipe gestures to switch between tabs.

---

## 使用技術・ライブラリ / Technologies & Libraries

**[JA / EN]**
- **Frontend:** HTML5, CSS3, Vanilla JavaScript (No heavy frameworks required / 軽量でフレームワーク不要)
- **AI Integration:** Google Gemini API (Server-Sent Events streaming / SSEによるストリーミング通信)
- **Version Control API:** GitHub REST API
- **Web APIs:** Service Worker, IndexedDB, LocalStorage, FileReader API
- **Fonts:** Fira Code (Monospace font for code editor / コードエディタ用フォント)

---

## セットアップ・使い方 / Setup & Usage

**[JA]**
1. **起動:** 本プロジェクトの `index.html` を任意のモダンブラウザ（Chrome, Safari, Edgeなど）で開きます。
2. **APIキーの設定:** `SET` (設定) タブに移動し、有効な **Gemini API Key** を入力して「設定を保存」ボタンをクリックします。（オプションで開発者のプロファイルも設定可能です）
3. **要件の定義:** `CHAT` タブに移動し、作成したいアプリのアイデアを入力するか、画像を添付してメッセージを送信します。
4. **コードの生成:** AIとの会話で仕様が固まったら、「⚡️コードを作成 (BUILD)」ボタンをクリックします。
5. **プレビューと編集:** `PREVIEW` タブで実際の動作を確認し、`CODE` タブで手動修正やローカルへのダウンロード、GitHubへのデプロイ操作を行います。

**[EN]**
1. **Launch:** Open the `index.html` file in any modern web browser (Chrome, Safari, Edge, etc.).
2. **Configure API Key:** Navigate to the `SET` (Settings) tab, enter your valid **Gemini API Key**, and click "Save Settings". (You can optionally define your developer profile here).
3. **Define Requirements:** Go to the `CHAT` tab, type your app idea, optionally attach an image or mockup, and send the message to the AI.
4. **Generate Code:** Once the requirements are finalized through the chat, click the "⚡️ Generate Code (BUILD)" button.
5. **Preview & Edit:** Check the live result in the `PREVIEW` tab, and use the `CODE` tab to manually tweak the code, download it locally, or deploy it via GitHub.

---

## スクリーンショット / Screenshots

![CHAT Interface](https://via.placeholder.com/800x450.png?text=CHAT+Planning+Interface)
*CHATタブでの対話とマルチモーダル入力 / Chat interface with multimodal input*

![Code and Preview](https://via.placeholder.com/800x450.png?text=CODE+%26+PREVIEW+Interface)
*生成されたコードのエディタとリアルタイムプレビュー / Generated code editor and real-time preview*

*(※プレースホルダー画像です。実際のスクリーンショットに置き換えてください / Please replace these placeholders with actual screenshots of your application.)*

---

## ライセンス / License

**[JA]**  
このプロジェクトは [MIT License](LICENSE) の下で公開されています。商用・非商用問わず、自由にご利用・改変いただけます。

**[EN]**  
This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and distribute it for both commercial and non-commercial purposes.