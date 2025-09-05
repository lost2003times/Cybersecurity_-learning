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

