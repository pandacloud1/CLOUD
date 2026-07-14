## WORKING WITH FILES (using 'with open')
### Reading a file
```py
file = input('Enter file to read: ')

with open(file, 'r') as f:
  content = f.read()
print(content)

# Explanation
# with: ensure to close the file automatically
# open(): It is a function used to open a file either in read, write or append mode
# r: read
# f: variable, file content is stored here
# read(): function to read a file
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
