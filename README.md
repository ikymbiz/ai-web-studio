# 🪄 AI Web Studio

**AI Web Studio** は、ブラウザのみで完結するモバイルファーストのAI駆動型フロントエンド開発環境（SPA）です。チャットベースでAIに指示を出すだけで、要件定義からコーディング、プレビュー、そしてGitHub Pagesへのデプロイまでをワンストップで行うことができます。

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![CodeMirror](https://img.shields.io/badge/CodeMirror-D33833?style=flat-square&logo=codemirror&logoColor=white)](https://codemirror.net/)
[![PWA](https://img.shields.io/badge/PWA-5A0FC8?style=flat-square&logo=pwa&logoColor=white)](https://web.dev/explore/progressive-web-apps)

## ✨ 主な特徴 (Features)

* 🤖 **マルチAIプロバイダー対応**
  * Google Gemini, OpenAI (GPT), Anthropic (Claude), xAI (Grok), Groq を切り替えて使用可能。最適なモデルでコードを生成できます。
* 📱 **モバイル最適化 & PWA対応**
  * スマートフォンでの操作を前提としたUI設計。ネイティブアプリのようなスワイプ操作（仕様リストの編集・削除など）に対応し、インストールしてオフラインライクに利用可能です。
* 📋 **自動要件定義＆仕様管理**
  * AIとの会話から「実装すべき仕様（要件）」を自動抽出。リスト化された仕様と生成コードを照合し、未実装機能があればAIが修正を提案します。
* 👤 **ユーザーペルソナの自動学習**
  * 会話からユーザーの開発スタイルやデザインの好みを自動で抽出し、ペルソナとしてプロンプトに反映させます。
* 💻 **高性能エディタ内蔵**
  * `CodeMirror 6` を採用し、シンタックスハイライト、コード検索機能を提供します。
* 🚀 **GitHub 連携 & 1クリックデプロイ**
  * GitHub上のリポジトリからコードをインポート。
  * 編集したコードを新規リポジトリとして作成し、**GitHub Pagesへ直接デプロイ（公開）** できます。
* 🔒 **セキュアなローカル環境**
  * バックエンドサーバーは不要です。APIキーはブラウザの `Web Crypto API` で強力に暗号化され、IndexedDBにローカル保存されます（2週間で自動消去）。

## 🛠 技術スタック (Tech Stack)

* **Frontend**: HTML5, CSS3, Vanilla JavaScript (No Framework)
* **Editor**: CodeMirror 6
* **Storage**: IndexedDB, LocalStorage
* **Security**: Web Crypto API (AES-GCM / PBKDF2)
* **API Integration**: GitHub REST API, LLM Provider APIs

## 🚀 使い方 (Usage)

本アプリケーションは単一のHTMLファイル（`index.html`）として動作します。ローカルサーバーを立ち上げるか、そのままブラウザで開いて利用できます。

### 1. 初期設定 (Settings)
画面右上の「SET (設定)」タブを開き、以下の設定を行います。
1. 使用したい **AI PROVIDER** を選択します（Gemini推奨）。
2. プロバイダーの **API KEY** を入力します。
3. （オプション）GitHub連携を使用する場合は、**GITHUB TOKEN** (Personal Access Token) を入力します。

### 2. アプリの作成 (Chat & Build)
1. 「CHAT」タブで作りたいアプリのアイデアを入力し、送信します。
2. AIが要件を整理し、「📋 仕様」リストに項目が追加されます。
3. 要件が固まったら、表示される **「⚡️ コードを作成 (BUILD)」** ボタンをタップします。
4. AIがコード（HTML/CSS/JS）を一括生成します。

### 3. プレビューと修正 (Preview & Debug)
1. 「PREVIEW」タブで生成されたアプリの動作を確認します。
2. 修正したい点があれば、画面下部のデバッグパネルに「ボタンの色を赤にして」などと入力し、「修正を依頼」をタップします。

### 4. デプロイ (Deploy)
1. 「CODE」タブを開き、右上の「🚀 Deploy」ボタンをタップします。
2. リポジトリ名を入力し、「✨ 作成」→「🚀 デプロイ実行」をタップするだけで、全世界にWebアプリが公開されます。

## 📁 独自機能のカスタマイズ

* **テーマエディタ**: 設定タブの「CODE THEME」から、生成されるアプリのベースとなるCSSカラーテーマを作成し、自動適用させることができます。
* **テンプレート**: よく使うHTMLのボイラープレートやスニペットをテンプレートとして保存し、いつでも呼び出せます。
* **プロンプトエンジニアリング**: 設定タブ内の「PROMPT TEMPLATES」から、AIへの指示（システムプロンプト、要件抽出ルール、コーディング原則）を自由にカスタマイズ可能です。

## ⚠️ 注意事項

* **CORS制限**: 一部のAIプロバイダー（Anthropic等）は、ブラウザから直接APIを叩く際にCORSエラーが発生する場合があります。その場合、ローカル環境でプロキシサーバーを用意するか、GeminiAPI（ブラウザから直接呼び出し可能）の使用を推奨します。
* **外部アセット**: 内部で `prompts.json` の読み込みを試行するロジックが含まれています。同階層にファイルが存在しない場合は、ハードコードされたデフォルトのプロンプトが適用されます。

## 📜 ライセンス (License)

This project is licensed under the MIT License - see the LICENSE file for details.

---
*Generated with ❤️ by AI Web Studio Architecture*