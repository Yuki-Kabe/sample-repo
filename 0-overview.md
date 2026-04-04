# 技術スタック
- Backend
   - Python
   - FastAPI
   - SQLAlchemy
- Database
   - PostgreSQL
   - pgvector
- Cache / Memory
   - Redis
- Event Streaming
   - Apache Kafka
- Search
   - Elasticsearch
- Authentication
   - Keycloak
- Infrastructure
   - Docker
   - Docker Compose
   - Nginx
- Testing
   - pytest

# 各章

1. Docker
2. DevContainer
3. Linux
4. Git
5. HTTPServerFromScrach
6. HTTPServerFromFastAPI
7. SimpleMemoAPI
8. RDB
9. DockerCompose
10. SimpleMemoAPIWithRDB
11. UnitTest
12. FrontEnd



# このロードマップでは何をするのか

# Unixについての雑学
## 目的
開発環境にはLinuxを用いるが、環境構築に関する調べ物をする際の取っ掛かりを作る。Ubuntu/CentOSとは何か。apt/yumという単語が出てきた時に何に関する文章なのかを把握できるようにするための雑学を学ぶ
## 学習内容
- UNIXの誕生と発展
- BSD・商用Unixの登場、Unixの乱立
- POSIXの登場
- GNUプロジェクトの発足
- Linuxカーネルの誕生とGNU/Linux
- Linuxディストリビューションについて
- 現代のOSの整理
- UNIXという名前とLinuxの立ち位置



# Phase1 Webの全体像
## 目的
Webアプリの全体構造を理解する。

Browser → HTTP → Web Server → Application → DB
## 学習内容
- HTTPとは何か
- リクエスト / レスポンス
- ステータスコード
- APIの役割
## 到達目標
以下を説明できる
- ブラウザがどのようにサーバへアクセスするか
- APIサーバの役割

## Phase2 Dockerによる開発環境
目的

再現可能な開発環境を作る。

学習内容

Dockerとは何か

コンテナ

Dockerfile

到達目標

以下を実行できる

docker build
docker run
Phase3 Linux基本操作
学習内容

基本コマンド

ls
cd
cat
less
tail
grep
find
到達目標

ログを調査できる

Phase4 Git
学習内容
git init
git add
git commit
git branch
git merge
到達目標

変更履歴を管理できる

Phase5 HTTP基礎
学習内容

HTTPメソッド

GET
POST
PUT
DELETE
curl
curl http://localhost:8000
到達目標

curlでAPIを呼び出せる

Phase6 フロントエンド最小
学習内容

HTML

JavaScript

fetch API

例

fetch("/api/memos")
Phase7 Python HTTPサーバ
目的

フレームワークなしでHTTPを理解する。

学習内容
http.server

簡易サーバ

Phase8 FastAPI導入
学習内容

FastAPIでAPIを作る

例

from fastapi import FastAPI

app = FastAPI()

@app.get("/hello")
def hello():
    return {"message": "hello"}
Phase9 PostgreSQL
学習内容

SQL

CREATE TABLE
SELECT
INSERT
UPDATE
DELETE
Phase10 Docker Compose
目的

アプリ + DBを同時に起動

app
db
学習内容

compose.yaml

Phase11 プロジェクト構造
構成
app/
  routers/
  services/
  repositories/
  models/
Phase12 REST API設計

メモアプリ

GET /memos
POST /memos
GET /memos/{id}
PUT /memos/{id}
DELETE /memos/{id}
Phase13 CRUD API実装
実装機能

メモ

作成

更新

削除

一覧

Phase14 責務分離

構造

Router
 ↓
Service
 ↓
Repository
 ↓
DB
Phase15 認証
Keycloak

機能

OAuth2

OpenID Connect

JWT

API

Authorization: Bearer token
Phase16 Redis
用途

キャッシュ

セッション

Queue

例

GET /memos
→ Redis cache
Phase17 Kafka
イベント駆動
POST /memos
 ↓
Kafka event
 ↓
Consumer

例

memo_created
Phase18 Vector Search
Embedding

文章 → ベクトル

"I love python"
→ [0.12, 0.77 ...]
pgvector

類似検索

用途

似たメモ

レコメンド

Phase19 Elasticsearch
用途

全文検索

GET /search?q=python
Phase20 非同期処理

処理例

メール

AI推論

データ更新

構成

API
 ↓
Redis Queue
 ↓
Worker
Phase21 監視
Observability
Metrics

Prometheus

Logging

ELK

Tracing

OpenTelemetry

Phase22 CI/CD

GitHub Actions

push
 ↓
test
 ↓
docker build
 ↓
deploy
Phase23 スケーリング
スケール
Vertical

CPU増強

Horizontal

インスタンス増加

Phase24 マイクロサービス

サービス分割

user-service
memo-service
recommend-service

通信

Kafka
最終構成
Browser
   ↓
Nginx
   ↓
FastAPI
   ↓
Redis
   ↓
Kafka
   ↓
PostgreSQL
   ↓
pgvector
   ↓
Elasticsearch
メモアプリ完成機能
基本機能

メモ作成

メモ更新

メモ削除

メモ一覧

拡張機能
検索

Elasticsearch

レコメンド

Embedding + pgvector

非同期処理

Kafka

キャッシュ

Redis

認証

Keycloak
