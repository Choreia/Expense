# Choreia Expense

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![GitHub Pages](https://img.shields.io/badge/使ってみる-GitHub%20Pages-brightgreen)](https://choreia.github.io/Expense/)

**レシートを撮るだけ。AIが自動で経費処理。**

スマホでレシートを撮影 → AIが「いつ・どこで・いくら・何に使ったか」を自動で読み取り → Google Sheetsに保存。APIキー不要・完全無料。

**[使ってみる](https://choreia.github.io/Expense/)**

## 使い方

1. 「Googleでログイン」をタップ
2. レシートを撮影またはアップロード（複数枚OK）
3. 「AIで読み取る」をタップ → 自動で内容を解析
4. 読み取り結果を確認・修正して「Google Sheetsに保存」

## 特徴

- **AI自動読み取り** — Gemini Vision がレシートの日付・店名・金額・品目を自動抽出
- **勘定科目の自動判定** — AIが適切な勘定科目（消耗品費、会議費、交通費 等）を自動で割り当て
- **税区分対応** — 課税仕入10%、軽減8%、非課税を自動判別
- **Google Sheets保存** — データは自分のGoogle Driveに保存。サーバーにデータを送りません
- **スマホ対応** — カメラで直接撮影して即処理
- **複数枚一括処理** — レシートをまとめてアップロード→一括読み取り
- **完全無料** — オープンソース（MIT）、処理件数無制限

## アーキテクチャ

```
スマホ/PC（ブラウザ）
    │
    ├── レシート画像 → Gemini Vision API → JSON（日付・店名・金額・科目）
    │
    └── 仕訳データ → Google Sheets API → 自分のスプレッドシート
```

- サーバー不要（GitHub Pages）
- AIはGoogleログインのOAuthトークンで利用（APIキー不要）
- データはユーザーのGoogle Driveに保存

## 関連プロジェクト

- [Choreia Books](https://github.com/Choreia/Books) — 無料会計ソフト（税金計算・仕訳帳・請求書）
- [Choreia Forms](https://github.com/Choreia/Forms) — 無料フォームビルダー

## ライセンス

[MIT](LICENSE)
