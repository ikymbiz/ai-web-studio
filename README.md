# AI Web Studio Pro 2026

**AIとの対話だけでWebアプリを設計・構築・プレビュー・デプロイできる、オールインワンのブラウザIDEです。**

---

## 概要 / Overview

AI Web Studio Pro 2026 は、Google Gemini API を活用したノーコード／ローコード開発環境です。サーバー不要、HTMLファイル2つだけで動作します。チャットでアイデアを伝えると、AIがプランニングからコード生成まで一貫して行い、リアルタイムプレビューを確認しながら GitHub Pages へワンクリックでデプロイできます。

---

## 主な機能 / Features

### CHAT — 企画・設計フェーズ
- Gemini とリアルタイムストリーミング会話で要件定義・仕様策定
- 画像添付（カメラ撮影・ギャラリー・ファイル）によるマルチモーダル入力
- 仕様が固まると「⚡ コードを作成」ボタンが出現し、シームレスにBUILDフェーズへ移行

### CODE — コーディングフェーズ
- Gemini によるワンショットのフルHTML/CSS/JS生成
- **既存コード保護**: エディタにコードがある場合、構造を維持した差分修正のみ実行（全面書き換え防止プロンプト搭載）
- **GitHub Import**: リポジトリからファイルを直接インポートしてエディタに読み込み
- **バックグラウンド生成**: Service Worker + IndexedDB により、タブを閉じてもコード生成が継続。復帰時に自動反映
- ローカルファイルのUpload / Copy / Download

### PREVIEW — リアルタイムプレビュー
- iframe によるライブプレビュー（コード編集と連動）
- プレビュー画面から直接「修正を依頼」でき、チャットに修正指示が自動送信される

### DEPLOY — GitHub デプロイ
- **GitHub Deployer (Deployer.html)** でワンクリックデプロイ
- リポジトリの新規作成 / 既存リポジトリへの上書きに対応
- GitHub Pages の自動有効化
- **README 自動生成**: デプロイ時に Gemini がコードを分析し、日英併記の README.md を自動作成
- 404.html のデフォルト同梱

### SET — 設定
- CHAT用 / CODE用で個別にモデルを選択可能
- Developer Profile によるコーディングスタイルのカスタマイズ
- 設定はすべて localStorage に永続化

---

## 対応モデル / Supported Models

| 用途 | モデル | 特徴 |
|------|--------|------|
| CHAT (PLAN) | Gemini 3 Flash Preview | 高速＆フロンティア |
| CHAT (PLAN) | Gemini 2.5 Flash | バランス型 |
| CHAT (PLAN) | Gemini 2.5 Pro | 高品質推論 |
| CHAT (PLAN) | Deep Research Pro Preview | エージェント型プラン策定 |
| CODE (BUILD) | Gemini 3.1 Pro Preview | Vibe Coding / 最高品質 |
| CODE (BUILD) | Gemini 2.5 Pro | 深い推論 |
| CODE (BUILD) | Gemini 3 Flash Preview | 高速ビルド |

---

## セットアップ / Setup

### 必要なもの
1. **Google Gemini API Key** — [Google AI Studio](https://aistudio.google.com/apikey) で取得
2. **GitHub Personal Access Token**（デプロイ機能を使う場合） — `repo` と `workflow` 権限が必要。[トークン発行ページ](https://github.com/settings/tokens/new?scopes=repo,workflow&description=WebDeployTool)

### 使い方

```
1. index.html と Deployer.html を同じフォルダに配置
2. index.html をブラウザで開く
3. SET タブで Gemini API Key を入力し「設定を保存」
4. CHAT タブでアイデアを入力（例：「ダークモードのTodoアプリ」）
5. AIとプランを練り、「⚡ コードを作成」でビルド
6. PREVIEW で確認 → 修正があれば「修正を依頼」
7. CODE タブの「🚀 GitHub Deploy」でデプロイ
```

### GitHub Import を使う場合

```
1. Deployer.html を開き、GitHub Token を入力・保存
2. index.html の CODE タブで「📥 Import」をクリック
3. リポジトリ一覧からファイルを選択してインポート
```

---

## ファイル構成 / File Structure

```
├── index.html        # メインアプリ（CHAT / CODE / PREVIEW / SET）
└── Deployer.html     # GitHub デプロイヤー（リポジトリ管理・Pages有効化）
```

サーバー不要。ローカルでHTMLファイルを開くだけで動作します。

---

## 技術スタック / Tech Stack

- **Frontend**: Vanilla HTML / CSS / JavaScript（フレームワーク不使用）
- **AI**: Google Gemini API（Streaming SSE + REST）
- **Background Processing**: Service Worker + IndexedDB
- **Deploy**: GitHub REST API v3（Contents API / Pages API）
- **Storage**: localStorage（設定・トークン永続化）
- **UI**: レスポンシブ対応、スワイプナビゲーション、ダークモード

---

## アーキテクチャ / Architecture

```
┌─────────────────────────────────────────────────┐
│                   index.html                     │
│                                                  │
│  ┌──────┐  ┌──────┐  ┌────────┐  ┌─────┐       │
│  │ CHAT │→ │ CODE │→ │PREVIEW │→ │ SET │       │
│  └──┬───┘  └──┬───┘  └────────┘  └─────┘       │
│     │         │                                  │
│     ▼         ▼                                  │
│  Gemini    Gemini     ┌──────────────────┐       │
│  Stream    REST  ───→ │  Service Worker  │       │
│  (PLAN)   (BUILD)     │  + IndexedDB     │       │
│                       │  (BG生成・復帰)   │       │
│                       └──────────────────┘       │
│         │                                        │
│         ▼                                        │
│  ┌─────────────┐    localStorage                 │
│  │  GitHub API  │◄── gh_token                    │
│  │  (Import)    │                                │
│  └─────────────┘                                 │
└──────────────────────┬──────────────────────────┘
                       │ pending_deploy_code
                       │ pending_deploy_readme
                       ▼
              ┌─────────────────┐
              │  Deployer.html  │
              │  GitHub API     │
              │  (Deploy/Pages) │
              └─────────────────┘
```

---

## バックグラウンド生成について / Background Generation

Service Worker（Blob URL方式）を使用し、コード生成APIリクエストをバックグラウンドで実行します。

- **タブを閉じても処理が継続**（ブラウザ自体が起動している限り）
- 完了後、結果は IndexedDB に保存
- ページを再度開くと自動的に結果を復元しエディタに反映
- Service Worker 非対応環境では従来のフォアグラウンド実行にフォールバック

> ⚠️ ブラウザを完全に終了した場合、Service Worker も停止します。タブを閉じる程度であれば処理は継続します。

---

## ブラウザ対応 / Browser Support

| ブラウザ | 対応状況 |
|---------|---------|
| Chrome / Edge (Chromium) | ✅ 完全対応 |
| Safari (iOS / macOS) | ✅ 対応（SW制限あり） |
| Firefox | ✅ 対応 |

モバイル最適化済み（タッチスワイプでタブ切り替え対応）。
