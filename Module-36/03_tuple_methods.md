# TUPLE METHODS
- Unlike list & set, tuple doesn't have many methods
- It has list of fixed (immutable) items
- It only supports `count` & `index`
- Although you can convert tuple to list/set & then use the methods

### count: Count the occurence of items
```py
fruits = ("apple", "banana", "cherry", "banana")

print(fruits.count("banana"))
```
##### Output
```sh
2
```

### index: Fetch the first index occurence of item
```py
fruits = ("apple", "banana", "cherry", "banana")
print(fruits.index("banana"))     # Output: 1
print(fruits.index("banana", 2))  # Output: 3
```

### Convert tuple to list
```py
fruits = ("apple", "banana", "cherry", "banana")

print(fruits.pop())
```
##### Output
```sh
['apple', 'banana', 'cherry']
```
