# 🚀 AI Web Studio Pro 2026

**AI Web Studio Pro 2026** は、ブラウザ上で完結するAI駆動の次世代Web開発環境です。
Geminiモデルを活用し、チャットベースの要件定義（PLAN）から、コード生成（BUILD）、リアルタイムプレビュー、そしてGitHubへのデプロイ（DEPLOY）までを1つの画面でシームレスに行うことができます。

![Version](https://img.shields.io/badge/version-2.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)

## ✨ 主な特徴 (Features)

### 💬 1. 対話型プランニング (Chat to Plan)
- **AIディレクターとの対話:** 作り込みたいアプリのアイデアをチャットで伝えると、AIがプロのWebディレクターとして要件を整理し、実装プランを提案します。
- **マルチモーダル入力:** カメラ、ギャラリー、ファイルから画像を添付し、デザインカンプやモックアップを元にしたプランニングが可能です。
- **文脈の維持と編集:** チャット履歴はローカル（IndexedDB）に自動保存。メッセージの編集や削除によるプロンプトの微調整も容易です。

### ⚡️ 2. ワンクリック・コード生成 (One-Click Build)
- **最新のGeminiモデル対応:** Gemini 2.5 Flash/Pro, 3.0 Flash, 3.1 Proなど、タスクに応じた最適なモデルを選択可能。
- **バックグラウンド生成:** Service Workerを活用し、生成中にタブを閉じてもバックグラウンドで処理を継続。長時間のコード生成でもストレスフリーです。
- **差分更新:** 既存のコード構造を維持したまま、会話で合意した差分のみをインテリジェントに更新します。

### 💻 3. 統合エディタ ＆ プレビュー (Code & Preview)
- **CodeMirror 6 統合:** シンタックスハイライト、高度な検索機能を備えたエディタを内蔵。
- **リアルタイムプレビュー:** 生成されたコードを即座にiframe内で動作確認。
- **デバッグアシスト:** プレビューを見ながら「修正を依頼」ボタン一つで、AIにバグの要因分析と修正案の提案を依頼できます。

### 🚀 4. シームレスな GitHub 連携 (GitHub Deploy)
- **コードのインポート:** 既存のGitHubリポジトリから対象のファイルを直接エディタにインポート。
- **ワンクリック・デプロイ:** アプリ内から新規リポジトリを作成し、生成したコードとAIが自動生成した `README.md` をコミット＆プッシュ。
- **GitHub Pages 対応:** チェックボックス一つで GitHub Pages を有効化し、即座に世界中へ公開できます。

---

## 🛠️ 技術スタック (Tech Stack)

- **Frontend:** Vanilla HTML / CSS / JavaScript (No Framework)
- **Editor:** [CodeMirror 6](https://codemirror.net/) (ES Modules 経由で動的ロード)
- **Storage:** IndexedDB (`WebStudioBG` データベース)
- **Background:** Service Worker
- **APIs:** 
  - Google Gemini API (SSE Streaming対応)
  - GitHub REST API

---

## 📖 使い方 (Usage)

### 1. セットアップ
本アプリはサーバーレスで動作するシングルHTMLファイルです。
`index.html` をブラウザで開くだけで起動します。（※Service Workerなどの全機能を利用するため、ローカルサーバー経由での起動を推奨します）。

### 2. 初期設定 (SETタブ)
右端の `SET` タブを開き、以下の設定を行います。
- **API KEY:** ご自身の Google Gemini API キーを入力します。（※未設定の場合は機能制限付きのパブリックプロキシワーカーを経由します）
- **GITHUB TOKEN:** GitHubデプロイ機能を使用する場合、`repo` スコープを持つ Personal Access Token を入力します。
- **DEVELOPER PROFILE:** 「Tailwind CSSを使用」「日本語でコメントを書く」など、コード生成時のベースとなるシステムプロンプト（指示）を設定できます。

### 3. 基本的なワークフロー
1. **[CHAT]** タブで作りたいWebアプリの要件をAIに伝えます。
2. AIが要件を整理し、合意に至ると **「⚡️ コードを作成 (BUILD)」** ボタンが出現するのでクリックします。
3. コードが生成されたら **[PREVIEW]** タブで動作を確認します。
4. 修正が必要な場合はプレビュー下部のデバッグパネルから修正を依頼、または **[CODE]** タブで直接編集します。
5. 完成したら **[CODE]** タブの `🚀 GitHub Deploy` ボタンからリポジトリへプッシュ・公開します。

---

## 📁 ファイル構成

本プロジェクトは究極のポータビリティを実現するため、すべての機能が1つのファイルに統合されています。

- `index.html`
  - **CSS:** Obsidian Terminal風のダークデザインシステム、レスポンシブUI、アニメーション。
  - **HTML:** SPA構成のDOMツリー、各種モーダルウィンドウ。
  - **JS:** 状態管理、API通信、CodeMirror統合、IndexedDB制御、Service Worker登録ロジック。

---

## ⚠️ 注意事項・制限事項

- **APIキーの管理:** 入力されたAPIキーやGitHubトークンは、お使いのブラウザのローカルデータベース（IndexedDB）にのみ保存され、外部サーバーに送信されることはありません（Gemini API、GitHub APIへの直接リクエストを除く）。
- **プロキシフォールバック:** APIキー未設定時は、コード内にハードコードされた Cloudflare Workers のプロキシを経由しますが、リクエスト制限やモデルの制限がかかる場合があります。本番利用時は自身のAPIキーの設定を強く推奨します。
- **コードの完全性:** AIによるコード生成は必ずしも完璧ではありません。[CODE] タブにて適宜人間によるレビューと修正を行ってください。

---

## 🤝 コントリビューション

バグ報告や機能追加のPull Requestは大歓迎です！
1. このリポジトリをフォークする
2. 新しいブランチを作成する (`git checkout -b feature/amazing-feature`)
3. 変更をコミットする (`git commit -m 'Add amazing feature'`)
4. ブランチにプッシュする (`git push origin feature/amazing-feature`)
5. Pull Request を作成する

---

*Generated and Designed for the Future of Web Development. - 2026*
```

### 💡 README作成のポイント（分析に基づくアピールポイント）
1. **ワンファイル完結のポータビリティ**: 複雑なビルドツールを必要とせず、`index.html` だけでエディタ・AIチャット・デプロイ環境が手に入る点を強調しました。
2. **ローカルファーストな設計**: `IndexedDB` や `Service Worker` を駆使しており、リロードしてもデータが消えず、裏側で生成を進められるモダンなPWA的設計であることを明記しました。
3. **セキュリティの透明性**: APIキーやGitHubトークンをブラウザ（IndexedDB）のみに保持することを明記し、利用者の不安を払拭するよう配慮しました。