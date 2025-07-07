# リアルタイム共感マップ生成プラットフォーム

## 概要

旅行者が日本各地で感じたこと・体験を短文で投稿し、位置情報とともに日本地図上へリアルタイムに可視化するプラットフォームです。投稿が多いエリアや感情が集中するスポットを「共感ホットスポット」として色分け表示し、旅行先のリアルな雰囲気や感情トレンドを俯瞰できます。

---

## 主な機能

- JWT認証付きREST API（Django REST Framework）
- GeoDjango＋PostGISによる位置情報保存・距離検索
- Django Channels＋WebSocketによる地図のリアルタイム更新
- 管理画面で感情ワード辞書の編集・投稿文の自動分類
- 日本地図上へのプロット＆ホットスポット色分け表示
- スケーラブルなインフラ設計（ロードバランサー＋複数インスタンス）

---

## 要件一覧（MoSCoW法）

### Must（必須）
- JWT認証REST API（投稿・取得・更新・削除）
- 位置情報の保存・距離検索（GeoDjango）
- WebSocketによる地図のリアルタイム更新
- 管理画面で感情辞書編集＋自動分類
- 日本地図へのプロット＆ホットスポット色分け
- スケーラビリティ確保

### Should（実装すべき）
- 投稿タイムライン／履歴表示
- 感情タグの細分類
- ユーザープロフィール・過去投稿閲覧
- Redisキャッシュによる高速化

### Could（あればよい）
- SNS連携による自動インポート
- フォロー／コメント機能
- クラスタリング等の可視化
- 多言語対応

### Won't（今回は対応しない）
- 動画投稿や画像解析
- オフラインモードやPWA
- AIによる複雑な感情解析

---

## 技術スタック

- Python 3.x, Django, Django REST Framework, GeoDjango, Django Channels
- PostgreSQL＋PostGIS, Redis
- フロントエンド: Leaflet.js または Mapbox GL JS
- インフラ: Docker, Kubernetes, AWS/GCP/Azure等

---

## 開発・運用のポイント

- OpenAPI(Swagger)によるAPI仕様書作成
- SRID（座標系）はWGS84で統一
- ログ・メトリクス監視（ELK, Prometheus, Grafana等）
- セキュリティ（レート制限, CSRF/XSS対策, セキュアヘッダー）
- テスト自動化（pytest, Playwright/Cypress）

---

## 今後のセクション

- アーキテクチャ・DBスキーマ
- 実装ステップ
- マイルストーン
- 評価方法

---

## ライセンス

このプロジェクトはMITライセンスです。
