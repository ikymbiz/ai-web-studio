
# ⚡ Native App Packager

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](#)
[![PWA](https://img.shields.io/badge/PWA-Ready-blueviolet.svg)](#)

ブラウザ上でWebアプリ（HTML/CSS/JS）を選択するだけで、GitHub Actionsを利用して自動的にAndroidネイティブアプリ（APK）をビルド・生成できるフロントエンド完結型のWebツールです。

ローカル環境の構築（Node.js, Android Studio等のインストール）は一切不要。すべてクラウド上で完結します。

## ✨ 特徴 (Features)

- 🌐 **完全ブラウザ完結**: バックエンドサーバーは不要。静的ファイル（HTML）をブラウザで開くだけで動作します。
- ☁️ **クラウドネイティブビルド**: GitHub APIと連携し、対象リポジトリへファイルをプッシュして GitHub Actions (Capacitor利用) を自動トリガーします。
- 📁 **2つのソース方式に対応**:
  - **Local**: PC内のフォルダ（HTML群）をドラッグ＆ドロップでまとめて選択・ZIP化して転送。
  - **GitHub**: 既存のリポジトリ内の指定パスからアセットを直接取得。
- 🎨 **ダイナミックアイコン**: アプリ名からデフォルトのアプリ用アイコンを自動生成（カスタム画像のアップロードも可能）。
- 📊 **リアルタイムコンソール**: Actionsのビルド進行状況やエラーログをブラウザ上でリアルタイムに監視。
- 💾 **設定の永続化**: GitHubトークンなどの設定はIndexedDBを使用してブラウザに安全に保存されます。

## 🏗️ 仕組み (Architecture)

1. 本ツール（フロントエンド）が、ユーザーの入力情報と選択されたWebアセットを取得。
2. GitHub APIを叩き、指定されたリポジトリへアセットとビルド用のワークフローファイル (`build-apk.yml`) を自動コミット。
3. GitHub Actions `workflow_dispatch` を呼び出し、ビルドジョブを開始。
4. GitHub Actions上で **Capacitor** がセットアップされ、Webアセットを内包したAndroid APKがビルドされる。
5. 本ツールがActionsのステータスをポーリングし、成功時にAPKのダウンロードリンクを提供。

---

## 🚀 使い方 (Usage)

### 1. 事前準備 (Prerequisites)
- **GitHubアカウント**
- **Personal Access Token (PAT)**
  - 必要なスコープ: `repo` (または `Contents: Read & Write`, `Actions: Read & Write`, `Workflows: Write`)
- **空のGitHubリポジトリ**（ビルドとファイルの一時保存先として使用します）

### 2. 初期設定
1. 右上の歯車アイコン（⚙️）をクリックして設定を開きます。
2. 取得した GitHub PAT を入力し、「トークンを保存して接続」をクリックします。
3. 連携が成功すると自動的にユーザー名が取得されます。

### 3. アプリのパッケージング
1. **App Configuration (アプリ設定)**
   - アプリの表示名、パッケージID（例: `com.example.app`）、アプリアイコンを設定します。
2. **Web Assets (アセット選択)**
   - **ローカルから**: デプロイしたい `index.html` を含むフォルダをドラッグ＆ドロップで選択します。
   - **GitHubから**: トークン設定後に表示されるプルダウンからリポジトリとパスを選択し、「ファイル一覧を取得」で対象ファイルを選びます。
3. **ビルドの実行**
   - 「🚀 パッケージ & デプロイ」ボタンをクリックします。
   - コンソールに進行状況が表示されます。ブラウザは閉じずにお待ちください（スリープ防止機能が働きます）。
4. **ダウンロード**
   - ビルドが完了（Success）すると、自動的に「📥 APKをダウンロード」ボタンが表示されます。

---

## 🛠 技術スタック (Tech Stack)

### Frontend
- HTML5 / CSS3 (Native CSS Variables)
- Vanilla JavaScript (ES6+)
- [JSZip](https://stuk.github.io/jszip/) (ローカルファイルのZIP圧縮)
- IndexedDB (データ永続化)
- Wake Lock API (ビルド待機中の画面スリープ防止)

### Backend / CI・CD
- GitHub REST API
- GitHub Actions
- [Capacitor](https://capacitorjs.com/) (Webアプリのネイティブコンテナ化)
- Android SDK (Gradle build)

---

## ⚠️ 注意事項と制限事項 (Notes & Limitations)

- **トークンの取り扱いについて**: GitHub PATはブラウザのローカルデータベース(IndexedDB)に保存されます。共有のPCやパブリックな端末で利用する場合は、使用後に必ず設定画面から「🗑️ 設定を初期化」を実行してください。
- **iOSビルドについて**: 現在はAndroid (APK) のビルドのみサポートしています（iOSアプリのビルドにはApple Developer ProgramとmacOS環境のプロビジョニング設定が必要なため）。
- **ファイルのサイズ制限**: GitHub APIを経由するため、極端に巨大な動画ファイル等を含むWebアプリのローカルアップロードは失敗する可能性があります。

## 📜 ライセンス (License)

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
*Created with ❤️ for Web Developers.*