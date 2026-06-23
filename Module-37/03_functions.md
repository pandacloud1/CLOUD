# FUNCTIONS
- Functions in python are used to reusable code
- Without functions, you need to write logic repetitively
- But with functions, you write the logic once and use it multiple times
- You can save the logic in a separate file & use it in your main code using `from <logic-file> import <function-name>`

## Why Functions?
- Reusability	    You can call function anywhere in your program without rewriting the logic.
- Readability	    The function instantly & clearly tells what the code does.
- Maintainability	If you later change the logic (e.g., add validation or logging), you only update the function, not change every place you used the logic.
- Scalability	    Functions make large programs modular — each part handles one task.
- Testing	        You can easily test square() separately, which is great for debugging.

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

You can save the function in a separate file & call it as below
```py
# File name: logic.py
def square(num):
    return num*num
```
```py
# File name: main.py
# Call the function from separate file
from logic import square
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

You can store your functions & user credentials in a separate file
```py
# File name logic.py
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
```
```py
File name: main.py
from logic import login
user = input("Enter your username: ")
password = input("Enter your password: ")

# Call the function
print (login(user, password))
```
