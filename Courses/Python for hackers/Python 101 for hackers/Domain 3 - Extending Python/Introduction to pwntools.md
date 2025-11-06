___
### Input:
```
from pwn import *

print(cyclic(50))
print(cyclic_find("laaa"))

print(shellcraft.sh())
print(hexdump(asm(shellcraft.sh())))

print(p32(0x13371337))
print(hex(u32(p32(0x13371337))))

l = ELF('/bin/bash')

print(hex(l.address))
print(hex(l.entry))

print(hex(l.got['write']))
print(hex(l.plt['write']))

for address in l.search(b'/bin/sh\x00'):
	print(hex(address))

print(hex(next(l.search(asm('jmp esp')))))

r = ROP(l)
print(r.rbx)

print(xor(xor("A","B"),"A"))
print(b64e(b"Jayman"))
print(b64d(b"SmF5bWFu"))
print(md5sumhex(b"Hello"))
print(sha1sumhex(b"Hello"))

print(bits(b'J'))
print(unbits([0, 1, 0, 0, 1, 0, 1, 0]))

```

### Output:
```
python3 pwntools.py
b'aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaama'
44
    /* execve(path='/bin///sh', argv=['sh'], envp=0) */
    /* push b'/bin///sh\x00' */
    push 0x68
    push 0x732f2f2f
    push 0x6e69622f
    mov ebx, esp
    /* push argument array ['sh\x00'] */
    /* push 'sh\x00\x00' */
    push 0x1010101
    xor dword ptr [esp], 0x1016972
    xor ecx, ecx
    push ecx /* null terminate */
    push 4
    pop ecx
    add ecx, esp
    push ecx /* 'sh\x00' */
    mov ecx, esp
    xor edx, edx
    /* call execve() */
    push SYS_execve /* 0xb */
    pop eax
    int 0x80

00000000  6a 68 68 2f  2f 2f 73 68  2f 62 69 6e  89 e3 68 01  │jhh/│//sh│/bin│··h·│
00000010  01 01 01 81  34 24 72 69  01 01 31 c9  51 6a 04 59  │····│4$ri│··1·│Qj·Y│
00000020  01 e1 51 89  e1 31 d2 6a  0b 58 cd 80               │··Q·│·1·j│·X··│
0000002c
b'7\x137\x13'
0x13371337
[*] '/bin/bash'
    Arch:       amd64-64-little
    RELRO:      Full RELRO
    Stack:      Canary found
    NX:         NX enabled
    PIE:        PIE enabled
    FORTIFY:    Enabled
0x0
0x33810
0x147918
0x31300
0x33cf2
0x33d91
0xb5d8d
[*] Loaded 127 cached gadgets for '/bin/bash'
Gadget(0x33b78, ['pop rbx', 'ret'], ['rbx'], 0x8)
/usr/lib/python3/dist-packages/pwnlib/util/fiddling.py:340: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  strs = [packing.flat(s, word_size = 8, sign = False, endianness = 'little') for s in args]
b'B'
SmF5bWFu
b'Jayman'
8b1a9953c4611296a827abf8c47804d7
f7ff9e8b7bb2e09b70935a5d785e0cc5d9d0abf0
[0, 1, 0, 0, 1, 0, 1, 0]
b'J'
```