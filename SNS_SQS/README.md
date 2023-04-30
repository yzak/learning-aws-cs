# SNS SQS

## 1. ファンアウトの実装

### 依頼内容

- 以下の構成のSNSとSQSを作成してください

| サービス  | 用途 | 補足 |  
| ------------- | ------------- | ------------- | 
| SNS  | 注文イベントの通知  | 標準タイプのトピックでOK、下記SQSの2つをサブスクリプションとして登録 | 
| SQS  | 在庫管理処理を行うためのキュー  | 標準キュー | 
| SQS  | 注文分析処理を行うためのキュー | 標準キュー | 

### 成果物
- AWSリソース
  - ※作成後、作成したことを証明するスクリーンショットを取得したら、削除してOKです
- 確認した内容がわかるもの(チェックリストやテストケース、テスト手順等)

## 2. チャレンジ1
- 注文分析処理キューに入った内容をログ出力するLambdaを作成してください
  - ヒント:Lambda作成時に「設計図の使用 > `SQS`で検索すると、SQSキューのメッセージを処理する設計図」を指定し、必要事項を入力することで作成できます