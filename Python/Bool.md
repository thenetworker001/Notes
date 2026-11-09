Empty or zero-like values are generally `False`.  like: 0, 0.0, 0j, " ", [ ], { }, ( ), None
If a variable contains any of this value, when evaluated it returns False

Non-empty or non-zero values are generally `True`.

While operating inside a function, if comparison operations or bool operations are done and need to be returned bool type, then instead of using an explicit variable to store and return bool result use the expression/condition itself to return value
```python
def myFunc(data):
	if data in list:
		return True
	else:
		return False
```
Instead of this, use:
```python
def myFunc(data):
	return data in list
```