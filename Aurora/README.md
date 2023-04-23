# Aurora

## 1. DBの構築とSQL操作

### 依頼内容

- 以下の構成を作成してください
  - VPCやサブネットは以下の条件を満たしていれば、既存の流用OKです

| 項目  | 内容 |
| ------------- | ------------- |
| リージョン  | 東京  |
| エンジン  | Aurora(MySQL互換)  |
| バージョン  | Aurora(MySQL 5.7) のデフォルト  |
| 用途  | 開発/テスト  |
| DBクラスター識別子  | 任意の値  |
| マスターユーザー名  | 任意の値  |
| マスターパスワード  | 任意の値  |
| インスタンスクラス  | バースト可能クラス db.t3.small |
| レプリカ  | 作成する |
| サブネットグループ  | 新規作成 |
| パブリックアクセス  | なし |
| セキュリティグループ  | EC2からのみ接続できるようにする |
| モニタリング  | 拡張モニタリング 無効 |

- 上記のAuroraに接続するためのEC2をパブリックサブネットに1台作成してください
- EC2からMySQL(Aurora)に接続してみましょう
- MySQLに接続後、日本語データが文字化けしないようにするため、以下の2つのコマンドを実行しておきましょう
  - ```
    mysql> set character_set_database=utf8;
    Query OK, 0 rows affected, 1 warning (0.00 sec)
    mysql> set character_set_server=utf8;
    Query OK, 0 rows affected (0.00 sec)
    ```

- 以下の内容でデータベースの初期設定をしてください
  - `MySQL CREATE DATABSE`
  - `MySQL CREATE TABLE`
  - などで検索すると参考になるSQL文が見つかると思います

| 項目  | 内容 |
| ------------- | ------------- |
| データベース名  | devtest  |
| テーブル名  | friends  |

- 以下の内容で作成したテーブルにデータを登録し、検索してみてください
  - `MySQL INSERT`
  - `MySQL SELECT`
  - などで検索すると参考になるSQL文が見つかると思います

| no  | user | friend | connection | 
| ------------- | ------------- | ------------- | ------------- | 
| 1  | 佐藤  | 鈴木 | 部活 | 
| 2  | 佐藤  | 高橋 | 部活 | 
| 3  | 鈴木  | 田中 | クラス | 
| 4  | 田中  | 鈴木 | クラス | 

### 成果物
- AWSリソース
  - ※作成後、作成したことを証明するスクリーンショットを取得したら、削除してOKです
- 確認した内容がわかるもの(チェックリストやテストケース、テスト手順等)

## 2. チャレンジ1

### 依頼内容

- リードレプリカを増やしてみよう
- リードレプリカのエンドポイントに接続して、書き込めないことを確認しよう
- リードレプリカのカスタムエンドポイントを作成してみよう、さらに、作成したエンドポイントに接続してみよう