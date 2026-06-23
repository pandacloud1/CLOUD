# LIST METHODS

### (append): Add item at the end of list
```py
fruits = ["apple", "banana", "cherry"]
fruits.append("orange")
print(fruits)
```
##### Output
```sh
['apple', 'banana', 'cherry', 'orange']
```

### (insert): Add item anywhere
```py
fruits = ["apple", "banana", "cherry"]
fruits.insert(0,"orange")
print(fruits)
```
##### Output
```sh
['orange', 'apple', 'banana', 'cherry']
```

### (pop): Remove item at the end or as per index
```py
# Remove item at the end
fruits = ["apple", "banana", "cherry"]
fruits.pop()
print(fruits)
```
##### Output
```sh
['apple', 'banana']
```

```py
# Remove item at the index no 0
fruits = ["apple", "banana", "cherry"]
fruits.pop(0)
print(fruits)
```
##### Output
```sh
['banana', 'cherry']
```

### (remove): Remove only one occurence
```py
fruits = ["apple", "banana", "cherry","banana","banana"]
fruits.remove("banana")
print(fruits)
```
##### Output
```sh
['apple', 'cherry', 'banana', 'banana']
```

### (remove): Remove & while loop: Remove all occurences
```py
fruits = ["apple", "banana", "cherry","banana","banana"]
while "banana" in fruits:
    fruits.remove("banana")
print(fruits)
```
##### Output
```sh
['apple', 'cherry']
```

### (count): Count all occurences of an item
```py
fruits = ["apple", "banana", "cherry","banana","banana"]

number = fruits.count("banana")
print(number)

# or
# print(fruits.count("banana"))
```
##### Output
```sh
3
```

### (sort): Sort items
```py
fruits = ["apple", "banana", "cherry","banana","banana"]

fruits.sort()
print(fruits)
```
##### Output
```sh
['apple', 'banana', 'banana', 'banana', 'cherry']
```

### (reverse): Reverse items
```py
fruits = ["apple", "banana", "cherry","dates","guava"]
fruits.reverse()
print(fruits)
```
##### Output
```sh
['guava', 'dates', 'cherry', 'banana', 'apple']
```

### (index): Get the index no of an item
- We can fetch the index of an item
- This is not possible with set
```py
fruits = ['apple', 'banana', 'cherry']
print(fruits.index('banana'))
```
##### Output
```sh
1
```
