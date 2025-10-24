___
### Input:

```
dict1 = {"a":1, "b":2, "c":3}
print(dict1)
print(type(dict1))
print(len(dict1))

print(dict1["a"])
print(dict1.get("a"))

print(dict1.keys())
print(dict1.values())
print(dict1.items())

dict1["a"] = 1
print(dict1)

dict1["d"] = 5
print(dict1)

dict1["a"] = 0
print(dict1)

dict1.update({"a": 1})
print(dict1)

dict1.pop("d")
print(dict1)

del dict1['c']
print(dict1)

dict1['c'] = {"a":1, "b":2}
print(dict1)

dict2 = {}
print(dict2)

dict3 = dict()
print(dict3)
```

### Output:
```
python3 Dictonaries.py
{'a': 1, 'b': 2, 'c': 3}
<class 'dict'>
3
1
1
dict_keys(['a', 'b', 'c'])
dict_values([1, 2, 3])
dict_items([('a', 1), ('b', 2), ('c', 3)])
{'a': 1, 'b': 2, 'c': 3}
{'a': 1, 'b': 2, 'c': 3, 'd': 5}
{'a': 0, 'b': 2, 'c': 3, 'd': 5}
{'a': 1, 'b': 2, 'c': 3, 'd': 5}
{'a': 1, 'b': 2, 'c': 3}
{'a': 1, 'b': 2}
{'a': 1, 'b': 2, 'c': {'a': 1, 'b': 2}}
{}
{}
```
