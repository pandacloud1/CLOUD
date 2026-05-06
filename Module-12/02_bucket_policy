## BUCKET POLICY
- This policy is used to give access to specific user to list & delete S3 bucket objects

### Creating policy for user
- Create two normal users
- For user1 do not give any permissions
- For user2 add below Inline permissions

```json
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Effect": "Allow",
			"Action": "s3:ListAllMyBuckets",
			"Resource": "*"
		}
	]
}
```

### Creating bucket policy
- Bucket policy allows access to specific user only
- Add this policy under Permissions --> Bucket policy
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "ListBucket",
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::207567771980:user/user1"
            },
            "Action": "s3:ListBucket",
            "Resource": "arn:aws:s3:::test-05052026"
        },
        {
            "Sid": "DeleteObjects",
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::207567771980:user/user1"
            },
            "Action": "s3:DeleteObject",
            "Resource": "arn:aws:s3:::test-05052026/*"
        }
    ]
} 
```

### TESTING
- Login from user1, you won't be able to list/delete buckets
- Login from user2, you will be able to list buckets & delete objects only.
