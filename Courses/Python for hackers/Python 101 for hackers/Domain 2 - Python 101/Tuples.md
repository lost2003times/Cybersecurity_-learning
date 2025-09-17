___
### Input:
```
tuple_items = ("item1", "item2", "item3")
print(tuple_items)
print(type(tuple_items))

tuple_numbers = (1,2,3)
print(tuple_numbers)
print(type(tuple_numbers))

tuple_repeat = ('Combine4' ,) * 4
print(tuple_repeat)
print(type(tuple_repeat))

mixed_tuple = ("A", 1, ("A" , 1))
print(mixed_tuple)
print(type(mixed_tuple))

tuple_combined = tuple_items + tuple_numbers
print(tuple_combined)
print(type(tuple_combined))

item1, item2, item3 = tuple_items
print(item1)
print(item2)
print(item3)

print("item2" in tuple_items)
print("item3" in tuple_items)
print("item4" in tuple_items)

print(tuple_items.index("item2"))

tuple_items = ("item1", "item2", "item3")
print(tuple_items[0])
print(tuple_items[1])
print(tuple_items[2])

print(len(tuple_items))

print(tuple_items[-1])
print(tuple_items[-2])

print(tuple_items[0:2])
print(tuple_items[:2])
print(tuple_items[-3:-1])

string1 = "I m a crazzzy dude."
print(string1[0:4])
print(string1[-1])
```

### Output:

```
python3 Tuples.py 
('item1', 'item2', 'item3')
<class 'tuple'>
(1, 2, 3)
<class 'tuple'>
('Combine4', 'Combine4', 'Combine4', 'Combine4')
<class 'tuple'>
('A', 1, ('A', 1))
<class 'tuple'>
('item1', 'item2', 'item3', 1, 2, 3)
<class 'tuple'>
item1
item2
item3
True
True
False
1
item1
item2
item3
3
item3
item2
('item1', 'item2')
('item1', 'item2')
('item1', 'item2')
I m 
.

```