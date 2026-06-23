## STRINGS

### INDEX
#### Print letters of a string in fwd/reverse order
```py
name = "PANDA"
print(name[0])
print(name[1])
print(name[2])
print(name[3])
print(name[4])
print()
print(name[-1])
print(name[-2])
print(name[-3])
print(name[-4])
print(name[-5])
print(name[::-1])  # reverse string
```
<img width="165" height="189" alt="image" src="https://github.com/user-attachments/assets/8b9a3b32-08ce-4bfa-94eb-f444d9b3a75f" />

### STRING SLICING
#### Used to pick specific characters from a string
```py
name = "PANDACLOUD"  # word length = 10
print(name[0:5])     # goes from 0 to (5-1)
print(name[5:])      # goes from 5th index character (or 6th letter) to last character 
print(name[0:10:2])  # keeps [(2-1=1] consecutive characters
print(name[0:10:3])  # keeps [(3-1)=2] consecutive characters
print(name[0:])      # considers last character
print(name[:])       # considers first & last character
print(name[:-1])     # skips the last character
# Note: Strings are immutable, you cannot replace string or index values
# name = "Panda"
# name[0] = "D"
# TypeError: 'str' object does not support item assignment
```
<img width="116" height="111" alt="image" src="https://github.com/user-attachments/assets/668913bb-1642-488f-9704-ec5a7f049730" />

### STRING METHODS
#### Cases
```py
name = "panda cloud"
print(len(name))
print(name.upper())
print(name.lower())
print(name.capitalize())  # Only first letter
print(name.title())       # First letter of each word
```
<img width="150" height="80" alt="image" src="https://github.com/user-attachments/assets/715ab8f0-dbeb-44ab-9908-fcce8e10c0b7" />

#### Whitespaces
```py
name = " Panda Cloud "
print(name.strip())    # removes whitespaces from left & right
print(name.lstrip())   # removes whitespace from left
print(name.rstrip())   # removes whitespace from right
```
<img width="131" height="50" alt="image" src="https://github.com/user-attachments/assets/26d394c0-8212-4216-8709-63d3c69ec676" />

#### Find, Replace & Count
```py
name = "Panda Cloud"
print(name.find("d"))                    # tells the index position of letter
print(name.replace("Cloud", "Academy"))  # Replace 'Cloud' --> 'Academy'
print(name.count("a"))                   # counts no of a's
```
<img width="140" height="52" alt="image" src="https://github.com/user-attachments/assets/ad14a671-1118-4c59-bfda-f4e9e97450f5" />

#### String --> List (& vice versa)
```py
name1 = "Panda,Cloud,Academy"           # string
name2 = ["Panda", "Cloud", "Academy"]   # list
print(name1.split(","))                 # string --> list
print(",".join(name2))                  # list --> string
```
<img width="222" height="35" alt="image" src="https://github.com/user-attachments/assets/f7cc4929-7436-4198-b491-05d86ff1a843" />

#### String properties
```py
name = "panda"
year = "2023"
github = "pandacloud1"
youtube = " \t "
print(name.isalpha())
print(year.isdigit())
print(github.isalnum())
print(youtube.isspace())
```
<img width="116" height="67" alt="image" src="https://github.com/user-attachments/assets/46f09253-a803-4963-8941-4d20105b8f4e" />

#### String format
```py
name = "Panda"
age = 5
print(f"My name is {name} & my age is {age}")
```
<img width="215" height="21" alt="image" src="https://github.com/user-attachments/assets/12fd2703-1342-441b-b02b-84d54259ea12" />

#### count vowels 
```py
vowels = ["a","e","i","o","u"]
sentence = "Coding in Python is fun" 

sum=0
for i in sentence.lower():
    if (i in vowels):
        sum += 1
print(f"There are {sum} vowels in this sentence")
```
<img width="238" height="20" alt="image" src="https://github.com/user-attachments/assets/8763e4fe-6f04-4916-a7e3-a627b393db7f" />

#### Check if palindrome or not
```py
text = input("Enter any word: ")
if text == text[::-1]:
    print("It is palindrome")
else:
    print("It is not palindrome")
```
<img width="165" height="37" alt="image" src="https://github.com/user-attachments/assets/202f6170-e746-4111-809a-d6471b32f735" />
