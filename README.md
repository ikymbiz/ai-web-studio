提供されたHTMLコードを詳細に分析し、このプロジェクトの魅力を最大限に伝える高品質な `README.md` を作成しました。

そのままGitHubなどのリポジトリに配置して使用できるフォーマットにしています。

---

# 🌌 AI Web Studio Pro 2026

**ブラウザ完結型の次世代AI駆動Web開発プラットフォーム**

![Version](https://img.shields.io/badge/version-2.0-blue)
![Platform](https://img.shields.io/badge/platform-Web%20%7C%20PWA-lightgrey)
![License](https://img.shields.io/badge/license-MIT-green)

AI Web Studio Pro 2026 は、AI（Gemini）と対話しながら**要件定義・コード生成・編集・プレビュー・GitHubデプロイ**までを1つの画面で一気通貫に行える、シングルファイル構成の強力なWebアプリケーションです。

ダークモードベースの洗練されたUI（Obsidian Terminalデザインシステム）を備え、PCでもスマートフォンでもシームレスに開発を進めることができます。

---

## ✨ 主な機能 (Features)

### 🤖 1. AIとの対話による要件定義と実装 (CHAT)
- **対話型プランニング**: 作り上げたいアプリの要件をAIとチャットで壁打ちし、仕様を固めます。
- **マルチモーダル対応**: カメラ撮影、ギャラリー、ファイルからの画像添付に対応。モックアップ画像からのUI生成も可能です。
- **履歴管理**: 会話履歴はローカル（IndexedDB）に自動保存され、過去のメッセージの再編集や削除も可能です。

### 💻 2. 統合コードエディタ (CODE)
- **CodeMirror 6 搭載**: シンタックスハイライト、コード検索機能（Find in Code）を備えた本格的なエディタ。
- **ファイル操作**: ローカルファイルのインポート / エクスポート（ダウンロード）に対応。
- **GitHubインポート**: 既存のGitHubリポジトリから対象のファイルを直接読み込んで編集できます。

### 👁️ 3. リアルタイム・プレビュー (PREVIEW)
- **即時確認**: エディタの変更が即座に反映されるプレビュー用iframe。
- **スマート・デバッグパネル**: プレビューを見ながら「ここを修正して」とメモを入力するだけで、AIが文脈（バグか仕様変更か）を解釈し、コードの修正案を再提案します。

### 🚀 4. ワンクリックデプロイ (DEPLOY)
- **GitHub Pages 連携**: GitHub APIを利用し、ブラウザ上から直接新規リポジトリの作成、コミット、プッシュが可能です。
- **README自動生成**: デプロイ実行時に、作成したコードをAIが分析し、高品質な `README.md` を自動生成して一緒にプッシュします。
- **Pages公開設定**: ワンクリックでGitHub Pagesを有効化し、即座に世界中へ公開できます。

### ⚡️ 5. 高度なアーキテクチャ
- **Service Workerによるバックグラウンド生成**: 長時間のコード生成タスクはバックグラウンドで処理されます。生成中に別のタブを見たり、ブラウザを閉じても構築が継続されます。
- **モデルの使い分け**: プランニング用（高速・推論重視）とコーディング用（Vibe Coding・精度重視）で、異なるGeminiモデルを割り当てることができます。

---

## 🛠️ 技術スタック (Tech Stack)

このアプリケーションは、ビルドツールを必要としない**1つのHTMLファイル (Zero-Build)** で構築されています。

- **フロントエンド**: HTML5, CSS3, Vanilla JavaScript
- **エディタ**: [CodeMirror 6](https://codemirror.net/) (ES Modules via esm.sh)
- **AI API**: Google Gemini API (v1beta / Stream API対応)
- **外部連携**: GitHub REST API
- **ストレージ**: IndexedDB API (完全なローカルファースト)
- **PWA**: Service Worker API (バックグラウンド処理用)

---

## 🚀 使い方 (How to Use)

### 1. セットアップ
1. 本リポジトリの `index.html` をダウンロードするか、任意のホスティングサービスで開きます。
2. 右上の **[SET]** (Settings) タブを開きます。
3. ご自身の **Gemini API Key** と、デプロイ機能を使用する場合は **GitHub Personal Access Token (repo権限)** を入力して保存します。
   *(※開発者プロファイルを設定することで、あなた好みのコードスタイルを指定できます)*

### 2. 開発ワークフロー
1. **要件定義**: **[CHAT]** タブで、作りたいWebアプリの要件を伝えます。（例: 「ダークモードのTodoアプリを作りたい」）
2. **コード生成**: AIと仕様が合意できたら、チャット上に現れる `⚡️ コードを作成 (BUILD)` ボタンをクリックします。
3. **プレビュー**: **[PREVIEW]** タブで生成されたアプリを動かして確認します。
4. **編集**: **[CODE]** タブで直接コードを微調整するか、プレビュー画面下のデバッグパネルからAIに修正を依頼します。
5. **公開**: 完成したら **[CODE]** タブの `🚀 GitHub Deploy` をクリックし、リポジトリを作成してワンクリックで公開します！

---

## 📱 モバイル対応 (Mobile Support)

スマートフォンやタブレットからの操作にも最適化されています。
- レスポンシブなUI設計
- 画面の左右スワイプによる直感的なタブ切り替え
- カメラからの直接画像添付

---

## ⚙️ 環境設定 (Configuration)

| 設定項目 | 説明 |
| :--- | :--- |
| **CHAT MODEL** | 会話・プランニング用モデル。高速な `Flash` や推論に特化した `Deep Research` 等を選択可能。 |
| **CODE MODEL** | コード生成用モデル。コーディング精度に優れた `Pro` や 最新の `3.1 Pro` などを選択可能。 |
| **API KEY** | Google AI Studio で取得した Gemini APIキー。（未設定時は内蔵のプロキシワーカー経由で固定モデルがフォールバックとして動作します） |
| **GITHUB TOKEN** | コードのインポート・デプロイに使用するGitHubのPAT (Personal Access Token)。 |
| **DEVELOPER PROFILE** | AIに対するシステムプロンプト。「Tailwind CSSを使用」「コメントは日本語で」などの制約を記述できます。 |

---

## 📄 ライセンス (License)

This project is licensed under the MIT License.

---

*Generated and designed for the future of AI-driven development. (c) 2026*