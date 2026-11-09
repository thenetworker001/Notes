uncleared topics: ==hashable and hashing==

- List - Ordered, Mutable, Allow duplication
- Tuple - Ordered, Immutable, Allow duplication
- Set - Unordered, Mutable, Unique elements
- Dictionary - Key-value pairs, Mutable, Unique Keys

### List
Stores multiple values in a single variable
```python
numbers = [10,20,30,40]
```
Can contain any data type, mixed ones and even another lists also
It preserves insertion order

##### Indexing
Each element have an index and is directly accessible. 0 Element refers to first, 1 to second element and so from left to right (from start to end). -1 refers to last element, -2 to second last and so from right to left (end to start)

slicing: `list[start:stop:step]` 

-> List methods: There are several list methods to perform several operations on it

---
### Tuple
Collection that stores multiple values, just like a list, but they are immutable means they can't be modified after creation
```python
numbers = (10, 20, 30)
```
They can also contain any data type and also mixed one, also can contain other tuples

Parentheses isn't mandatory but commas does
```python
a = (10)
print(type(a))
# <class 'int'>

a = (10,)
print(type(a))
# <class 'tuple'>
```

Indexing is same as of lists
It also preserves insertion order

We can't modify existing values but we can create a new tuple for that
```python
numbers = (10, 20, 30)
numbers = numbers + (40, 50)
print(numbers)
# (10, 20, 30, 40, 50)
```
But tuple can have mutable elements and we can modify those elements, which doesn't change tuple:
```python
data = (10, 20, [30, 40])
data[2].append(50)
print(data)
# (10, 20, [30, 40, 50])
```
Tuple have less methods than lists

---
### Set
Stores unique elements, duplicates are automatically removed, implemented using hash tables, therefore membership checking is easier
```python
numbers = {10, 20, 30}
```
But, empty curly braces create a dictionary
```python
a = {}
print(type(a))
# <class 'dict'>
```
It also supports some methods like lists
Set also supports mathematical operations like union, intersection, difference and subset checking etc

Set is mutable, but there is a immutable version called frozenset
it doesn't preserve insertion order

---
### Dictionary
Stores values as key-value pairs
```python
person = {
    "name": "Tony",
    "age": 35,
    "profession": "Engineer"
}
```
It preserve insertion order in modern python
They are also mutable
There are also several methods to perform on dictionaries

Loop through keys:
```python
user = {
    "name": "Tony",
    "age": 35,
    "role": "admin"
}

for key in user:
    print(key)
```
Loop through values:
```python
for value in user.values():
    print(value)
```
Through both:
```python
for key, value in user.items():
    print(key, value)
```

Dictionaries can be nested:
```python
users = {
    "user1": {
        "name": "Tony",
        "age": 35,
        "role": "admin"
    },

    "user2": {
        "name": "Bruce",
        "age": 40,
        "role": "user"
    }
}
```
Access nested values:
```python
print(users["user1"]["name"])
# Tony
print(users["user2"]["role"])
# user
users["user1"]["age"] = 36 #modify values
```

Membership checks with `in` checks the keys not values
```python
user = {
    "name": "Tony",
    "age": 35
}

print("name" in user)
# True

print("Tony" in user)
# False
```
check values:
```python
print("Tony" in user.values())
# True
```

---