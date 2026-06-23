# LOOPS

### FOR LOOP
```txt
for loop = Fixed biscuits in a box
You have 10 biscuits → eat one by one until finished.
You already know the count = 10

for = count controlled
use case: Lists, ranges, files
```

### WHILE LOOP
```txt
while loop = Eat until hungry
You keep eating while you are hungry.
You don’t know how many biscuits you’ll eat — depends on condition (hunger)

while = condition controlled
use case: User input, waiting, conditions
```


## FOR LOOP
### Print table of 5
```py
for i in range (1, 11):    # [range is from 1 to (11-1) 10]
    print ("5 x", i, "=", (i)*5)
```
Output<br>
<img width="131" height="154" alt="image" src="https://github.com/user-attachments/assets/2b8b0f73-981b-452b-8bd3-4e75a08d00d8" />

### Print * in pyramid
```py
for i in range(1,6):
    print(i*"*")
```
Output<br>
<img width="133" height="80" alt="image" src="https://github.com/user-attachments/assets/ba388a76-6ee2-4a75-a806-bb9dcd87d986" />


### Print any multiplication table
```py
n = int(input("Enter a number for multiplication table: "))

for i in range (1, 11):
    print (n, "x", i, "=", i*n)
```

## WHILE LOOP
### Infinite loop (ICAI)
```py
while True:
    print("This is infinite loop!!")
```

### Print 1 to 5 (ICAI)
```py
i = 1         # initial value
while i<6:    # condition
    print(i)  # 1 2 3 4 5 exit (Output)  # argument
    i+=1      # 2 3 4 5 6                # increment
```

### Ask the user to enter a password until they enter the correct one
```py
while True:
  prompt = input("Enter password: ")
  if prompt == "pass":
      print("Correct password")
      break
```
