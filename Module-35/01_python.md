# PYTHON

## Install Python
* Install VS Code: [https://code.visualstudio.com/download](https://code.visualstudio.com/download)
* Install Python: [https://www.python.org/downloads/](https://www.python.org/downloads/)
* Create a file with a `.py` extension (e.g., `test.py`)
* Run the file using `py` as a prefix (e.g., `py test.py`)
* Alternatively, you can directly click the **Run** button in VS Code to execute Python code

## VS Code Shortcuts
* Comment/uncomment lines → `Ctrl + /`
* To indent  → `Ctrl + ]` & unindent  → `Ctrl + [`
* Duplicate the current line  → `Alt + Shift + ↓`
* Modify multiple texts together: Click on text → Hold `Alt` and click on another text → Edit both simultaneously
* Settings → Settings → Commonly Used → **Editor: Mouse Wheel Zoom** → Enable it to zoom files using `Ctrl + Mouse Wheel` or `Touchpad`
* Top → Search → `>Developer: Toggle Screencast Mode` → Shows keyboard shortcuts on screen

## Standard Rules
* Always save file with .py extension
* Use lowercase (with underscores) for file names, variables & functions → : `my_script.py`
* Use UPPERCASE for constants → : `PI = 3.14`
* Use 4 spaces for indentation, do not use TAB
* Max 79 characters allowed per line
* Use `#` for short comments & `"""` for long comments (docstring)

## Python Data Types
* String       → `name = "Panda"`
* Integer      → `age = 5` (Note: numbers inside quotes become strings)
* Float        → `version = 1.2`
* Boolean      → `True / False` (First letter uppercase, no quotes)
* List         → `[1, 2, 3, 4]` (changeable / mutable)
* Tuple        → `(1, 2, 3, 4)` (fixed / immutable)
* Set          → `{1, 2, 3, 4}`
* Dictionary   → `{"name": "panda", "age": 5}`

## User Input
* The `input()` function is used to take input from the user
* By default, input is treated as a **string**

<img width="446" height="191" alt="image" src="https://github.com/user-attachments/assets/f6482c73-c0b5-4e30-b92b-62f0871214f8" />

## Script output
* The `print()` function is used to provide output of the script

## Python data types testing using code
```py
name = "panda"
print(type(name))

num = 123
print(type(num))

pi = 3.142
print(type(pi))

out = True
print(type(out))

item = ['milk', 'eggs']
print(type(item))

cards = {'ace', 'king', 'queen'}
print(type(cards))

gift = ('chocolate', 'honey', 'greentea')
print(type(gift))

dictt = { 
    'bank': ['finance', 'river edge'], 
    'bat': ['animal', 'sports equipment']
}

print(type(dictt))
```
<img width="166" height="175" alt="image" src="https://github.com/user-attachments/assets/9468737f-ab70-4e99-a943-0ee277de5d32" />

## Variables
* Variables are used to store values
* Variables can include letters, underscores, and numbers
* They cannot start with a number
* Variables are case-sensitive
* Do not use standard Python keywords (e.g., `if`, `else`, `for`, `while`)

## Typecasting in Python
* It is used to convert one data type into another

### Example: String to Integer

```py
a = "5"
print(type(a))   # Output: <class 'str'>
b = int(a)
print(type(b))   # Output: <class 'int'>
```

### Example: Integer to String

```py
a = 5
b = str(a)
```

## Why Typecasting is Required?
- The below program which is a bit lengthy
<img width="445" height="313" alt="image" src="https://github.com/user-attachments/assets/4cbb3b3d-3055-4034-bdeb-7499ae50a9e0" />

- It will get simplified by using typecasting
<img width="450" height="112" alt="image" src="https://github.com/user-attachments/assets/0df11fb8-c2ca-4a82-bf6a-c26012523aff" />

## Using New Lines & Tabs

* `\n` → New line
* `\t` → Tab space
<img width="450" height="152" alt="image" src="https://github.com/user-attachments/assets/63b00c11-8de9-44bc-927f-3af98b00f9f5" />

## Print Formatting

* By default, **space** is used as a separator in `print()`
* You can change the separator using `sep`
* Use `end` to control what prints at the end of the line
* Use `end=""` to avoid moving output to the next line

<img width="600" height="164" alt="image" src="https://github.com/user-attachments/assets/8b1d5cdc-8522-44ad-894e-7652a6c2c76e" />
