___
### Input1:
```
f = open('Assessment.txt')
print(f)

f = open('Assessment.txt','rt')
print(f)

print(f.read())
f.seek(0)

print(f.readlines())
print(f.readlines()) # This wont print out the file contents coz the file has already been read .

f.seek(0) # This brings the position of file back to zero.

print(f.readlines())

f.seek(0)

for line in f:
	print(line.strip())

f.close()

print("Create and write in the file")
f = open("test.txt","w")
f.write("test line one!")

print("append in file")

f.write("test line two!")
f.close()

print(f.name)
print(f.closed)
print(f.mode)

with open('rockyou.txt', encoding='latin-1') as f:
	for line in f:
		print(line.strip())
```

### Output:
```
print(f.read())
Normal output

print(f.readlines())
'80/443 - 192.168.15.8 \n', 'Default webpage - Apache PHP\n', 'Information Disclosure - 404 page\n', '\n', 'Information Disclosure - Server headers dislcose verseion information\n', '\n', '\n', '80/tcp    open  http        Apache httpd 1.3.20 ((Unix)  (Red-Hat/Linux) mod_ssl/2.8.4 OpenSSL/0.9.6b)\n', '\n', ' mod_ssl/2.8.4 - mod_ssl 2.8.7 and lower are vulnerable to a remote buffer overflow which may allow a remote shell.\n', ' \n', ' Webalizer Version 2.01 - http://192.168.15.8/usage/usage_202509.html\n', ' \n', ' smb version - Samba 2.2.1a\n', ' \n', ' \n', ' \n', ' \n', ' \n', ' \n', ' -oKexAlgorithms=+\n'


```