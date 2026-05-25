# AWS CLI COMMANDS

## AWS CLI INSTALLATION
- Ref: [https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html#getting-started-install-instructions]

## EC2 COMMANDS
### Create instance
- img id: `ami-0236922087fa98b6e` (Amazon_Linux-2023)
```sh
aws ec2 run-instances --image-id <img-id> --count <num> --instance-type <type> --key-name <Key-name> --security-groups <SG-name>
```

### Describe instances
```sh
aws ec2 describe-instances --filters Name=instance-state-name,Values=running --output table
```

### Terminate instances
```sh
aws ec2 terminate-instances --instance-ids <InstanceId>
```

### EXAMPLES:
### CREATE EC2 USING CLI
```sh
aws ec2 run-instances --image-id ami-0236922087fa98b6e --instance-type t2.micro --key-name Linux-key --security-groups Linux-SG
```

### TERMINATE EC2 USING CLI
```sh
aws ec2 terminate-instances --instance-id <instance-id>
```

---
## S3 COMMANDS
- REF: [https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3api/create-bucket.html]

### Create S3 bucket
```sh
aws s3api create-bucket --bucket <bucket-name> --region us-east-1
```

### Empty S3 bucket
```sh
aws s3 rm s3://<bucket-name> --recursive
```

### Delete S3 bucket
```sh
aws s3api delete-bucket --bucket <bucket-name> --region us-east-1
```
