# 🚀 AI Web Studio

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![No Frameworks](https://img.shields.io/badge/Framework-None-blueviolet.svg)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![PWA Ready](https://img.shields.io/badge/PWA-Ready-success.svg)](#)

**AI Web Studio** は、ブラウザ上で完結する完全自律型のAI駆動Web開発環境です。
チャットベースの要件定義から、仕様の自動抽出、コーディング、エディタでの微調整、そして **GitHub Pagesへのワンクリックデプロイ** まで、フロントエンド開発の全工程を1つの画面でシームレスに実行できます。

ビルドツールも、Node.jsも、バックエンドサーバーも必要ありません。`index.html` を開くだけで、そこがあなたのフルスタック開発スタジオになります。

---

## ✨ 主な機能 (Features)

### 💬 1. 対話型AI開発 & 仕様の自動抽出 (CHAT)
- 要件をチャットで伝えるだけで、AIが文脈を解釈し完全な HTML/CSS/JS を生成します。
- **スマート要件リスト**: 会話の中から実装すべき「仕様」をAIが自動抽出し、タスクリストとして管理。実装漏れを防ぎます。
- **ペルソナ学習**: 会話からあなたの好みのUI/UXや技術スタックをAIが学習し、ユーザープロファイルの更新を提案します。

### 💻 2. 本格的なコードエディタ (CODE)
- **CodeMirror 6 統合**: CDN経由で動的に読み込まれる、シンタックスハイライト・検索機能付きの本格的なコードエディタ。
- **ローカル連携**: 書いたコードの直接ダウンロード、またはローカルファイルのアップロードによる編集の再開が可能です。

### 👁️ 3. ライブプレビュー & ダイレクトデバッグ (PREVIEW)
- 生成・編集されたコードを安全な `iframe` サンドボックス内で即座にプレビュー。
- プレビューを見ながら「ボタンの色を赤にして」といった修正依頼を、画面下部のデバッグパネルから直接AIに送信できます。

### 🚀 4. GitHub シームレス連携 (Import & Deploy)
- **リポジトリからのインポート**: GitHub上の既存のリポジトリから直接コードを読み込み。
- **ワンクリック・デプロイ**: 新規リポジトリの作成から、コードのPush、`README.md` の作成、**GitHub Pages の有効化** までをブラウザから一括で実行します。

### ⚙️ 5. マルチLLM & 高度なカスタマイズ (SETTINGS)
- **対応プロバイダー**: Gemini, OpenAI (GPT-4o等), Claude, xAI (Grok), Groq。
- プロンプトテンプレート、コードの生成原則、UIのカスタムテーマカラー、ボイラープレートテンプレートなどを自由にカスタマイズ可能。

---

## 🛠 技術スタック・アーキテクチャ

このプロジェクトは、モダンなWeb標準APIをフル活用し、**バックエンドレス**で構築されています。

- **UI / ロジック**: HTML5, CSS3, Vanilla JavaScript
- **エディタ**: [CodeMirror 6](https://codemirror.net/) (esm.sh 経由での動的インポート)
- **データ永続化**: IndexedDB (チャット履歴、設定、コードの保存)
- **セキュリティ**: Web Crypto API (`AES-GCM`, `PBKDF2` を用いたAPIキーのローカル暗号化)
- **外部通信**: GitHub REST API, 各社LLM REST API (ストリーミング応答対応)

---

## 🔒 セキュリティ (APIキーの保護)

本アプリケーションは外部のデータベースやバックエンドサーバーを一切持ちません。
設定画面で入力した各種APIキーやGitHubのアクセストークンは、ブラウザの **Web Crypto API によって強力に暗号化** され、ローカルの IndexedDB に保存されます。

- 暗号化キーはユーザー環境に依存する動的ソルトを使用して生成されます。
- 安全性を考慮し、保存されたAPIキーは **14日間で自動的に消去** される仕組みになっています。

---

## 🚀 使い方 (Getting Started)

### 1. インストールと起動
リポジトリをクローンし、`index.html` を開くだけです。
※ 一部のAPI制約（CORS等）やモジュールの動的読み込みを安定させるため、VS Codeの「Live Server」などのローカルサーバー経由での起動を推奨します。

```bash
git clone https://github.com/yourusername/ai-web-studio.git
cd ai-web-studio
# Pythonをお使いの場合、簡易サーバーで起動
python -m http.server 8000
```

### 2. 初期設定
1. 画面右上の **SET** タブを開きます。
2. 使用したい **AI PROVIDER** を選択し、対応する API KEY を入力します。（Google Gemini がデフォルトで最適化されています）
3. ※必要に応じて GitHub Token (Classic PAT / `repo` 権限付き) を設定すると、デプロイ機能が解放されます。

### 3. アプリを開発する
1. **CHAT** タブで「モダンなポモドーロタイマーを作って」などと入力して送信します。
2. AIと仕様を詰め、準備ができたら **「⚡️ コードを作成 (BUILD)」** ボタンをクリックします。
3. **PREVIEW** タブで動作を確認し、**CODE** タブで微調整を行います。
4. 完成したら **「🚀 Deploy」** ボタンからGitHub Pagesへデプロイして世界中に公開しましょう！

---

## 📱 モバイル対応 / PWA

`meta` タグおよび UI設計 はモバイル端末（スマートフォン・タブレット）に完全に最適化されています。
ホーム画面に追加することで、ネイティブアプリのようなフルスクリーン体験（PWA）が可能です。

---

## 📜 ライセンス

このプロジェクトは [MIT License](LICENSE) のもとで公開されています。
個人的なツールとしての利用、商用プロジェクトへの組み込みなど、自由にご活用ください。