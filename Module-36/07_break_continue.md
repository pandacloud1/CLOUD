## Break, Continue & Pass

### break
```py
for i in range(1, 11):
    if i == 6:
        break
    print(i)
```
Output (Number 6 and later have been skipped) <br>
<img width="129" height="79" alt="image" src="https://github.com/user-attachments/assets/f1044102-c0d6-45a1-9d08-39e36679100d" />


### continue
```py
for i in range(1, 11):
    if i == 6:
        continue    # '6' will be skipped
    print(i)
```
Output (Only '6' has been skipped) <br>
<img width="177" height="140" alt="image" src="https://github.com/user-attachments/assets/8e57e37d-a96f-4a37-b7d3-d69539936677" />

### pass
```py
### Used when we want to use condition later
i = 3
if i==3:
    pass  # do nothing
```
