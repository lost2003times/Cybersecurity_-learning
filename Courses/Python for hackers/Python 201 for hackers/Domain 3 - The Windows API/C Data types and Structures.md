___

### Input:
```
from ctypes import *

b0 = c_bool(0)
b1 = c_bool(1)

print(b0)
print(type(b0))
print(b0.value)

print(b1)
print(type(b1))
print(b1.value)

i0 = c_uint(-1)
print(i0.value)

c0 = c_char_p(b"test")
print(c0.value)

print(c0)
c0 = c_char_p(b"test2")
print(c0)
print(c0.value)

p0 = create_string_buffer(5)
print(p0)
print(p0.raw)
print(p0.value)

p0.value = b"a"
print(p0.raw)
print(p0)

i = c_int(42)
pi = pointer(i)

print(i)
print(pi)
print(pi.contents)

print(p0.value)
print(p0)
print(hex(addressof(p0)))

pt = byref(p0)
print(pt)

print(cast(pt, c_char_p).value)

print(cast(pt, POINTER(c_int)).contents)
print(ord('a'))

class PERSON(Structure):
    _fields_ = [("name",c_char_p),
                ("age", c_int)]

bob = PERSON(b"bob", 30)
print(bob.name)
print(bob.age)

alice = PERSON(b"alice", 23)
print(alice.name)
print(alice.age)

person_array_t = PERSON * 4
print(person_array_t)

person_array = person_array_t()

person_array[0] = PERSON(b"bob",13)
person_array[1] = PERSON(b"alice",35)
person_array[2] = PERSON(b"mallory",40)
person_array[3] = PERSON(b"nancy",28)

for person in person_array:
    print(person)
    print(person.name)
    print(person.age)

```

### Output:
```
J:\Python 201 for Hackers>Python C_types_struc.py
c_bool(False)
<class 'ctypes.c_bool'>
False
c_bool(True)
<class 'ctypes.c_bool'>
True
4294967295
b'test'
c_char_p(2672685039152)
c_char_p(2672685039584)
b'test2'
<ctypes.c_char_Array_5 object at 0x0000026E48745250>
b'\x00\x00\x00\x00\x00'
b''
b'a\x00\x00\x00\x00'
<ctypes.c_char_Array_5 object at 0x0000026E48745250>
c_long(42)
<__main__.LP_c_long object at 0x0000026E48745550>
c_long(42)
b'a'
<ctypes.c_char_Array_5 object at 0x0000026E48745250>
0x26e48745298
<cparam 'P' (0x0000026E48745298)>
b'a'
c_long(97)
97
b'bob'
30
b'alice'
23
<class '__main__.PERSON_Array_4'>
<__main__.PERSON object at 0x0000026E48745850>
b'bob'
13
<__main__.PERSON object at 0x0000026E487458D0>
b'alice'
35
<__main__.PERSON object at 0x0000026E48745850>
b'mallory'
40
<__main__.PERSON object at 0x0000026E487458D0>
b'nancy'
28
```