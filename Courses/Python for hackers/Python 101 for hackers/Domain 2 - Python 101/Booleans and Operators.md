___
### Input :

```
print(bool(0) == True)
print(bool(1) == True)

print(bool(0))
print(bool(1))

print("1-------------1")

valid = True
not_valid = False

print(valid)
print(not_valid)

print(valid == True)
print(not_valid == False)
print(valid == False)

print(valid != True)
print(not_valid != True)

print(not valid)
print(not not_valid)

print("2-----------2")

print((10 < 9) == True)
print((10 == 10) == True)
print((2 != 2) == True)
print((2 >= 2) == True)
print((2 <= 2) == True)
print((2 > 1) == True)

print(10 < 9) 
print(10 == 10)
print(2 != 2)
print(2 >= 2) 
print(2 <= 2) 
print(2 > 1) 

print("3---------------3")

print(5 > 2 and 5 < 2)
print(5 > 2 or 5 < 2)

print(2 + 2)
print(2 - 2)
print(2 / 2)
print(2 // 2)   
print(2 * 2)

print(10 / 3)
print(10 // 3)
print(10 % 3)

print(10 ** 10)
print(10 % 10)

print("4---------------4")

x = 10
print(x)
x = x + 1
print(x)
x += 1
print(x)
x -= 1
print(x)
x *= 5 
print(x)
x /= 5
print(x)

print("5---------------5")

x = 13
print(bin(x))
print(bin(x)[2:].rjust(4,"0"))

y = 5
print(bin(y)[2:].rjust(4,"0"))

#logical and (multiply)
print(bin(x & y)[2:].rjust(4,"0"))
print(x & y)

#logical or (addition)
print(bin(x | y)[2:].rjust(4,"0"))
print(x | y)

print("6------------------6")

# Right bit shift
print(bin(x))
print(bin(x >> 1)[2:].rjust(6,"0"))
print(bin(x >> 2)[2:].rjust(6,"0"))
print(bin(x >> 3)[2:].rjust(6,"0"))

# Left bit shift
print(bin(x >> 2)[2:].ljust(6,"0"))

```

### Output :

```
False
True
False
True
1-------------1
True
False
True
True
False
False
True
False
True
2-----------2
False
True
False
True
True
True
False
True
False
True
True
True
3---------------3
False
True
4
0
1.0
1
4
3.3333333333333335
3
1
10000000000
0
4---------------4
10
11
12
11
55
11.0
5---------------5
0b1101
1101
0101
0101
5
1101
13
6------------------6
0b1101
000110
000011
000001
110000

```