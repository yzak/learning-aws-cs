# ParameterStore

## 1. パラメータストアを使った変数管理

### 依頼内容

- パラメータストアに以下の内容を登録

| 名前  | タイプ | 値 | その他 |  
| ------------- | ------------- | ------------- | ------------- |
| cs-id  | 文字列  | 1001 | text型 | 
| cs-secret  | 安全な文字列  | This_is_secret_value | KMSキーIDは、`alias/aws/ssm`を選択 | 

### 成果物
- AWSリソース
- 確認した内容がわかるもの(チェックリストやテストケース、テスト手順等)

## 2. チャレンジ1

### 依頼内容

- パラメータストアを利用するメリットは？
- 作成したパラメータストアの値を取り出して、CloudWatchLogsにログ出力するlambda関数を作成してみよう

