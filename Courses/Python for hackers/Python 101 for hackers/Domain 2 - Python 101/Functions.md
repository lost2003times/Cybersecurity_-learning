___
### Input:
```
def function1():
	print("Hello from function1!")
function1()
function1()

def function2():
	return "hello from function2"

return_from_function2 = function2()
print(return_from_function2)

def function3(s):
	print("\t{}".format(s))

function3("Parameter1")
function3("Parameter2")

def function4(s1,s2):
	print("{} {}".format(s1,s2))

function4("any","thing")
function4(s1="thing",s2 = "thing")
function4(s2="any",s1="thing")

def function5(s1 = "default"):
	print("{}".format(s1))

function5()
function5("anythingssss")

def function6(s1, *more):
	print("{} {}".format(s1, " ".join([s for s in more])))

function6("function12434")
function6("function6","abc")
function6("hey","hello","bye","ja ne")

def function7(**ks):
	for a in ks:
		print(a,ks[a])

function7(a="1",b="2",c="3",d="4")

def function8(s,f,i,l):
	print(type(s))
	print(type(f))
	print(type(i))
	print(type(l))

function8("string",True,1.0,1000)

v = 100
def function9():
	global v
	v += 1
	print(v)

function9()
print(v)

def function10():
	print("Hello from function10")

def function11():
    function10()
    print("hello from function11")

function11()

def function12(x):
	print(x)
	if x > 0:
		function12(x-1)

function12(7)

print("--------")

def function13(x):
	while x >= 0:
		print(x)
		x -= 1

function13(5)
```

### Output:
```
 python3 Function.py
Hello from function1!
Hello from function1!
hello from function2
        Parameter1
        Parameter2
any thing
thing thing
thing any
default
anythingssss
function12434 
function6 abc
hey hello bye ja ne
a 1
b 2
c 3
d 4
<class 'str'>
<class 'bool'>
<class 'float'>
<class 'int'>
101
101
Hello from function10
hello from function11
7
6
5
4
3
2
1
0
--------
5
4
3
2
1
0

```