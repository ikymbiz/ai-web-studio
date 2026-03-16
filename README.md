# 🌌 AI Web Studio Pro 2026

![Version](https://img.shields.io/badge/version-2.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Platform](https://img.shields.io/badge/platform-Web-lightgrey.svg)

**AI Web Studio Pro 2026** は、ブラウザ上で完全に動作するAI駆動型のオールインワンWeb開発環境（IDE）です。

たった1つのHTMLファイルの中に、**「AIによる要件定義・設計（PLAN）」**、**「自律的なコード生成（BUILD）」**、**「本格的なコード編集（CODE）」**、**「リアルタイムプレビュー（PREVIEW）」**、そして**「GitHubへの直接デプロイ（DEPLOY）」**までの全プロセスを統合しました。

## ✨ 主な機能 (Features)

### 🤖 AIアシスタントによる設計と実装 (PLAN & BUILD)
*   **マルチモーダルチャット**: Google Gemini APIを利用し、テキストだけでなく画像（カメラ・ギャラリー）を添付してUIの模写や設計の壁打ちが可能です。
*   **自動コンテキスト管理**: チャットのやり取りと現在のコード状態をAIが把握し、的確な差分修正や提案を行います。
*   **バックグラウンド生成 (Service Worker)**: コードの生成処理はバックグラウンドで実行されます。生成中にブラウザのタブを閉じても処理は中断されません。

### 📝 本格的なコードエディタ (CODE)
*   **CodeMirror 6 統合**: シンタックスハイライト、オートインデント、検索機能（Find in Code）を備えた軽量かつ強力なエディタを内蔵。
*   **ファイルのインポート/エクスポート**: ローカルファイルの読み込みや、作成したコードの即時ダウンロード（HTML形式）に対応。

### 🚀 シームレスなGitHub連携 (DEPLOY & IMPORT)
*   **GitHub Import**: あなたのGitHubリポジトリを検索し、ファイルツリーを辿って既存のコードをエディタに直接読み込むことができます。
*   **1-Click GitHub Deploy**: アプリ内から新しいリポジトリを作成し、コードをPush。さらに**AIが現在のコードを読み取って高品質なREADME.mdを自動生成**し、**GitHub Pagesの有効化**までワンストップで行います。

### 💾 ローカルファースト・アーキテクチャ
*   **IndexedDBによる自動保存**: チャット履歴、現在のコード、設定情報などはすべてブラウザのローカルデータベースに自動保存されます。次回アクセス時も前回の状態から即座に再開できます。

---

## 🛠️ 技術スタック (Tech Stack)

*   **Frontend**: HTML5, CSS3 (Custom Properties), Vanilla JavaScript
*   **Code Editor**: [CodeMirror 6](https://codemirror.net/) (ES Modules via esm.sh)
*   **AI API**: Google Gemini API (`gemini-2.5-flash`, `gemini-2.5-pro`, `gemini-3-flash`, etc.)
*   **Version Control**: GitHub REST API
*   **Storage & Background**: IndexedDB, Service Worker

---

## 🚀 使い方 (Usage)

### 1. セットアップ（インストール不要）
このツールは単一のHTMLファイルで構成されています。`index.html` をお好みのモダンブラウザ（Chrome, Edge, Safari推奨）で開くだけですぐに使い始めることができます。

### 2. 初期設定 (SETタブ)
高度な機能を利用するために、画面上部の「SET」タブから以下の設定を行ってください。
*   **API KEY**: Google AI Studioで取得したGemini APIキーを入力します。（※未設定の場合、デモ用のProxy Workerを介して動作しますが制限があります）
*   **GITHUB TOKEN**: GitHub Deploy / Import機能を使用する場合、`repo` スコープを持った Personal Access Token (`ghp_...`) を入力してください。
*   **DEVELOPER PROFILE**: AIに守らせたいコーディング規約（例：「Tailwind CSSを使用」「コメントは日本語」など）を指定できます。

### 3. アプリの開発フロー
1.  **CHAT (要件定義)**:
    チャット画面で「ダークモードのTodoアプリを作りたい」などAIに要望を伝えます。AIが要件を整理し、プランが固まると「⚡️ コードを作成」ボタンが出現します。
2.  **PREVIEW (確認)**:
    生成が完了すると、自動的にプレビュー画面に遷移し、実際のアプリの動作を確認できます。修正したい場合は下のデバッグ入力欄から指示を出せます。
3.  **CODE (微調整)**:
    生成されたコードをCodeMirrorエディタで直接編集できます。
4.  **DEPLOY (公開)**:
    CODEタブの右上にある「🚀 GitHub Deploy」ボタンをクリックします。リポジトリ名を入力するだけで、コードのPushとWebへの公開が完了します。

---

## ⚙️ モデルのカスタマイズ

SETタブでは、用途に合わせてAIモデルを切り替えることができます。

*   **CHAT MODEL (PLAN)**: 要件定義や会話用のモデル（推論能力の高いモデルを推奨）。
*   **CODE MODEL (BUILD)**: コード生成用のモデル（コーディングに特化したモデルや高速なモデルを推奨）。

*対応モデル例: `gemini-2.5-flash`, `gemini-2.5-pro`, `gemini-3.1-pro-preview`, `deep-research-pro` など*

---

## ⚠️ 免責事項 (Disclaimer)

*   本ツールで入力されたAPIキーおよびGitHubトークンは、お使いのブラウザのローカル（IndexedDB）にのみ保存され、外部のサーバーに送信されることはありません（Google APIおよびGitHub APIへの直接通信を除く）。
*   本ツールによって生成されたコードの動作性やセキュリティについて、開発者は一切の責任を負いません。本番環境にデプロイする前に必ずコードの内容をご自身で確認してください。
*   APIキー未設定時のProxy Workerへのフォールバック動作は、サーバー側の仕様変更により利用できなくなる場合があります。

---

## 📄 ライセンス (License)

This project is licensed under the MIT License.