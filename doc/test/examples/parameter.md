# Parameter Test

- AWSの各種リソースの「設定内容」が意図とした通りとなっているかをチェックするためのテスト
- リソースごとにスプレッドシートやExcelのシートに記載するイメージ
- 画面上で入力できる設定を記載する


## IAMグループ

| 属性(Level1)  | 内容 | 結果 | 確認者 | 確認日 | NG内容 |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| ユーザーグループ名  | cs-log-read-group  | OK | TESTER_NAME | YYYY/MM/DD | | 
| 許可ポリシー  | S3の読み込み専用ポリシー  | OK | TESTER_NAME | YYYY/MM/DD | | 
|  | CloudWatchLogsの読み込み専用ポリシー  | NG | TESTER_NAME | YYYY/MM/DD | CloudWatchLogsの書き込みポリシーも付与されていた | 
| 所属ユーザー  | tester1  | OK | TESTER_NAME | YYYY/MM/DD | | 

## IAMユーザー

| 属性(Level1)  | 内容 | 結果 | 確認者 | 確認日 | NG内容 |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| ユーザー名  | tester1  | OK | TESTER_NAME | YYYY/MM/DD | | 
| 所属グループ  | cs-log-read-group  | OK | TESTER_NAME | YYYY/MM/DD | | 
| 許可ポリシー  | なし  | OK | TESTER_NAME | YYYY/MM/DD | | 

## IAMポリシー
- 作成している場合

### S3の読み込みポリシー
| 属性(Level1)  | 属性(Level2)  | 内容 | 結果 | 確認者 | 確認日 | NG内容 |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| ポリシー名  | | cs-s3-log-read-policy  | tester1  | OK | TESTER_NAME | YYYY/MM/DD | | 
| 許可ポリシー  | 効果 | 許可  | tester1  | OK | TESTER_NAME | YYYY/MM/DD | | 
|   | アクション | S3:Get*  | tester1  | OK | TESTER_NAME | YYYY/MM/DD | | 
|   | アクション | S3:List*  | tester1  | OK | TESTER_NAME | YYYY/MM/DD | | 
|   | リソース | *  | tester1  | OK | TESTER_NAME | YYYY/MM/DD | | 

### CloudWatchLogsの読み込みポリシー
| 属性(Level1)  | 属性(Level2)  | 内容 | 結果 | 確認者 | 確認日 | NG内容 |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| ポリシー名  | | cs-cwlogs-log-read-policy  | tester1  | OK | TESTER_NAME | YYYY/MM/DD | | 
| 許可ポリシー  | 効果 | 許可  | tester1  | OK | TESTER_NAME | YYYY/MM/DD | | 
|   | アクション | logs:Describe*  | tester1  | OK | TESTER_NAME | YYYY/MM/DD | | 
|   | アクション | logs:Get*  | tester1  | OK | TESTER_NAME | YYYY/MM/DD | | 
|   | アクション | logs:List*  | tester1  | OK | TESTER_NAME | YYYY/MM/DD | | 
|   | アクション | logs:StartQuery  | tester1  | OK | TESTER_NAME | YYYY/MM/DD | | 
|   | アクション | logs:StopQuery  | tester1  | OK | TESTER_NAME | YYYY/MM/DD | | 
|   | アクション | logs:TestMetricFilter | tester1  | OK | TESTER_NAME | YYYY/MM/DD | | 
|   | アクション | logs:FilterLogEvents | tester1  | OK | TESTER_NAME | YYYY/MM/DD | | 
|   | リソース | *  | tester1  | OK | TESTER_NAME | YYYY/MM/DD | | 

