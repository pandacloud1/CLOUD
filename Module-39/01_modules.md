# PYTHON MODULES
- Modules are used to import somebody else's code
- They are of three types: Custom-created, Build-in modules & External modules
- Build-in modules can be found here [https://docs.python.org/3/py-modindex.html]
- External modules can be installed via 'pip' (eg. pip install requests, requests module is used to fetch online urls)
- The dependency py files will be saved locally in your system
- Commonly used modules: requests, pandas, numpy, math, os, sys, boto3, botocore, etc.

## CUSTOM CREATING YOUR MODULE
- You can write you own modules & import them
- Keep your module in a separate file (eg. `module.py`), you can give any name of your choice
- Call your module in your code using `module.fn(x)`
  
### Simple 'Hello World' module
mymodule.py
```py
# Define your module
# File name: mymodule.py
def hello():
    print("Hello World")
```
main.py
```py
import mymodule
mymodule.hello()
```
<img width="92" height="19" alt="image" src="https://github.com/user-attachments/assets/d184966d-5ec3-4d2b-a966-15e5e51e06ec" />

### Sum module (using sum function)
mymodule.py
```py
# File name: mymodule.py
def sum(a,b,c):
    x = a+b+c
    print (x)
```
main.py
```py
import mymodule
mymodule.sum(1,2,3)
```
<img width="29" height="21" alt="image" src="https://github.com/user-attachments/assets/ad715f53-300c-4367-9810-c118af76f6c7" />

### Square module
mymodule.py
```py
def square(x):
    return(x*x)
```
main.py
```py
num = int(input("Please enter any num: "))
import mymodule
print(mymodule.square(num))
```
<img width="166" height="34" alt="image" src="https://github.com/user-attachments/assets/a3b71b3c-b278-42b5-8386-e5e409390550" />

### Check if number is even/odd
mymodule.py
```py
def is_even(n):
    if n%2==0:
        return True
    else:
        return False
```
main.py
```py
n = int(input("Enter a number to check even/odd: "))
import mymodule
print(mymodule.is_even(n))
```
<img width="236" height="32" alt="image" src="https://github.com/user-attachments/assets/c40859cd-f66d-44f9-a377-bac352cc1302" />

## WORKING WITH FILES (using 'with open')
### Reading a file
```py
file = input('Enter file to read: ')

with open(file, 'r') as f:
  content = f.read()
print(content)
```
```txt
# output
Enter file name to read: test.txt
This is a test file
```

### Writing to a file (overwriting existing content)
```py
file = input('Enter the file name: ')
content = input('Enter the content to add to the file: ')

with open(file, 'w') as f:
    add = f.write(content)
print('Content added successfully! Please check the file.')
```
```txt
# output
Enter the file name: test.txt
Enter the content to add to the file: new line added!
Content added successfully! Please check the file
```

### Writing to a file (retaining existing content)
```py
file = input('Enter the file name: ')
content = input('Enter the content to add to the file: ')

with open(file, 'a') as f:                  # a = append
    add = f.write('\n' + content)
print('Content added successfully! Please check the file.')
```
```txt
# output
Enter the file name: test.txt
Enter the content to add to the file: new line 2 added!
Content added successfully! Please check the file
```

Note:
- What if file doesn't exists?
  - read will throw an error 
  - write/append will create a file

## BUILT-IN MODULES
- Build-in modules can be found here [https://docs.python.org/3/py-modindex.html]
- You can simply import build-in modules & use them

### OS MODULE
### Print current working directory
```py
import os
print(os.getcwd())                                             
```

### Check if file exists
```py
import os
print(os.path.exists("dir"))          
```  

```py
import os

filename = input('Enter file name: ')

if os.path.exists(filename):
    print("File exists!")
else:
    print("File does not exist!")
```
```txt
# output
Enter file name: test.txt
File exists!
```

### Check if file exists & read the file
```py
import os
filename = input('Enter file name: ')

if os.path.exists(filename):
    with open(filename, "r") as f:   # open in read mode
        content = f.read()
        print('File exists & below are the contents')
        print(content)
else:
    print("File not found!")
```

### List files & directories
```py
import os
print(os.listdir("dir"))  
# list dir/files inside dir, use 'r' = raw string for complete path
```

### Removes files
```py
import os
os.remove("<file-name>")    

### Remove empty directories
```py
import os                                 
os.rmdir("abcdir")
```
```py
import os 
print('NOTE: THIS WILL DELETE EMPTY DIRECTORIES ONLY!')
print('To delete directories with content use shutil module "rmtree"')
dir = input('Enter directory name: ')

if os.path.exists(dir):
    os.rmdir(dir)
    print('Directory has been deleted')
else:
    print('Directory not found!')
```


### SHUTIL MODULE
### Remove directories with content
```py
import shutil
shutil.rmtree("abcdir")
```

```py
import os
import shutil

print('WARNING: Note that this will delete directories & its contents permanently')
dir = input('Enter directory name to delete: ')

if os.path.exists(dir): 
    shutil.rmtree(dir)
    print('Directory has been deleted!')
else:
    print('Directory not found')
```

### Create a copy of a file
```py
import shutil
shutil.copy("file1.txt", "new-file1.txt")
```

### Create a copy of a directory
```py
import shutil
shutil.copytree('dir', 'new-dir')
```

### Move file or directory
```py
import shutil
shutil.move("dir/file1.txt", "new-dir/file1.txt")
```

### Archive (zip) a directory (for backup)
```py
import shutil
shutil.make_archive("backup", "zip", "dir")
```
```txt
# output
backup.zip will be created from 'dir'
```

### Disk usage
```py
import shutil
usage = shutil.disk_usage("/")
print("Total:", usage.total, "Used:", usage.used, "Free:", usage.free)

```

### Disk usage (Human readable)
```py
import shutil

def convert_bytes(size):
    # Convert bytes into KB, MB, GB, TB
    for unit in ['Bytes', 'KB', 'MB', 'GB', 'TB']:
        if size < 1024:
            return f"{size:.2f} {unit}"
        size /= 1024

usage = shutil.disk_usage("/")

print("Total:", convert_bytes(usage.total))
print("Used:", convert_bytes(usage.used))
print("Free:", convert_bytes(usage.free))
```

### MATH MODULE
### Factorial of a number
```py
import math
print('Find the factorial of any number')
x = int(input('Enter any number: '))
print(math.factorial(x))
```
```txt
# output
Enter any number: 5
120
```

### Square root of a number
```py
import math
print('Find the square root of any number')
num = int(input('Enter any number: '))
print(math.isqrt(num))
```
```txt
# output
Enter any number: 16
4
```

### Power of a number
```py
import math
print('Find the power of any number')
x = int(input('Enter any number: '))
y = int(input('Enter the power: '))
print(int(math.pow(x,y)))
```
```txt
# output
Find the power of any number
Enter any number: 2
Enter the power: 8
256
```

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
- If you have multiple python version, then ensure you install boto3 in correct version or uninstall older python versions
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
- Ref: [https://docs.aws.amazon.com/boto3/latest/guide/ec2-example-managing-instances.html]
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
    print(f'Error: Instance "{instance_id}" does not exist')
```
