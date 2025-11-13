___
### Input
```
def gen_demo():

    n = 1
    yield n

    n += 1
    yield n

    n += 1
    yield n

test = gen_demo()
print(test)

print(next(test))
print(next(test))
print(next(test))
#print(next(test)) , this will give an iteration error


test2 = gen_demo()
for a in test2:
    print(a)
    
def xor_static_key(a):
    key = 0x5
    for i in a:
        yield chr(ord(i) ^ key)

for i in xor_static_key("test"):
    print(i)


xor_static_key2 = (chr(ord(i) ^ 0x5) for i in "test")

print(xor_static_key2)
print(next(xor_static_key2))
print(next(xor_static_key2))

for i in xor_static_key2:
    print(i)
```

### Output

```
J:\Python 201 for Hackers>python Generators.py
<generator object gen_demo at 0x0000015FD5C27040>
1
2
3
1
2
3
q
`
v
q
<generator object <genexpr> at 0x0000015FD5ED2C00>
q
`
v
q
```

