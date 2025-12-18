# デプロイ手順書

## 1. 概要

本ドキュメントでは、Mini Games and AppsプロジェクトをFirebase Hostingにデプロイする手順を説明します。

---

## 2. 前提条件

### 必要なツール
- Node.js (v18以上推奨)
- npm
- Firebase CLI
- gcloud CLI (オプション)
- Git

### 必要なアカウント
- Google アカウント (kosuke.omure@aozora-cg.com)
- GitHubアカウント (kosukeomure-acg)

---

## 3. 初期セットアップ

### 3.1 Firebase CLIのインストール

```bash
npm install -g firebase-tools
```

### 3.2 Firebaseへのログイン

```bash
firebase login
```

ブラウザが開くので、Googleアカウントで認証を完了します。

### 3.3 ログイン確認

```bash
firebase login:list
```

出力例:
```
Logged in as kosuke.omure@aozora-cg.com
```

---

## 4. プロジェクト構成

### 4.1 firebase.json

Firebase Hostingの設定ファイルです。

```json
{
  "hosting": {
    "public": "public",
    "ignore": [
      "firebase.json",
      "**/.*",
      "**/node_modules/**"
    ],
    "rewrites": [
      {
        "source": "**",
        "destination": "/index.html"
      }
    ]
  }
}
```

| 設定項目 | 説明 |
|---------|------|
| public | 公開するディレクトリ |
| ignore | デプロイから除外するファイル |
| rewrites | URLリライト設定 |

### 4.2 .firebaserc

プロジェクト設定ファイルです。

```json
{
  "projects": {
    "default": "mini-games-web-app"
  }
}
```

---

## 5. デプロイ手順

### 5.1 プロジェクトディレクトリへ移動

```bash
cd /Users/oomure/練習
```

### 5.2 ファイルの確認

```bash
ls -la public/
```

publicディレクトリに以下のファイルがあることを確認:
- index.html
- tetris.html
- 404.html

### 5.3 デプロイの実行

```bash
firebase deploy --only hosting
```

出力例:
```
=== Deploying to 'mini-games-web-app'...

i  deploying hosting
i  hosting[mini-games-web-app]: beginning deploy...
i  hosting[mini-games-web-app]: found 3 files in public
✔  hosting[mini-games-web-app]: file upload complete
✔  hosting[mini-games-web-app]: version finalized
✔  hosting[mini-games-web-app]: release complete

✔  Deploy complete!

Hosting URL: https://mini-games-web-app.web.app
```

### 5.4 デプロイの確認

ブラウザで以下のURLにアクセスして確認:
- https://mini-games-web-app.web.app

---

## 6. ローカルテスト

デプロイ前にローカルで動作確認する場合:

```bash
firebase serve --only hosting
```

ブラウザで http://localhost:5000 にアクセス。

---

## 7. ロールバック

問題が発生した場合、Firebaseコンソールから以前のバージョンにロールバック可能です。

1. https://console.firebase.google.com/project/mini-games-web-app/hosting にアクセス
2. 「リリース履歴」から以前のバージョンを選択
3. 「ロールバック」をクリック

---

## 8. トラブルシューティング

### 認証エラー

```bash
# 再ログイン
firebase logout
firebase login
```

### プロジェクトが見つからない

```bash
# プロジェクト一覧を確認
firebase projects:list

# プロジェクトを切り替え
firebase use mini-games-web-app
```

### デプロイ失敗

```bash
# 詳細ログを表示
firebase deploy --only hosting --debug
```

---

## 9. CI/CD設定（オプション）

GitHub Actionsを使用した自動デプロイの設定例:

```yaml
# .github/workflows/firebase-deploy.yml
name: Deploy to Firebase Hosting

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: FirebaseExtended/action-hosting-deploy@v0
        with:
          repoToken: '${{ secrets.GITHUB_TOKEN }}'
          firebaseServiceAccount: '${{ secrets.FIREBASE_SERVICE_ACCOUNT }}'
          channelId: live
          projectId: mini-games-web-app
```

---

## 10. 関連リンク

- [Firebase Hosting ドキュメント](https://firebase.google.com/docs/hosting)
- [Firebase CLI リファレンス](https://firebase.google.com/docs/cli)
- [Firebaseコンソール](https://console.firebase.google.com/project/mini-games-web-app/overview)
