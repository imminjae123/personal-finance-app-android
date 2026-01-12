# アーキテクチャ設計

## 1. 全体構成

本アプリは、Androidネイティブアプリとして開発し、  
保守性・拡張性を考慮して Clean Architecture をベースとした構成を採用する。

[UI Layer]
↓
[Domain Layer]
↓
[Data Layer]

---

## 2. 各レイヤの責務

### 2.1 UI Layer
- Jetpack Compose による画面表示
- ユーザー入力の受付
- ViewModel を通じて UseCase を呼び出す
- ビジネスロジックは持たない

---

### 2.2 Domain Layer
- アプリケーションの中核となるビジネスロジックを管理
- Entity / UseCase を定義
- UI や DB に依存しない構成とする

---

### 2.3 Data Layer
- ローカルデータベース（Room）との連携
- SMS / Notification 解析による自動支出記録
- Domain Layer が定義した Repository Interface を実装する

---

## 3. データ管理方針

- データはローカル DB を優先して管理する
- オフライン環境でも利用可能とする
- 将来的なバックエンド連携を考慮し、Repository パターンを採用する

---

## 4. 技術スタック

- Android
  - Kotlin
  - Jetpack Compose
  - Room
- アーキテクチャ
  - Clean Architecture
  - MVVM