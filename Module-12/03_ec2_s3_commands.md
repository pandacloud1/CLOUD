## COMMANDS TO CHECK EC2-S3 CONNECTION

List the S3 buckets
```sh
aws s3 ls <bucket-name>
```

Copy (download) files from S3 bucket to EC2
```sh
aws s3 cp s3://<bucket-name>/<file> <ec2-path>
```

Copy (upload) files from EC2 to S3
```sh
aws s3 cp <ec2-path> s3://<bucket-name>/<path>
```
