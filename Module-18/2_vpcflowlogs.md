## TESTING FLOW LOGS

- VPC Flow Logs capture network traffic logs at the VPC level.
- Flow Logs are NOT real-time; they usually take 2–5 minutes to appear in CloudWatch.

### Commands to Run in EC2

```sh
curl https://example.com
````

### Check Logs in CloudWatch

* Go to: `CloudWatch --> Logs --> <Your Log Group>`
* Select **Filter events**
* Enter the following filter:

```sh
<EC2-Private-IP> 443 ACCEPT
```

* Hit **Enter**
* Wait for a few minutes if logs are not appearing immediately.
* * Visit [https://www.nslookup.io/website-to-ip-lookup/] to get IP associated with `example.com`

### Example Log Explanation

| Field            | Meaning                      |
| ---------------- | ---------------------------- |
| `10.0.1.41`      | Your EC2 private IP          |
| `172.66.147.243` | example.com public IP        |
| `56608`          | Random ephemeral source port |
| `443`            | HTTPS destination port       |
| `ACCEPT`         | Traffic allowed              |

### Example Screenshot
<img width="1876" height="473" alt="image" src="https://github.com/user-attachments/assets/bba0a2b9-aa01-4c10-8ec6-8e3e9f471a95" />

