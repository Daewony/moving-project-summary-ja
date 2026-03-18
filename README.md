<img width="3450" height="1942" alt="image" src="https://github.com/user-attachments/assets/0c478e9e-1d93-454d-b2ec-3edd15ed6b4c" /># moving-project-summary-ja
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

## 🖥 実装画面

### ① 見積依頼開始（ユーザー側）
![見積依頼開始](<img width="3450" height="1942" alt="image" src="https://github.com/user-attachments/assets/97c0a6c0-5c52-43b2-bcf9-8a8cdf0c8318" />)

ユーザーが引越し条件を入力し、見積依頼フローを開始する画面です。

### ② 見積依頼確認・送信
![見積依頼確認](<img width="3448" height="1944" alt="image" src="https://github.com/user-attachments/assets/0d7c3a60-c78f-44bb-845a-380b6622ec17" />)

入力内容を確認して見積依頼を確定する画面です。  
バックエンドでは入力値の検証と見積状態の制御を行いました。

### ③ 見積依頼一覧（業者側）
![見積依頼一覧](<img width="1731" height="972" alt="image" src="https://github.com/user-attachments/assets/fa4a26b4-503e-4750-832e-0acfc2003c3e" />)

業者が受信した見積依頼を確認する画面です。  
条件に応じた一覧表示や、依頼内容の把握をしやすい形を意識しました。

### ④ 見積送信機能
![見積送信](<img width="1728" height="974" alt="image" src="https://github.com/user-attachments/assets/2465587e-c309-4ee1-b4ab-10058d246003" />)

業者が見積金額とコメントを入力して送信する画面です。  
重複見積防止や、見積送信と通知送信の整合性を意識して実装しました。

---

## 🧱 データベース設計（ERD）

### ① ユーザー・業者関連
![ERD User](<img width="3362" height="830" alt="image" src="https://github.com/user-attachments/assets/c6aa075d-2a99-4909-bb72-4452e38f643d" />)

ユーザーを基準に、顧客プロフィールと業者プロフィールを分離し、
お気に入り機能も独立したテーブルで管理しました。

### 見積依頼関連
![ERD Quote Request](<img width="1430" height="434" alt="image" src="https://github.com/user-attachments/assets/3f0261a1-7a59-4568-8c68-b4b589d2c2ec" />)

見積依頼を中心に、出発地・到着地・ステータス履歴を管理する構造で設計しました。

### ③ 見積フロー関連
![ERD Quote Flow](<img width="2646" height="900" alt="image" src="https://github.com/user-attachments/assets/d46aa66a-5a24-475a-8a7d-e42c318a1468" />)

見積依頼（QuoteRequest）を起点に、住所情報、状態履歴、指定見積依頼、業者見積、最終マッチングまでを
一連の流れとして管理する構造で設計しました。
特に、QuoteStatusHistory によって状態遷移を履歴として管理できるようにした点を重視しました。

### 全体構造
![ERD Full](<img width="5570" height="2022" alt="image" src="https://github.com/user-attachments/assets/2242a4ab-d1e7-49bf-837c-ae17cd4bcb70" />)

全体のテーブル関係を俯瞰した構造です。

詳細なERDはこちら  
https://www.erdcloud.com/d/tSXQkMbPGrZthuhzi

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
