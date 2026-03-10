# ai-web-studio

## 概要 / Overview

**[JA]**
AI Web Studio Pro 2026 は、Google Gemini API を活用してスマートフォンやPCブラウザ上で動作するチャットベースのWeb統合開発環境（IDE）です。ユーザーはチャットで自然言語を使って要件を伝えるだけで、AIがHTML/CSS/JavaScriptが一体となったWebアプリケーションを自動生成します。画像ファイルを添付してUIのモックアップからコードを起こす（マルチモーダル機能）ことも可能です。さらに、バックグラウンド生成、リアルタイムプレビュー、GitHubからのインポート・デプロイなど、モダンな開発に必要な機能が1つの画面に統合されています。

**[EN]**
AI Web Studio Pro 2026 is a chat-based Web Integrated Development Environment (IDE) powered by the Google Gemini API, optimized for both mobile and PC browsers. Users can simply describe their requirements in natural language via chat, and the AI will automatically generate complete Web applications (HTML/CSS/JavaScript). It also supports multi-modal inputs, allowing you to attach images/mockups to generate UI code. Furthermore, it integrates essential modern development features such as background code generation, real-time preview, and GitHub import/deployment into a single seamless interface.

## 主な機能一覧 / Key Features

**[JA]**
- **AIチャットによる要件定義とコード生成**: Geminiモデルと対話しながら仕様を固め、1クリックでWebアプリを構築。
- **マルチモーダル対応**: カメラ撮影、ギャラリー、ローカルファイルから画像を添付し、デザイン画からコードを生成。
- **高度なバックグラウンド生成**: Service WorkerとIndexedDBを活用し、タブを閉じたりバックグラウンドに移行してもAIのコード生成処理を継続。
- **リアルタイムプレビュー＆デバッグ**: 生成されたコードを即座にプレビュー。プレビュー画面から「修正依頼」を直接チャットにフィードバック可能。
- **内蔵コードエディタ**: 生成されたソースコードの手動編集、ローカルファイルのアップロード、コードのダウンロード・コピーに対応。
- **GitHub連携**: 既存のGitHubリポジトリからソースコードを検索・インポート。AIによる自動README生成機能付きのGitHubデプロイ機能。
- **柔軟なAIモデル選択**: チャット用（要件定義）とコード生成用で、Gemini 3.1 Pro、2.5 Pro、3 Flash、Deep Researchなどのモデルを用途に合わせて選択可能。
- **モバイルファーストなUI**: スワイプジェスチャーによるタブ切り替えに対応し、スマートフォンでも快適に直感的な操作が可能。

**[EN]**
- **AI Chat for Planning & Code Generation**: Define requirements by conversing with Gemini models, and build web apps with a single click.
- **Multi-modal Support**: Attach images from the camera, gallery, or files to generate code directly from UI mockups.
- **Advanced Background Generation**: Utilizes Service Workers and IndexedDB to continue code generation even if the tab is closed or moved to the background.
- **Real-time Preview & Debugging**: Instantly preview generated code and send revision requests directly from the preview panel.
- **Built-in Code Editor**: Manually edit generated code, upload local files, or download and copy the code.
- **GitHub Integration**: Import source code from existing GitHub repositories, and deploy to GitHub with AI-generated READMEs.
- **Flexible AI Model Selection**: Choose different Gemini models (e.g., 3.1 Pro, 2.5 Pro, 3 Flash, Deep Research) independently for chatting (planning) and coding (building).
- **Mobile-first UI**: Optimized for smartphones with swipe-gesture tab navigation for a seamless experience.

## 使用技術・ライブラリ / Technologies & Libraries

**[JA]**
- **フロントエンド**: HTML5, CSS3 (CSS Variables, ダークテーマ), JavaScript (Vanilla ES6+)
- **ストレージ & ワーカー**: Service Worker, IndexedDB, LocalStorage
- **API**: 
  - Google Gemini API (`generativelanguage.googleapis.com` / SSE Streaming & REST)
  - GitHub REST API (リポジトリ検索、ファイルツリー取得、インポート)
- **依存関係**: 外部ライブラリなし（フルスクラッチのVanilla JS実装）

**[EN]**
- **Frontend**: HTML5, CSS3 (CSS Variables, Dark Theme), JavaScript (Vanilla ES6+)
- **Storage & Workers**: Service Worker, IndexedDB, LocalStorage
- **APIs**: 
  - Google Gemini API (`generativelanguage.googleapis.com` / SSE Streaming & REST)
  - GitHub REST API (for importing and fetching file trees)
- **Dependencies**: None (Zero-dependency, pure Vanilla JS implementation)

## セットアップ・使い方 / Setup & Usage

**[JA]**
1. `index.html` をブラウザで開きます。（※Service WorkerやIndexedDBを使用するため、ローカルサーバー（Live Server等）またはHTTPS環境での実行を強く推奨します）
2. **SET (設定) タブ**を開き、ご自身の `Google Gemini API キー` を入力して「設定を保存」をクリックします。必要に応じて開発者プロファイルや使用モデルを変更してください。
3. **CHAT タブ**に移動し、作りたいWebアプリのアイデアを入力します。画像ファイル（UIのラフスケッチなど）を添付メニュー（＋ボタン）から追加することも可能です。
4. AIと対話して仕様が固まったら、チャット内に表示される「⚡️コードを作成 (BUILD)」ボタンを押します。
5. バックグラウンドで生成が完了すると自動的にコードがセットされ、**PREVIEW タブ** で動作を確認できます。
6. 修正が必要な場合は、プレビュー画面下部の入力欄に修正指示を書いて「修正を依頼」ボタンを押すか、**CODE タブ** で直接コードを編集してください。
7. 完成したコードは、**CODE タブ** からダウンロード、または「🚀 GitHub Deploy」ボタンからデプロイ画面へ移行できます。

**[EN]**
1. Open `index.html` in your web browser. (*Running it via a local server like Live Server or over HTTPS is highly recommended for Service Worker and IndexedDB support.*)
2. Go to the **SET (Settings) tab**, enter your `Google Gemini API Key`, and click "Save". You can also customize your developer profile and select preferred AI models.
3. Switch to the **CHAT tab** and type your web app idea. You can also attach image files (e.g., rough UI sketches) using the attachment menu (+ button).
4. After finalizing the plan with the AI, click the "⚡️ Generate Code (BUILD)" button that appears in the chat.
5. Once background generation is complete, the code will be set automatically, and you can test your app in the **PREVIEW tab**.
6. If revisions are needed, type your instructions in the debug input field at the bottom of the Preview tab and click "Request Fix", or manually edit the code in the **CODE tab**.
7. You can download the finished code from the **CODE tab** or deploy it directly using the "🚀 GitHub Deploy" button.

## スクリーンショット / Screenshots

**[JA]**
> ※ 実際の運用時には以下のプレースホルダーを適切な画像URLに置き換えてください。

**[EN]**
> *Please replace the placeholder images below with actual screenshot URLs.*

![CHAT Interface](https://via.placeholder.com/800x450?text=Chat+Interface+-+Planning)
*CHATタブでの要件定義 / Requirements definition in the CHAT tab*

![CODE Editor](https://via.placeholder.com/800x450?text=Code+Editor+-+Building)
*CODEタブでのエディタとアクション / Code editor and actions in the CODE tab*

![PREVIEW Screen](https://via.placeholder.com/800x450?text=Real-time+Preview)
*PREVIEWタブでの動作確認とデバッグ依頼 / Real-time preview and debug requests*

## ライセンス / License

**[JA]**
このプロジェクトは MIT ライセンスの下で公開されています。

**[EN]**
This project is licensed under the MIT License.