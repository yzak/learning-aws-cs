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

# 032

### CPU負荷
```bash
yes > /dev/null
```

### EBS ReadOps
```bash
# 1Gの巨大ファイルを作成
dd if=/dev/zero of=largefile.dat bs=1M count=1024

# 10分間、上記で作成した巨大ファイルを読み込むことで、Read負荷を上げる(iostatで確認)
END_TIME=$(( $(date +%s) + 600 ))

while [[ $(date +%s) -lt $END_TIME ]]; do
    dd if=largefile.dat of=/dev/null bs=1M
done
```