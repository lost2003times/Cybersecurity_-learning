___
### Input:
```
list1 = ["A", "B", "C", "D", "E", "F"]
print(list1)

list2 = ["A", 1, 2.0, ["A"], [], list(), ("A"), False]
print(list2)
print(type(list2))

print(list1[0])
print(list1[-1])
print(list2[3][-1])

list1[0] = "X"
print(list1)

del list1[0]
print(list1)

list1.insert(0, "A")
print(list1)

del list1[0]
print(list1)

list1 = ["A"] + list1
print(list1)

list1.append("G")
print(list1)

print(max(list1))
print(min(list1))

print(list1.index("C"))
print(list1[list1.index("C")])

list1.reverse()
print(list1)

list1 = list1[::-1]
print(list1)

print(list1.count("A"))
list1.append("A")
print(list1)
print(list1.count("A"))

list1.pop()
print(list1)

list3 = ["H","I","J"]
print(list3)

list1.clear()
print(list1)

list4 = [8, 12, 5, 6, 7, 2]
print(list4)

list4.sort(reverse=True)
print(list4)

list5 = list4
print(list4)
print(list5)

list5[2] = "X"
print(list5)
print(list4)

list6 = list4.copy()
print(list6)
print(list4)

list6[2] = "A"
print(list6)
print(list4)

list7 = ["1", "2", "3"]
print(list7)

list8 = list(map(float, list7))
print(list8)
```

### Output:
```
 python3 Lists.py  
['A', 'B', 'C', 'D', 'E', 'F']
['A', 1, 2.0, ['A'], [], [], 'A', False]
<class 'list'>
A
F
A
['X', 'B', 'C', 'D', 'E', 'F']
['B', 'C', 'D', 'E', 'F']
['A', 'B', 'C', 'D', 'E', 'F']
['B', 'C', 'D', 'E', 'F']
['A', 'B', 'C', 'D', 'E', 'F']
['A', 'B', 'C', 'D', 'E', 'F', 'G']
G
A
2
C
['G', 'F', 'E', 'D', 'C', 'B', 'A']
['A', 'B', 'C', 'D', 'E', 'F', 'G']
1
['A', 'B', 'C', 'D', 'E', 'F', 'G', 'A']
2
['A', 'B', 'C', 'D', 'E', 'F', 'G']
['H', 'I', 'J']
[]
[8, 12, 5, 6, 7, 2]
[12, 8, 7, 6, 5, 2]
[12, 8, 7, 6, 5, 2]
[12, 8, 7, 6, 5, 2]
[12, 8, 'X', 6, 5, 2]
[12, 8, 'X', 6, 5, 2]
[12, 8, 'X', 6, 5, 2]
[12, 8, 'X', 6, 5, 2]
[12, 8, 'A', 6, 5, 2]
[12, 8, 'X', 6, 5, 2]
['1', '2', '3']
[1.0, 2.0, 3.0]
```
