___
### Input:
```
from pwn import *
import sys

if len(sys.argv) != 2:
	print("Invalid arguments!")
	print(">> {} <sha256sum>".format(sys.argv[0]))
	exit()

wanted_hash = sys.argv[1]
password_file = "rockyou.txt"
attempts = 0

with log.progress("Attempting to back: {}!\n".format(wanted_hash)) as p:
	with open(password_file, "r", encoding='latin-1') as password_list:
		for password in password_list:
			password = password.strip("\n").encode('latin-1')
			password_hash = sha256sumhex(password)
			p.status("[{}] {} == {}".format(attempts, password.decode('latin-1'), password_hash))
			if password_hash == wanted_hash:
				p.success("Password hash found after {} attempts! {} hashes to {}!".format(attempts, password.decode('latin-1'), password_hash))
				exit()
			attempts += 1
		p.failure("Password hash not found!")
		    	
```

### Output:
```
─(kali㉿kali)-[~/Desktop/Python 101]
└─$ python3 Project_2_SHA256_password_cracking.py 11a4a60b518bf24989d481468076e5d5982884626aed9faeb35b8576fcd223e1
[+] Attempting to back: 11a4a60b518bf24989d481468076e5d5982884626aed9faeb35b8576fcd223e1!
    : Password hash found after 16471 attempts! python hashes to 11a4a60b518bf24989d481468076e5d5982884626aed9faeb35b8576fcd223e1!

```


### How to convert the text into sha256

```
(kali㉿kali)-[~]
└─$ echo -ne python | sha256sum
11a4a60b518bf24989d481468076e5d5982884626aed9faeb35b8576fcd223e1  -
```

