___
### Input:
```
print(1)
print(2)

try:
	fgdsakg
except:
	print("The file does not exist!")


try:
	f = open(asdfasddff)
except FileNotFoundError:
	print("The file does not exist!")
except Exception as e:
	print(e)
finally:
	print("this message!")

n = 100 
if n == 0:
	raise Exception("n can't be 0")
if type(n) is not int:
	raise Exception("n must be an int!")

print(1/n)

a = 1
assert(a != 0)
print(1/a)

b = 0
assert(b != 0) 
print(1/b)
```

### Output:
```
─$ python3 Exception.py
1
2
The file does not exist!
name 'asdfasddff' is not defined
this message!
0.01
1.0
Traceback (most recent call last):
  File "/home/kali/Desktop/Python 101/Exception.py", line 32, in <module>
    assert(b != 0)
           ^^^^^^
AssertionError

```

### Input:
```
n = "asad" 
if n == 0:
	raise Exception("n can't be 0")
if type(n) is not int:
	raise Exception("n must be an int!")
```

### Output:
```
Traceback (most recent call last):
  File "/home/kali/Desktop/Python 101/Exception.py", line 5, in <module>
    raise Exception("n must be an int!")
Exception: n must be an int!
```