## INSTALL EFS IN AMAZON LINUX
- REF: [https://docs.aws.amazon.com/efs/latest/ug/installing-amazon-efs-utils.html]

- Create two EC2 instances
- Create Security group & allow SSH, HTTP, HTTPS & NFS
- Create EFS in same AZ as EC2 & attach the same Security group created for EC2
- Install EFS package (client) & run commands in all EC2 instances

```sh
sudo su -
yum update -y
yum install amazon-efs-utils -y
```

Created directory (mount point)
```sh
mkdir efs
# Paste the command from EFS --> Attach --> Using the EFS mount helper
```

Go inside the directory & run required commands
```sh
cd efs
touch file1 
# The 'file1' created in 'Server1' will be visible in 'Server2'
```
