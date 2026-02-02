___
- Not all Windows APIs are documented on MSDN.
- The documented APIs we used so far operate in user mode.
- When calling a user mode API, we eventually end up in kernel mode.
- Windows APIs are an abstraction layer over the native API.
- These native API calls we are interested in, are defined in NTDLL.

### Input:
```
from ctypes import*
from ctypes import wintypes

kernel32 = windll.kernel32
SIZE_T = c_size_t

VirtualAlloc = kernel32.VirtualAlloc
VirtualAlloc.argtypes = (wintypes.LPVOID, SIZE_T, wintypes.DWORD, wintypes.DWORD)
VirtualAlloc.restype = wintypes.LPVOID

MEM_COMMIT = 0x00001000
MEM_RESERVE = 0x00002000
PAGE_EXECUTE_READWRITE = 0x40

prt = VirtualAlloc(None, 1024 * 4, MEM_COMMIT | MEM_RESERVE, PAGE_EXECUTE_READWRITE)

error = GetLastError()

if error:
    print(error)
    print(WinError(error))

print("VirtualAlloc: ", hex(prt))

nt = windll.ntdll
NTSTATUS = wintypes.DWORD

NtAllocateVirtualMemory = nt.NtAllocateVirtualMemory
NtAllocateVirtualMemory.argtypes = (wintypes.HANDLE, POINTER(wintypes.LPCVOID), wintypes.ULONG, POINTER(wintypes.ULONG), wintypes.ULONG, wintypes.ULONG)
NtAllocateVirtualMemory.restype = NTSTATUS

handle = 0xffffffffffffffff
base_address = wintypes.LPCVOID(0x0)
zero_bits = wintypes.ULONG(0)
size = wintypes.ULONG(1024 *12)
prt2 = NtAllocateVirtualMemory(handle, byref(base_address),zero_bits, byref(size), MEM_COMMIT | MEM_RESERVE, PAGE_EXECUTE_READWRITE)

if prt2 != 0:
    print("error!")
    print(prt2)

print("NtAllocateVirtualMemory: ", hex(base_address.value))
input()

```

### Output:

```
J:\Python 201 for Hackers>python Undocumented_API.py
VirtualAlloc:  0x1a635dc0000
NtAllocateVirtualMemory:  0x1a635dd0000
```

