___
### Input:

```
from ctypes import *
from ctypes.wintypes import HWND, LPCSTR, UINT, INT, LPSTR, LPDWORD, DWORD, HANDLE, BOOL

MessageBoxA = windll.user32.MessageBoxA
MessageBoxA.argtypes = (HWND, LPCSTR, LPCSTR, UINT)
MessageBoxA.restype = INT

print(MessageBoxA)

lpTest = LPCSTR(b"World")
lpcaption = LPCSTR(b"Hello")
MB_OK = 0x00000000
MB_OKCANCEL = 0x00000001

MessageBoxA(None, lpTest, lpcaption, MB_OKCANCEL)
```

### Output:

![](../../../../assets%20/-20260131.png)

### Input:

```
from ctypes import *
from ctypes.wintypes import HWND, LPCSTR, UINT, INT, LPSTR, LPDWORD, DWORD, HANDLE, BOOL

MessageBoxA = windll.user32.MessageBoxA
MessageBoxA.argtypes = (HWND, LPCSTR, LPCSTR, UINT)
MessageBoxA.restype = INT

print(MessageBoxA)

lpTest = LPCSTR(b"World")
lpcaption = LPCSTR(b"Hello")
MB_OK = 0x00000000
MB_OKCANCEL = 0x00000001

#MessageBoxA(None, lpTest, lpcaption, MB_OKCANCEL)

GetUserNameA = windll.advapi32.GetUserNameA
GetUserNameA.argtypes = (LPSTR, LPDWORD)
GetUserNameA.restype = INT

buffer_size = DWORD(2)
buffer = create_string_buffer(buffer_size.value)

GetUserNameA(buffer, byref(buffer_size))
print(buffer.value)

error = GetLastError()

if error:
    print(error)
    print(WinError(error))

class RECT(Structure):
    _fields_ = [("left", c_long),
                ("top", c_long),
                ("right", c_long),
                ("bottom", c_long)]
    
rect = RECT()

print(rect.left)
print(rect.top)
print(rect.right)
print(rect.bottom)

rect.left = 1

print(rect.left)

GetWindowsRect = windll.user32.GetWindowRect
GetWindowsRect.argtypes = (HANDLE, POINTER(RECT))
GetWindowsRect.restype = BOOL

hwnd = windll.user32.GetForegroundWindow()
GetWindowsRect(hwnd, byref(rect))

print(rect.left)
print(rect.top)
print(rect.right)
print(rect.bottom)

```

### Output:

```
J:\Python 201 for Hackers>python3 Interfacing_with_windows_API.py
<_FuncPtr object at 0x000001FACDBA9A50>
b''
122
[WinError 122] The data area passed to a system call is too small.
0
0
0
0
1
-7
-7
1543
871
```

### Input:

```
from ctypes import *
from ctypes.wintypes import HWND, LPCSTR, UINT, INT, LPSTR, LPDWORD, DWORD, HANDLE, BOOL

MessageBoxA = windll.user32.MessageBoxA
MessageBoxA.argtypes = (HWND, LPCSTR, LPCSTR, UINT)
MessageBoxA.restype = INT

print(MessageBoxA)

lpTest = LPCSTR(b"World")
lpcaption = LPCSTR(b"Hello")
MB_OK = 0x00000000
MB_OKCANCEL = 0x00000001

MessageBoxA(None, lpTest, lpcaption, MB_OKCANCEL)

GetUserNameA = windll.advapi32.GetUserNameA
GetUserNameA.argtypes = (LPSTR, LPDWORD)
GetUserNameA.restype = INT

buffer_size = DWORD(8) #Change '8' to '2' and there will be an error message 
buffer = create_string_buffer(buffer_size.value)

GetUserNameA(buffer, byref(buffer_size))
print(buffer.value)

error = GetLastError()

if error:
    print(error)
    print(WinError(error))

```

### Output:

```
J:\Python 201 for Hackers>python3 Interfacing_with_windows_API.py
<_FuncPtr object at 0x0000016CADB35A50>
b'jayma'
```

