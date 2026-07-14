# PYTHON MODULES
- Modules are used to import somebody else's code
- They are of three types: Custom-created, Build-in modules & External modules
- Build-in modules can be found here [https://docs.python.org/3/py-modindex.html]
- External modules can be installed via 'pip' (eg. pip install requests, requests module is used to fetch online urls)
- The dependency py files will be saved locally in your system
- Commonly used modules: requests, math, os, shutil, sys, boto3, botocore, etc.

## CUSTOM CREATING YOUR MODULE
- You can write you own modules & import them
- Keep your module in a separate file (eg. `mymodule.py`), you can give any name of your choice
- Call your module in your code using `mymodule.fn(x)`
  
### Simple 'Hello World' module
mymodule.py
```py
# Define your module
# File name: mymodule.py
def hello(name):
    return(f"Hello {name}")
```
main.py
```py
name = input('Enter your name: ')
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

### Square root function
mymodule.py
```py
def fn(x):
    return(x**0.5)
```
main.py
```py
x = int(input('Enter number: '))
import mymodule
print(mymodule.fn(x))
```
<img width="110.5" height="30.5" alt="image" src="https://github.com/user-attachments/assets/ff52c94d-6dd5-43c1-9944-2618bab57b32" />

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
