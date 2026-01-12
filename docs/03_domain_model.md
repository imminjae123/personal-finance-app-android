# ドメインモデル設計

## 1. 基本方針

本アプリでは、「実績（Actual）」と「予定（Planned）」を  
同一の取引モデルで管理し、  
集計・指標算出時に区別する設計を採用する。

---

## 2. Transaction（取引）

### 概要
収入および支出を表す基本エンティティ。

### 属性
- id
- amount（金額）
- type（INCOME / EXPENSE）
- timing（ACTUAL / PLANNED）
- category
- description
- transactionDate

---

## 3. Category

- id
- name
- type（支出 / 収入）

---

## 4. UseCase 一覧

- AddTransactionUseCase
- GetMonthlySummaryUseCase
- GetPlannedBalanceUseCase
- GetCategoryMetricsUseCase
