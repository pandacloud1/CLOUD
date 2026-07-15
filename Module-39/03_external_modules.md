## EXTERNAL MODULES
- You can directly use build-in modules in python using `import module`
- External modules can be installed via 'pip' (eg. `pip install requests`)

### REQUESTS MODULE
- Requests module is used to fetch online urls
- Install requests using `pip install requests`

```py
import requests
r = requests.get("https://www.example.com")
print(r.text)
```
<img width="575" height="100" alt="image" src="https://github.com/user-attachments/assets/e34d5877-c260-4988-a29d-858ec6694077" />

### PSUTIL MODULE
### Python system monitor (CPU, RAM & DISK USAGE)
- Install psutil using `pip install psutil`
```py
import psutil
import shutil

# CPU usage
print('#----- CPU -----#')
print("CPU Usage:", psutil.cpu_percent(interval=1), "%")

# RAM usage
memory = psutil.virtual_memory()
print('')
print('#----- RAM -----#')
print("Total RAM:", f"{memory.total / (1024**3):.2f} GB")
print("Used RAM:", f"{memory.used / (1024**3):.2f} GB")
print("Free RAM:", f"{memory.available / (1024**3):.2f} GB")
print("RAM Usage:", memory.percent, "%")

# Disk usage
usage = shutil.disk_usage("/")
def convert_bytes(size):
    for unit in ['Bytes', 'KB', 'MB', 'GB', 'TB']:
        if size < 1024:
            return f"{size:.2f} {unit}"
        size /= 1024
        
print('')
print('#----- DISK -----#')
print("Disk Total:", convert_bytes(usage.total))
print("Disk Used:", convert_bytes(usage.used))
print("Disk Free:", convert_bytes(usage.free))
```

## BOTO3 MODULE
- It is used for AWS services
- Install boto3 using command `pip install boto3`
- If you have multiple python version, then uninstall older versions
- Create an IAM user in AWS. Get the access key and secret key
- Run `aws configure` in your terminal & enter the access key and secret key
- You can now start using `boto3` module from your system

### List S3 bucket in your AWS account
- Ref: [https://docs.aws.amazon.com/boto3/latest/guide/quickstart.html]
```py
import boto3
s3 = boto3.resource('s3')
for bucket in s3.buckets.all():
    print(bucket.name)
```

### Creating an EC2 using `boto3` module
- Ref: [https://docs.aws.amazon.com/boto3/latest/guide/migrationec2.html#launching-new-instances]
- [https://docs.aws.amazon.com/boto3/latest/guide/ec2-example-managing-instances.html]
```py
import boto3

ec2 = boto3.client('ec2')

response = ec2.run_instances(
    ImageId='ami-08f44e8eca9095668',
    InstanceType='t2.micro',
    KeyName='Linux-key',
    MinCount=1,
    MaxCount=1
)

print("Created instance:", response['Instances'][0]['InstanceId'])
```

### Describe the EC2
```py
import boto3

ec2 = boto3.client('ec2')
response = ec2.describe_instances()
print(response)
```

### Get the instance IDs
```py
import boto3
ec2 = boto3.client('ec2')

# Describe all instances
response = ec2.describe_instances()

for reservation in response['Reservations']:
    for instance in reservation['Instances']:
        print("Instance ID:", instance['InstanceId'], 
              "State:", instance['State']['Name'])
```

### Delete the EC2
```py
import boto3
instance_id = input('Enter your instance id: ')
ec2 = boto3.client('ec2')

ec2.terminate_instances(InstanceIds=[instance_id])
print(f'The Instance "{instance_id}" has been deleted successfully')
```

### Delete the EC2 only if it exists or give error if doesn't exists
```py
import boto3
from botocore.exceptions import ClientError

instance_id = input('Enter your instance id: ')
ec2 = boto3.client('ec2')

try:
    ec2.terminate_instances(InstanceIds=[instance_id])
    print(f'The Instance "{instance_id}" has been deleted successfully')
except ClientError:
    print(f'Error: Instance "{instance_id}" does not
