# Mini Games and Apps

ブラウザで動作するミニゲームとアプリケーションのコレクション。

## 公開URL

**https://mini-games-web-app.web.app**

## ゲーム一覧

### テトリス (Tetris)
クラシックなテトリスゲームをHTML5 Canvasで実装。

**プレイ**: https://mini-games-web-app.web.app/tetris.html

**操作方法**:
| キー | アクション |
|-----|-----------|
| ← → | 左右移動 |
| ↑ | 回転 |
| ↓ | 高速落下 |
| Space | 即落下 |
| P | 一時停止 |

**特徴**:
- 7種類のテトリミノ
- ゴースト表示（落下予測位置）
- レベルシステム（10ライン毎にレベルアップ）
- スコアリング（クラシックテトリス方式）
- 次のブロックプレビュー

## ドキュメント

設計書やドキュメントは `docs/` フォルダにあります。

| ドキュメント | 説明 |
|------------|------|
| [プロジェクト概要](docs/project-overview.md) | プロジェクト全体の概要 |
| [テトリス設計書](docs/tetris-design.md) | テトリスゲームの詳細設計 |
| [デプロイ手順書](docs/deployment-guide.md) | Firebase Hostingへのデプロイ方法 |
| [インフラ構成図](docs/infrastructure.md) | システム構成と依存関係 |

## 技術スタック

### フロントエンド
- HTML5
- CSS3
- JavaScript (ES6+)
- Canvas API

### インフラ
- Firebase Hosting
- Google Cloud Platform

## ローカル開発

### 前提条件
- Node.js (v18以上)
- Firebase CLI

### セットアップ

```bash
# Firebase CLIのインストール
npm install -g firebase-tools

# Firebaseにログイン
firebase login

# ローカルサーバー起動
firebase serve --only hosting
```

ブラウザで http://localhost:5000 にアクセス。

### デプロイ

```bash
firebase deploy --only hosting
```

## プロジェクト情報

| 項目 | 値 |
|-----|-----|
| GCPプロジェクトID | mini-games-web-app |
| Firebaseコンソール | [リンク](https://console.firebase.google.com/project/mini-games-web-app/overview) |

## ライセンス

MIT License
