# FUNCTIONS
- Functions in python are used to reusable code
- Without functions, you need to write logic repetitively
- But with functions, you write the logic once and use it multiple times
- You can save the logic in a separate file & use it in your main code using `from <logic-file> import <function-name>`

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
