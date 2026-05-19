# ROUTE 53 HANDS-ON

### Create the Following in One Region (Example: N. Virginia)

1. Create Security Group (SG): Allow ports `22` and `80`
2. Create Target Group (TG): Give a name, Set **Advanced health checks** to `minimum`
3. Create Application Load Balancer (ALB)
4. Create Launch Template: Select **Amazon Linux OS**, Add the script in **User data**
5. Create Auto Scaling Group (ASG): Network: Choose `AZ-1a` and `AZ-1b`; Group size: Desired: `2`, Min: `2`, Max: `2`

Follow the same steps above and create SG, TG, ALB, ASG in another region (Example: Mumbai).

### Installation Script (LoadBalancer-1)

```sh
#!/bin/bash
sleep 30

sudo yum update -y
sudo yum install git httpd -y
service httpd start
chkconfig httpd on
git clone https://github.com/pandacloud1/webapp1.git && cd webapp1
cp * -R /var/www/html/
```

### Installation Script (LoadBalancer-2)

```sh
#!/bin/bash

sleep 30

sudo yum update -y
sudo yum install git httpd -y
service httpd start
chkconfig httpd on

git clone https://github.com/pandacloud1/webapp1-india.git && cd webapp1-india
cp * -R /var/www/html/
```

## Route 53
### Create Health Check

- Name: `<Give name>`
- Specify endpoint by: `Domain name`
- Protocol: `HTTP`
- Domain name: `<Load-Balancer-1-DNS-Name>`
- Path: `/index.html`
- `Create alarm: No` --> `Create health check`

### Create Routing Policy (For LoadBalancer-1)
- Route53 --> Hosted zones --> Select your hosted zone
- Create record: name:  ```text  (www).example.com  ```; Select:  Alias; Endpoint:  Alias to Application & Classic Load Balancer; Region:  <region-1>
- Routing policy: Failover
- Failover type: Primary

Follow the same steps above for `LoadBalancer-2`.

The only change will be:

```text
Failover type: Secondary
```

We can follow the same steps for other routing policy types as well.
