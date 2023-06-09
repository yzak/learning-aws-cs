# Parameter Spec Sheet

- AWSの各種リソースの設定値を記載した詳細設計書
- リソースごとにスプレッドシートやExcelのシートに記載するイメージ
  - リソース量が多くなるため、横にリソースを定義し、縦に属性を記載するイメージ
  - [参考](https://docs.google.com/spreadsheets/d/1TCFicH4LofdXJm1VnNV62qyDZBM5khSlEFPIk_iAjMU/edit?usp=sharing)

## IAMグループ

| 属性(Level1) | 属性(Level2)  | 1 | 2 |
| ------------- | ------------- | ------------- | ------------- | 
| ユーザーグループ名  | | cs-log-read-group  | cs-ec2-maintain-group |  
| 許可ポリシー | | S3の読み込み専用ポリシー  | EC2のフルアクセス | 
|  | | CloudWatchLogsの読み込み専用ポリシー  | | 
| 所属ユーザー  | | tester1  | tester1 | 

## IAMユーザー

| 属性(Level1) | 属性(Level2)  | 1 | 
| ------------- | ------------- | ------------- |  
| ユーザー名  | | tester1  |  
| 許可ポリシー | | なし(所属グループのポリシーのみ) | 
| タグ  | CreatedBy | このリソースを作成したIAMユーザー名  | 
|   | ManagedBy | マネジメントコンソール  | 
|   | Environment | 開発  | 


