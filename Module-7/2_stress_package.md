## INSTALL STRESS PACKAGE IN AMAZON LINUX 2023

```sh
sudo dnf update -y
sudo dnf install stress -y
```

Trigger CPU using below command
```sh
stress --cpu 4 --timeout 60s
```


## Installing stress package in Amazon Linux 2
REF: [https://gist.github.com/mikepfeiffer/d27f5c478bef92e8aff4241154b77e54]

```sh
sudo amazon-linux-extras install epel -y
sudo yum install stress –y
stress –-cpu 40
```

OPTIONAL
- We can also trigger CloudWatch test alarm by running below command in EC2
- REF: [https://docs.aws.amazon.com/cli/latest/reference/cloudwatch/set-alarm-state.html]
```sh
aws cloudwatch set-alarm-state --alarm-name "myalarm" --state-value ALARM --state-reason "testing purposes"
```
