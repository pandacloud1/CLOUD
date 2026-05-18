## TESTING FLOW LOGS
- VPC Flow logs captures logs are VPC level
- Flow logs are NOT real-time, they usually take 2-5 minutes to appear

### Commands to run in EC2
```sh
curl https://example.com
```

### Check logs in CloudWatch
- Go to Cloudwatch --> Logs --> <Your Log group>
- Select Filter events --> `<EC2-Private-IP> 443 ACCEPT` --> Hit Enter
- You will see logs, wait for few mins if not appearing
- In below example
```sh
| Field            | Meaning                      |
| ---------------- | ---------------------------- |
| `10.0.1.41`      | Your EC2 private IP          |
| `172.66.147.243` | example.com public IP        |
| `56608`          | Random ephemeral source port |
| `443`            | HTTPS destination port       |
| `ACCEPT`         | Traffic allowed              |
```
- Example screenshot
<img width="1876" height="473" alt="image" src="https://github.com/user-attachments/assets/bba0a2b9-aa01-4c10-8ec6-8e3e9f471a95" />
