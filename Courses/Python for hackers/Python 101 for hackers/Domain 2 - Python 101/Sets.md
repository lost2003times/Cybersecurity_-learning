___
### Input:
```
set1 = {"a", "b", "c"}
print(set1)
print(type(set1))

set2 = {"a", "a", "a"}
print(set2)
print(len(set2))

set3 = {"a",0, True}
print(set3)

set4 = set(("b", 1, False))
print(set4)

set1.add("d")
print(set1)

set3.update(set4)
print(set3)

list1 = ["a", "b", "c"]
set5 = {4,5,6}
print(list1)
print(set5)

set5.update(list1)
print(set5)

set6 = {1,2,3}
set7 = set5.union(set6)
print(set7)
set7 = set5.intersection(set6)
print(set7)

set5.remove(4)
print(set5)

set5.discard(4)
print(set5) 
#We can use discard multiple times to remove the same value and it wont give us an error but if we use remove more than once to remove the same value from the set then it will give us an error.

print(set1)
set1.pop()
print(set1)
# It will pop a random set value everytime as there are no index for the elements.
```

### Output:
```
python3 Sets.py
{'c', 'b', 'a'}
<class 'set'>
{'a'}
1
{0, True, 'a'}
{False, 1, 'b'}
{'d', 'c', 'b', 'a'}
{0, True, 'b', 'a'}
['a', 'b', 'c']
{4, 5, 6}
{'c', 4, 5, 6, 'a', 'b'}
{1, 2, 'c', 4, 5, 6, 'a', 3, 'b'}
set()
{'c', 5, 6, 'a', 'b'}
{'c', 5, 6, 'a', 'b'}
{'d', 'c', 'b', 'a'}
{'c', 'b', 'a'}
```
