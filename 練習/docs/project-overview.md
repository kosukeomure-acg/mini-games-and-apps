# Mini Games and Apps プロジェクト概要

## 1. プロジェクト情報

| 項目 | 値 |
|-----|-----|
| プロジェクト名 | Mini Games and Apps |
| 公開URL | https://mini-games-web-app.web.app |
| GitHubリポジトリ | https://github.com/kosukeomure-acg/mini-games-and-apps |
| GCPプロジェクトID | mini-games-web-app |
| Firebaseコンソール | https://console.firebase.google.com/project/mini-games-web-app/overview |

---

## 2. 技術スタック

### フロントエンド
- HTML5
- CSS3
- JavaScript (ES6+)
- Canvas API

### インフラ
- **ホスティング**: Firebase Hosting
- **クラウド**: Google Cloud Platform (GCP)
- **ソース管理**: GitHub

---

## 3. ディレクトリ構成

```
練習/
├── README.md                 # プロジェクト説明
├── firebase.json             # Firebase Hosting設定
├── .firebaserc               # Firebaseプロジェクト設定
├── tetris.html               # テトリスゲーム（ソース）
├── docs/
│   ├── project-overview.md   # プロジェクト概要（本ドキュメント）
│   ├── tetris-design.md      # テトリス設計書
│   ├── deployment-guide.md   # デプロイ手順書
│   └── infrastructure.md     # インフラ構成図
└── public/                   # Firebase Hosting公開ディレクトリ
    ├── index.html            # トップページ（ゲーム一覧）
    ├── tetris.html           # テトリスゲーム
    └── 404.html              # エラーページ
```

---

## 4. 公開ページ一覧

| ページ名 | パス | 説明 |
|---------|------|------|
| トップページ | / | ゲーム一覧、プロジェクト紹介 |
| テトリス | /tetris.html | クラシックテトリスゲーム |
| 404エラー | /404.html | ページ未検出時のエラー画面 |

---

## 5. アカウント情報

### GCP / Firebase
- **アカウント**: kosuke.omure@aozora-cg.com
- **プロジェクトID**: mini-games-web-app
- **プロジェクト番号**: 399539881660

### GitHub
- **アカウント**: kosukeomure-acg
- **リポジトリ**: mini-games-and-apps

---

## 6. 関連ドキュメント

- [テトリス設計書](./tetris-design.md) - ゲームの詳細設計
- [デプロイ手順書](./deployment-guide.md) - Firebase Hostingへのデプロイ方法
- [インフラ構成図](./infrastructure.md) - システム構成と依存関係

---

## 7. 改訂履歴

| 日付 | バージョン | 内容 |
|-----|-----------|------|
| 2025-12-18 | 1.0 | 初版作成、テトリスゲーム公開 |
