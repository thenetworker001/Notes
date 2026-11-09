Python is ==dynamically typed==: no need to declare a variable's data type before using it. And data types are not permanently attached to the variable name it can be changed.
```python
x = 10; #No type declared
x = "hello" #Type changed later
```

---

Python is ==strongly typed==: it ensures what operations can be done on a object before an operation and doesn't silently converts the type (unlike other languages like C++ ...)
```python
x = 3
y = "10"
print(x+y) #TypeError since one is a string and other is number, it doesn't convert the type silently
```
For operations string must be converted to int : `int(y)` or `int("10")`

---

==Duck Typing==: For operations python doesn't care about the data types of objects (operands), it only checks whether the operation is possible or not.
```python
def show_length(obj):
print(len(obj))

show_length("hello")        # 5
show_length([1, 2, 3])      # 3
show_length({"a": 1, "b": 2})  # 2
```
Here passed objects are of different types but since they all supports `len()` operation, it works.

---

Variables/parameters/return types can be ==type hinted==, which means (program) reader can understand the expected type easily. But python doesn't enforce those types
```python
def addition(a:int, b:int) -> int:
	return a+b
```
Here expected arguments are int type and also does return type
But since python doesn't necessarily enforce these, this can also run:
```python
addtion("Hello"," World!") # returns "Hello World!"
```

Use Type Hinting:
- On function parameters and return types if possible (Especially on parent function if there is a sub function inside parent)
- If a function parameter is a  list, dict or set. so does return type
	```python
	def scan_target(target: str, ports: list[int]) -> list[int]:
    open_ports = []

    for port in ports:
        if check_port(target, port):
            open_ports.append(port)

    return open_ports
	```
- If there are multiple return types for a function
	```python
	def get_status() -> int | None:
	```
- On lists, dict or sets since any type can be stored especially if they are declared empty
	```python
	results: list[dict[str, str]] = []
	```
- Variables which expects a certain types
	```python
	port: int = 443 #to scan a port
	```

==Gradual Typing==: Program doesn't need to be fully type hinted at once or at first, we can modify the program later. Also a program can be partially type hinted

---

==Everything in python is an object==
Type can be checked by: `type()`
Functions are objects too, therefore they can be aliased (assign another name/variable to function):
```python
def greet():
	print("hello")

hello = greet
```
Now hello also refers to the same greet function. and function can be called as: hello()

Functions can be passed as arguments to function:
```python
def execute(func):
	func()
	
execute(greet)
```

Functions can also be stored in lists,sets,dict or tuples
```python
functions = [greet, print]

functions[0]()
functions[1]("Hello from Python")
```

Classes are objects too, and also instances of classes

---

Identity vs Equality
```python
a = [1, 2, 3]
b = [1, 2, 3]
c = a

print(a == b)  # True
print(a is b)  # False

print(a == c)  # True
print(a is c)  # True
```
- `==` - Are values equal?
- `is` - Are they exact same object

---
Mutable - Object content can be changed without creating a new object. eg: lists,set,dict..
```python
a = [1, 2, 3]
b = a

b.append(4)

print(a) #[1,2,3,4]
print(b) #[1,2,3,4]
```
Immutable - a new object is created if content is modified. eg: variables, tuples..etc..
```python
a = 10
b = a

b += 5

print(a)  # 10
print(b)  # 15
```

---

None means nothing/null, absence of value
It is not equal to 0," ", or False
None is only equal None itself therefor use `is` for comparison
It is a singleton object (there is exactly one instance to it):
```python
a = None
b = None

print(a is b)  # True
```
For a function if no explicit return type mentioned it returns None or also if it doesn't match any mentioned cases