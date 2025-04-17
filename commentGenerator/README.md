# 日報コメント生成ツール

日報を流し込んだら自動的にコメントをつけてくれる素敵ツール  
ブラウザで完結させるために PureJS で完結

https://shimajima-eiji.github.io/Hosting2/commentGenerator/

## 使い方

1. 日報の生 CSV を入れる
2. 生成結果をいい感じにやる

日報の生 CSV からは名前と理解度％と詳細コメントを探してくる処理しかいれておらず、勝手にクレンジングまでやってくれるので比較的セキュアになってるはず。

## 初期設定

config.js の以下項目を設定する

- provider を openai, anthoropic, gemini, などへ変更する。暴発防止のため、初期値は mock
- prompts.system にシステム設定を投入する。いわゆるファインチューニング欄
- prompts.userTemplate に指示を投入する。いわゆる ChahtGPT にコマンドを送っているアレ

### Google Gemini のエンドポイント

基本は `https://generativelanguage.googleapis.com/v1beta/models/（モデル名）-latest:generateContent` に対応するらしい？
使えるモデルの情報に注意。
投稿時点では `gemini-1.5-flash` を想定。
