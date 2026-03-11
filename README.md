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
- **電子帳簿保存法対応** — レシート画像をGoogle Driveに自動保存・スプレッドシートとリンク
- **経費ダッシュボード** — 月別推移・カテゴリ別内訳・明細一覧
- **テンプレート登録** — 毎月の固定費（家賃・サブスク等）をワンタップで登録
- **月次レポート出力** — 印刷 / PDF出力に対応
- **CSV出力** — 汎用・弥生会計・freee・マネーフォワード対応
- **完全無料** — オープンソース（MIT）、処理件数無制限

## アーキテクチャ

```
スマホ/PC（ブラウザ）
    │
    ├── レシート画像 → Gemini Vision API → JSON（日付・店名・金額・科目）
    │
    ├── 仕訳データ → Google Sheets API → 自分のスプレッドシート
    │
    └── 証憑画像 → Google Drive API → 「Choreia Expense 証憑」フォルダ（電帳法対応）
```

- サーバー不要（GitHub Pages）
- AIはGoogleログインのOAuthトークンで利用（APIキー不要）
- データ・証憑はすべてユーザーのGoogle Driveに保存

## 関連プロジェクト

- [Choreia Books](https://github.com/Choreia/Books) — 無料会計ソフト（税金計算・仕訳帳・請求書）
- [Choreia Forms](https://github.com/Choreia/Forms) — 無料フォームビルダー

## ライセンス

[MIT](LICENSE)
