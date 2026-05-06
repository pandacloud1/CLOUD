## S3 BUCKET POLICY
- Using below policy anyone on the internet can read (download) all objects in this bucket
- "Principal": "*" means: Everyone (public access)
- "Action": "s3:GetObject" means: only read/download allowed
- "Resource": "<bucket>/*" means: applies to all objects inside bucket

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
