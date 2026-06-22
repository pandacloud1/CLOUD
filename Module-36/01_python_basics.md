## LIST METHODS

### Remove only one occurence
```py
fruits = ["apple", "banana", "cherry","banana","banana"]
fruits.remove("banana")
print(fruits)
```
### Output
```sh
['apple', 'cherry', 'banana', 'banana']
```

### Remove all occurences
```py
fruits = ["apple", "banana", "cherry","banana","banana"]
while "banana" in fruits:
    fruits.remove("banana")
print(fruits)
```
### Output
```sh
['apple', 'cherry']
```
