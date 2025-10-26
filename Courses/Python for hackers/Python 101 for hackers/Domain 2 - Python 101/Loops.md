___
### Input:
```
a = 1 
while a < 5:
	a += 1
	print(a)

print("-----")

for i in [0,1,2,3,4]:
	print(i+6)

print("-----")

for i in range(5):
	print(i+6)

print("-----")

for i in range(3):
	for j in range(3):
		print(i,j)

print("-----")

for i in range(5):
	if i == 2:
		break
	print(i)

for i in range(5):
	if i == 2:
		continue
	print(i)

print("-----")

for i in range(5):
	if i == 2:
		pass
	print(i)

for c in "Jayman":
	print(c)

for key, value in {"a":1, "b":2, "c":3}.items():
	print(key,value)

```

### Output:
```
python3 Loops.py
2
3
4
5
-----
6
7
8
9
10
-----
6
7
8
9
10
-----
0 0
0 1
0 2
1 0
1 1
1 2
2 0
2 1
2 2
-----
0
1
0
1
3
4
-----
0
1
2
3
4
J
a
y
m
a
n
a 1
b 2
c 3
```