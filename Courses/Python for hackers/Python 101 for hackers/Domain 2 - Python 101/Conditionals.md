___
### Input:
```
if True:
	print("True")

if False:
	print("False") # wont get printed

if not False:
	print("not False")

if 1 < 1:
	print("1 < 1") # Wont get printed
elif 1 <= 1:
	print("1 <= 1")
else:
	print("else 1") # wont get printed coz the other condition was fulfilled

if 1 < 1:
	print("1 < 1") # wont get printed
elif 2 <= 2:
	print("2 <= 2")	
else:
	print("reached else") # wont get printed

if 1 > 0 and 0 < 1:
	print("1 > 0 and 0 < 1")

if 1 < 0 and 0 < 1:
	print("1 > 0 and 0 < 1")

if 1 < 0 or 0 < 1:
	print("1 < 0 or 0 < 1")

if (1 < 0 or 0 > 1) or 1 == 1:
	print("(1 < 0 or 0 > 1) or 1 == 1")

if (1 < 0 or 0 < 1) and 1 == 1:
	print("(1 < 0 or 0 < 1) and 1 == 1")

if 0 < 1: print("0 < 1")
print("1 >= 1") if 1 >= 1 else print("1 < 1")

if 1 >= 1:
	print("1 >= 1")
else:
	print("1 < 1")

if 0 < 0:
	print("1")
elif 0 > 1:
	print("2")
else:
	print("3")

print("1") if 0 < 0 else print("2") if 0 > 1 else print("3")	
```

### Output:
```
 python3 Conditionals.py
True
not False
1 <= 1
2 <= 2
1 > 0 and 0 < 1
1 < 0 or 0 < 1
(1 < 0 or 0 > 1) or 1 == 1
(1 < 0 or 0 < 1) and 1 == 1
0 < 1
1 >= 1
1 >= 1
3
3
```
