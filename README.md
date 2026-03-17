# moving-project-summary-ja
バックエンドを中心に開発した引越しマッチングサービスのプロジェクト概要

# 引越しマッチングサービス「Moving」プロジェクト概要

9人チームで開発した、引越し希望者と業者をつなぐO2Oプラットフォームです。  
私は主にバックエンド設計、ERD設計、見積依頼フローのAPI実装を担当しました。

---

## 📌 プロジェクト概要
- 開発期間: 2025.02.18 ~ 2025.04.10  
- チーム構成: 9名（Backend 3名 / Frontend 6名）  
- 目的: 見積価格の不透明性を解消し、合理的なマッチングを実現  

---

## 🛠 使用技術

### Backend
- TypeScript / Express.js  
- Prisma ORM / PostgreSQL  
- JWT / Bcrypt  

### Frontend
- Next.js / React  
- Zustand / TanStack Query  

### Infrastructure
- AWS EC2 / RDS / S3  

---

## 👨‍💻 担当役割
- バックエンド初期構成（フォルダ設計・環境構築）  
- ERD設計・データベース設計  
- 見積依頼フローのAPI設計・実装  
- ユーザー / 業者ごとのエンドポイント分離設計  
- 一部フロントエンド実装  

---

## ⚙️ 実装機能（バックエンド）
- 見積依頼作成 API  
- 見積提出 API  
- マッチング処理 API  
- 重複見積防止ロジック  
- ステータス管理（進行中 / 完了 / キャンセル）  

---

## 🔍 技術的な工夫
- 見積提出と通知送信を1つのトランザクションで処理し、データ不整合を防止  
- ステータスに応じた見積作成制御によりビジネスロジックの整合性を担保  
- RESTful設計に基づき、ユーザーと業者の責務を分離  

---

## ⚠️ 課題と解決
- enum状態管理の変更に伴うマイグレーション問題  
  → 柔軟なスキーマ設計に見直し対応  

- チーム内での認識ズレ  
  → API仕様やデータフローを整理し、共通認識を形成  

---

## 💡 学び
- UXとデータ整合性を両立する設計の重要性  
- チーム開発における認識合わせの必要性  
- 技術選定の根拠を言語化する力  

---

## 🔗 Links
- Backend Repository  
https://github.com/sprint-fs-3-part4-team2/fs3-moving-team2-BE  

- Frontend Repository  
https://github.com/sprint-fs-3-part4-team2/fs3-moving-team2-FE  

- Standard Board Project  
https://github.com/Daewony/standard-board  
