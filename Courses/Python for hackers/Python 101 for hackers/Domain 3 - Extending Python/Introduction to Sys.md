___
### Input:
```
import sys

print(sys.version)
print(sys.executable)
print(sys.platform)

for i in range(1,5):
	sys.stdout.write(str(i))
	sys.stdout.flush()

for i in range(1,5):
	print(i)

import time

for i in range(0,26):
  time.sleep(0.1)
  sys.stdout.write("{} [{}{}]\r".format(i, "@"*i, "."*(25-i)))
  sys.stdout.flush()
  sys.stdout.write("\n")

print(sys.argv)

print(sys.path)

if len(sys.argv) != 3:
	print("[X] To run {} enter a username and password".format(sys.argv))
sys.exit(5)

username = sys.argv[1]
password = sys.argv[2]

print("{} {}".format(username,password))

sys.exit(0)
```

### Output:
```
┌──(kali㉿kali)-[~/Desktop/Python 101]
└─$ python3 Sys.py test password
3.13.7 (main, Aug 20 2025, 22:17:40) [GCC 14.3.0]
/usr/bin/python3
linux
12341
2
3
4
0 [.........................]
1 [@........................]
2 [@@.......................]
3 [@@@......................]
4 [@@@@.....................]
5 [@@@@@....................]
6 [@@@@@@...................]
7 [@@@@@@@..................]
8 [@@@@@@@@.................]
9 [@@@@@@@@@................]
10 [@@@@@@@@@@...............]
11 [@@@@@@@@@@@..............]
12 [@@@@@@@@@@@@.............]
13 [@@@@@@@@@@@@@............]
14 [@@@@@@@@@@@@@@...........]
15 [@@@@@@@@@@@@@@@..........]
16 [@@@@@@@@@@@@@@@@.........]
17 [@@@@@@@@@@@@@@@@@........]
18 [@@@@@@@@@@@@@@@@@@.......]
19 [@@@@@@@@@@@@@@@@@@@......]
20 [@@@@@@@@@@@@@@@@@@@@.....]
21 [@@@@@@@@@@@@@@@@@@@@@....]
22 [@@@@@@@@@@@@@@@@@@@@@@...]
23 [@@@@@@@@@@@@@@@@@@@@@@@..]
24 [@@@@@@@@@@@@@@@@@@@@@@@@.]
25 [@@@@@@@@@@@@@@@@@@@@@@@@@]
['Sys.py', 'test', 'password']
['/home/kali/Desktop/Python 101', '/usr/lib/python313.zip', '/usr/lib/python3.13', '/usr/lib/python3.13/lib-dynload', '/usr/local/lib/python3.13/dist-packages', '/usr/lib/python3/dist-packages']

┌──(kali㉿kali)-[~/Desktop/Python 101]
└─$ echo $?
0
(0 is the exit code)
```
