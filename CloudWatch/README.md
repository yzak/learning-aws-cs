# CloudWatch EventBridge

## 1. CloudWatch

### 依頼内容

- EC2を監視して異常時にメールで通知されるようにCloudWatchを構築してください

| 監視リソース  | メトリクス | 閾値 |  
| ------------- | ------------- | ------------- | 
| EC2  | CPU使用率  | 65%以上で異常とする | 

- CPU使用率を65%以上にするために、EC2にSSH接続して以下のコマンドを実行します


```bash
[ec2-user@ip-xx-x-x-xxx ~]$
[ec2-user@ip-xx-x-x-xxx ~]$ yes > /dev/null

※コマンドを実行すると、待機状態になります、この状態でCPUがほぼ100%になっておりますので、監視アラートが上がることを確認します
※監視アラートが通知されたら、この待機状態を止めるため「Ctrlキー + c」を同時に押し、コマンドを戻します。

^C
[ec2-user@ip-xx-x-x-xxx ~]$
※このようにコマンドが打てる状態に戻ったらOKです。
```

### 成果物
- AWSリソース(以降のチャレンジも含め)
  - ※作成後、作成したことを証明するスクリーンショットを取得したら、削除してOKです
- 確認した内容がわかるもの(チェックリストやテストケース、テスト手順等)　（以降のチャレンジも含め）

## 2. チャレンジ1
- EC2のCPU使用率が正常になった場合にもメールで通知されるようにCloudWatchを設定してください

## 3. EventBridgeのスケジューリング
- 毎朝 09:00に、以下のLambdaが実行されるようにEventBridgeを設定してください

| 項目  | 内容 |   
| ------------- | ------------- | 
| Lambda関数のランタイム  | Node.js 16.x  | 
| Lambda関数のアーキテクチャ  | x86_64  | 
| Lambda関数のコード  | 以下を利用  | 

```javascript
exports.handler = async (event) => {
	console.log("called lambda");
};
```

- Lambdaの`console.log()`の実行結果は、CloudWatchLogsのロググループにLambda関数名が付いたロググループが自動的作成され、その中のログストリームを見ることで確認できます
- ※動作確認のため最初から朝9時に設定するのではなく、毎分の実行にしておき、確認できた後、朝9時に動くように設定してください
    - cron式の書き方は[公式サイトの説明](https://docs.aws.amazon.com/ja_jp/lambda/latest/dg/services-cloudwatchevents-expressions.html)も参考になります
## 4. チャレンジ2
- CloudwatchLogs ログのインサイトで、上記「Lambdaのロググループ」を指定して「最近追加された25件のログイベント」を抽出してください
  - ヒント：「サンプルクエリを選択」を見てみましょう
