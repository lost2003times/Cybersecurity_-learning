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