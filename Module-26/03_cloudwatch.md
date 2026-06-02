## MONITOR EC2 RAM USING CLOUDWATCH

### IAM Policy
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": ["cloudwatch:PutMetricData"],
      "Resource": "*"
    }
  ]
}
```

### Metrics file
NOTE
- Create a file metrics.sh in your EC2
- Make the metrics.sh file executable by running `sudo chmod +x metrics.sh`

```sh
#!/bin/bash

# Create a token for IMDSv2 that expires after 60 seconds
TOKEN=`curl -X PUT "http://169.254.169.254/latest/api/token" -H "X-aws-ec2-metadata-token-ttl-seconds: 60" -s`

# Use the token to fetch the EC2 instance ID
INSTANCE_ID=`curl -H "X-aws-ec2-metadata-token: $TOKEN" -s http://169.254.169.254/latest/meta-data/instance-id`

# Get memory usage and put metric data to CloudWatch
MEMORY_USAGE=$(free | awk '/Mem/{printf("%d", ($2-$7)/$2*100)}')
aws cloudwatch put-metric-data --region us-east-1 --namespace "RAM Metrics" --metric-name "MemUsage" --value "$MEMORY_USAGE" --unit "Percent" --dimensions "Name=InstanceId,Value=$INSTANCE_ID"
```

### Installing stress package
```sh
sudo dnf install stress-ng -y
```

### Install crontab
```sh
sudo dnf install cronie -y
sudo systemctl enable crond
sudo systemctl start crond
```

### Add metrics.sh to crontab
```sh
crontab -e
```
```sh
* * * * * /home/ec2-user/metrics.sh
```

### Run the stres utility to generate load
```sh
stress-ng --vm 15 --vm-bytes 80% --vm-method all --verify -t 60m -v
```
- Create alarm & add SNS notifications
