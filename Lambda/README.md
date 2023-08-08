# 001

### stop-rds

```python
import boto3

def lambda_handler(event, context):
    rds = boto3.client('rds', region_name='ap-northeast-1')
    rds.stop_db_instance(DBInstanceIdentifier='database-1')
```

### start-rds

```python
import boto3

def lambda_handler(event, context):
    rds = boto3.client('rds', region_name='ap-northeast-1')
    rds.start_db_instance(DBInstanceIdentifier='database-1')
```
