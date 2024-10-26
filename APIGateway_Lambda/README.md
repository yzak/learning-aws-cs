# APIGateway Lambda

## 1. APIの実装

### 依頼内容

- 以下の構成のAPIGatewayと、それに連携するLambdaを作成してください

| 項目  | 内容 | 補足 |  
| ------------- | ------------- | ------------- | 
| APIタイプ  | REST API  | | 
| メソッド  | GETのみ  | | 
| リクエストパラメータ  | id | 
| プロキシ統合  | しない | 

| 項目  | 内容 | 補足 |  
| ------------- | ------------- | ------------- | 
| Lambda関数のランタイム  | Node.js 16.x  | | 
| Lambda関数のアーキテクチャ  | x86_64 | 
| Lambda関数のコード  | 以下を利用 | 


```javascript
exports.handler = async (event) => {
    // TODO implement
    const response = {
        statusCode: 200,
        body: JSON.stringify('Hello from Lambda! id is ' + event["id"]),
    };
    return response;
};
```


### 成果物
- AWSリソース
  - ※作成後、作成したことを証明するスクリーンショットを取得したら、削除してOKです
  - Lambda関数を実行すると、CloudWatchLogsに、Lambda関数名が付いたロググループが自動的に作成されますので、それも削除してOKです
- 確認した内容がわかるもの(チェックリストやテストケース、テスト手順等)

## 2. チャレンジ1
- REST APIとは何か教えてください
