## Conditional Statements

### If-else (Check eligibility to vote)
```py
age = int(input("Enter your age: "))
if age >= 18:
    print("You are elgible to vote")
else:
    print("You are not eligible to vote")
```

### If-else (Check if number is even or odd)
```py
num = int(input("Enter a number: "))
if num % 2 == 0:
    print("Number is Even")
else:
    print("Number is Odd")
```

### If-else (Check if number is positive, negative, or zero)
```py
num = int(input("Enter a number: "))
if num > 0:
    print("Number is positive")
elif num == 0:
    print("Number is zero")
else:
    print("Number is negative")
```

### If-elif-else statement (Check BMI)
```py
weight = float(input("Enter weight in kg: "))
height = float(input("Enter height in metres: "))

bmi = (weight/height**2)
print (f"bmi is {bmi}")

if (bmi>30):
    print("You are obese")
elif (25<bmi<=30):
    print("You are overweight")
elif (18<=bmi<25):
    print("You have an ideal weight")
else:
    print("You are underweight")
```

### Match case statement (Lucky number)
```py
a = int(input("Enter any number from 1 to 5: "))

match a:
    case 1: 
        print("You won a toy gun!")
    case 2:
        print("You won Nike shoes!")
    case 3:
        print("You won free movie ticket!")
    case 4:
        print("You won a vacation package!")
    case _:
        print("Sorry! Better luck next time")
```

### Match case statement (Enter a day number (1–7) and print the corresponding day)
```py
day = int(input("Enter a number from 1-7: "))

match day:
    case 1:
        print("Sunday")
    case 2:
        print("Monday")
    case 3:
        print("Tuesday")
    case 4:
        print("Wednesday")
    case 5:
        print("Thursday")
    case 6:
        print("Friday")
    case 7:
        print("Saturday")
    case _:
        print("Invalid input")
```

### Enter two numbers & perform operations
```py
a = int(input("Enter number 1: "))
b = int(input("Enter number 2: "))
operator = input("Choose operator (+,-,*,/): ")

match operator:
    case "+":
        print(a+b)
    case "-":
        print(a-b)
    case "*":
        print(a*b)
    case "/":
        print(a/b)
```
