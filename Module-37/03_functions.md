# FUNCTIONS
- Functions in python are used to reusable code
- Without functions, you need to write logic repetitively
- But with functions, you write the logic once and use it multiple times
- You can save the logic in a separate file & use it in your main code using `from <logic-file> import <function-name>`
- But mostly, writing the logic in a separate file is a practise followed in module.
- So function is a small block of code & module is an entire file containing the complete logic

## Why Functions?
- Reusability:	    You can call function anywhere in your program without rewriting the logic.
- Readability:	    The function instantly & clearly tells what the code does.
- Maintainability:	If you later change the logic (e.g., add validation or logging), you only update the function, not change every place you used the logic.
- Scalability:	    Functions make large programs modular — each part handles one task.
- Testing:	        You can easily test square() separately, which is great for debugging.

Without a function: You’re repeating the same logic three times.
```py
x = 5
print(x*x)
y = 10
print(y*y)
z = 25
print(z*z)
```
With a function: Logic written once, used multiple times
```py
def square(num):
    return num*num

print(square(5))
print(square(10))
print(square(25))
```

## Login System
```py
user = input("Enter your username: ")
password = input("Enter your password: ")

# Dictionary of users and passwords
users = {
    "admin": "1234",
    "panda": "1234",
    "nasir": "1234"
}

# Define the function
def login(user, password):
    if user in users and users[user] == password:
        return "Login Successful"
    else:
        return "Access Denied"

# Call the function
print (login(user, password))
```

Doc string
```py
def sum(a,b):
    '''This function will sum two numbers'''
    c = a+b
    return c
print(sum.__doc__)
# Output: This function will sum two numbers
```
### Sum function
```py
def sum(a,b,c):
    x = a+b+c
    print (x)
sum(1,2,3)
```
<img width="32" height="20" alt="image" src="https://github.com/user-attachments/assets/bce8b174-518c-428e-8c6b-8bb699f381bb" />

### Divide function
```py
a = int(input("Enter num 1: "))
b = int(input("Enter num 2: "))
def div(a,b):
    if b==0:
        return("Cannot divide my zero")
    else:
        return(a/b)
print(div(a,b))
```
<img width="146" height="49" alt="image" src="https://github.com/user-attachments/assets/6b6939fe-f542-459a-907b-b24693f1fe13" />

### Return as single string
```py
def full_name(first, last):
    return (f"{first} {last}")
print(full_name("Panda", "Cloud"))
```
<img width="89" height="20" alt="image" src="https://github.com/user-attachments/assets/7e91a411-66a7-4bab-99db-af64e2983fc5" />

### Calculate area of square/rectangle
```py
# Calculate area of square/rectangle
def area(l,w):
    return l*w
print(area(30,40))
```
```txt
1200
```

### Multiply function
Using positional arguments
```py
def multiply(a,b,c):
    x = a*b*c
    print (x)
multiply(4,5,6)
```

Using default arguments
```py
def multiply(a=4,b=5,c=6):
    x = a*b*c
    print (x)
multiply()
```
<img width="37" height="21" alt="image" src="https://github.com/user-attachments/assets/0cc46e95-5b39-40e3-b997-31547abb9a02" />

Overwriting default arguments
```py
def multiply(a=4,b=5,c=6):    # default arguments
    x = a*b*c
    print (x)
multiply(10,11,12)            # overwriting arguments
```
<img width="43" height="20" alt="image" src="https://github.com/user-attachments/assets/401b4ac1-762a-44a2-bd68-8bb93279b4dc" />


### Average function
```py
def average(a,b,c):     # here a,b,c are parameters
    avg = (a+b+c)/3
    print(avg)

average(1,2,3)          # here 1,2,3 are arguments
average(4,5,6)
average(7,8,9)
```
<img width="71" height="49" alt="image" src="https://github.com/user-attachments/assets/44fe6b6f-2c82-41b7-86a7-d5aeef04d25d" />

Using return to store value in variable
```py
def average(a,b,c):
    avg = (a+b+c)/3
    return avg

a1 = average(1,2,3)
a2 = average(4,5,6)
a3 = average(7,8,9)
print(a1,a2,a3)
```
<img width="84" height="19" alt="image" src="https://github.com/user-attachments/assets/c21a41b2-441c-4a3a-b0a9-0f9f183f8eca" />

## LAMBDA FUNCTION
- It is a one liner function
- It will help you to save multiple lines of code
  
### Lambda - Sum function
```py
sum = lambda a,b: a+b
print(sum(2,3))

# Used instead of:
# def sum(a,b):
#     z = a+b
#     print(z)
# sum(2,3)
```
<img width="32" height="16" alt="image" src="https://github.com/user-attachments/assets/f06ab0e7-a974-4e9f-93c4-add59f5a74a0" />

### Lambda - Multiply function
```py
multiply = lambda a,b: a*b
print(multiply(4,5))
```

### Lambda - Add 3 nos
```py
a = int(input("Enter no.1: "))
b = int(input("Enter no.2: "))
c = int(input("Enter no.3: "))
sum = lambda a,b,c: a+b+c
print("The sum is: ")
print(sum(a,b,c))
```
<img width="125" height="83" alt="image" src="https://github.com/user-attachments/assets/ef9c01f4-65bf-4212-9020-a627c659d640" />

### Lambda - Print square of list [Using map()]
```py
nums = [1,2,3,4,5]
square = lambda x: x*x

print(list(map(square, nums)))
```
<img width="118" height="22" alt="image" src="https://github.com/user-attachments/assets/99f939c9-de08-483d-a9e2-75bd16802b73" />


## RECURSION
- Recursion is where a function calls itself again & again
- Sometimes, we may need to define the base case (values) in recursion

### Factorial function
```py
n = int(input("Enter a number: "))
def fact(n):
    if n==0 or n==1:
        return 1
    # recursive function
    return n * fact(n-1)

print(fact(n))
```
<img width="124" height="37" alt="image" src="https://github.com/user-attachments/assets/158f1747-fc51-4b57-a8bf-7e64909dc178" />

### Recursive function - Sum of digits
```py
n = int(input("Enter a multi-digit number: "))
def sum_of_digits(n):
    if n==0:
        return 0
    return (n%10) + sum_of_digits(n//10)
print(sum_of_digits(n))

"""
Explanation
sum_of_digits(123) returns (123 mod{10}) + sum_of_digits(123//10)
3 + sum_of_digits(12)
--> 3+3 = 6

sum_of_digits(12) returns (12 \mod{10}) + sum_of_digits(12//10)
2 + sum_of_digits(1)
--> 2+1 = 3

sum_of_digits(1) returns (1 mod{10}) + sum_of_digits(1//10)
1 + sum_of_digits(0)
--> 1+0 = 1

sum_of_digits(0) hits the base case and returns 
0

==> 3+2+1 = 6
"""
```
<img width="259" height="34" alt="image" src="https://github.com/user-attachments/assets/6df268d1-fe35-48e5-b346-b6e77c1875e6" />

### Fibonacci series
```py
### Fibonacci series
"""
0 1 1 2 3 5 8 13 21 ...   # Fibonacci
0 1 2 3 4 5 6 7 8 9 ...   # Index

f(0) = 0
f(1) = 1
f(2) = f(0)   + f(1)
f(n) = f(n-2) + f(n-1)
"""
x = int(input("Enter the fibonacci length: "))
def f(n):
    if (n==0 or n==1):
        return n
    else:
        return f(n-2) + f(n-1)

for n in range(0,x):
    print(f(n))
```
<img width="241" height="170" alt="image" src="https://github.com/user-attachments/assets/b278cb07-b6bf-43c4-bc97-9cc8176d1385" />

Alternate program (without functions)
```py
### Fibonacci
x = int(input("Enter the fibonacci length: "))
a = 0
b = 1
if (x==0 or x==1):
    print(a)
    print(b)
else:
    print(a)
    print(b)
    for i in range(2,x):
        c = a+b
        print(c)
        # Shift values
        a=b
        b=c
```
