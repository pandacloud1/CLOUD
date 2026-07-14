## BUILT-IN MODULES
- Build-in modules can be found here [https://docs.python.org/3/py-modindex.html]
- You can simply import build-in modules & use them
- So you do not need to write functions for square, square root, add, sum, etc, as they are already provided in 'math' module
- Other examples are also given below

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
