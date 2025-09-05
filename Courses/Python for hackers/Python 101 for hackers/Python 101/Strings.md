___
### Input 1:
```
string1 = 'Hey, I am Jayman'
print(string1)

string2 = "Hey, I am also Jayman"
print(string2)

string3 = """I am a very 
long
long 
long 
string! """
print(string3)

string4 = 'I"m Jayman'
string5 = "\nI'm Jayman"
print(string4,string5)

string6 = "I\"m a string\nI\"m on a newline!"
print(string6)

string7 = "aaaaaaaa"
print(string7)
string7 = "a" * 10
print(string7)

print(len(string7))

print("Jayman" in string4)
print(string4.startswith("I"))
print(string4.startswith("A"))

print(string4.index("Jayman"))
print(string4.upper())
print(string4.lower())
```

### Output 1: 

```
python3 strings.py
Hey, I am Jayman
Hey, I am also Jayman
I am a very 
long
long 
long 
string! 
I"m Jayman 
I'm Jayman
I"m a string
I"m on a newline!
aaaaaaaa
aaaaaaaaaa
10
True
True
False
4
I"M JAYMAN
i"m jayman
```

### Input 2:

```
messy_string = "     Messy,String!"
print(messy_string)
print(messy_string.strip())

print(messy_string.replace("!","<>").strip())
print(messy_string.replace("string","example"))

print(messy_string.split(","))
print(messy_string.split())

string4 = "I am a string"
print(string4)
print(string4.encode())
print(string4.encode("utf-8"))

print(string4.rjust(25))
print(string4.rjust(25,"X"))

print(string4.ljust(25))
print(string4.ljust(25,"J"))

print("I am "+ "a string")
print("string 4 is " + str(len(string4)) + "characters long ! ")
print(1+1)
print("1" + "1")
print(type("1" + "1"))
```

### Output 2:

```
     Messy,String!
Messy,String!
Messy,String<>
     Messy,String!
['     Messy', 'String!']
['Messy,String!']
I am a string
b'I am a string'
b'I am a string'
            I am a string
XXXXXXXXXXXXI am a string
I am a string            
I am a stringJJJJJJJJJJJJ
I am a string
string 4 is 13characters long ! 
2
11
<class 'str'>
```

### Input 3:

```
print("string4 is {} characters long!".format(len(string4)))

print("{} {} {}".format(len(string4),5.0, 0x12))
print("{0} {2} {1}".format(len(string4),5.0, 0x12))
print("{length}".format(length=len(string4)))

length = len(string4)
print(f"string4 is {length} characters long")

print("string4 is {length:.2f}characters long".format(length=len(string4)))
print("string4 is {length:.3f}characters long".format(length=len(string4)))
print("string4 is {length:.4f}characters long".format(length=len(string4)))

print("string4 is {length:x}characters long".format(length=len(string4)))
print("string4 is {length:b}characters long".format(length=len(string4)))
print("string4 is {length:o}characters long".format(length=len(string4)))

print("string4 is %d characters long!" % len(string4))
print("string4 is %f characters long!" % len(string4))
print("string4 is %x characters long!" % len(string4))
```

### Output 3:

```
string4 is 13 characters long!
13 5.0 18
13 18 5.0
13
string4 is 13 characters long
string4 is 13.00characters long
string4 is 13.000characters long
string4 is 13.0000characters long
string4 is dcharacters long
string4 is 1101characters long
string4 is 15characters long
string4 is 13 characters long!
string4 is 13.000000 characters long!
string4 is d characters long!
```
