If `return` is used in `if` ladder, then don't use `elif` or `else`, use alternate `if` and write default logic below all `if`
instead of:
```python
if a>b:
	return a
elif a<b:
	return b
else:
	return a,b
```
write:
```python
if a>b:
	return a
if a<b:
	return b
return a,b
```

