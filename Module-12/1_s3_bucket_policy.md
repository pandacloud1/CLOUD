## S3 BUCKET POLICY

```json
{
  "Version": "2012-10-17",
  "Statement": [
     {
      "Sid": "Mystatement",
      "Principal": "*",
      "Effect": "Allow",
      "Action": "s3:GetObject",
      "Resource": "<s3_bucket_arn>/*"
     }
  ]
}
```
