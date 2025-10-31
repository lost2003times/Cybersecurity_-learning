___
### Input:

```
test = input()
print("This is the Input.")
print(test)

test = input("enter the Ip:")
print(test)

while True:  # Stays in the infinite loop, unless there is a specific input or condition is fulfilled.
	test = input("Enter the IP: ")
	print(">>>> {}".format(test))
	if test == "exit":
		break
	else:
		print("Exploiting...")
```

### Output:

```
$ python3 Input.py 
HEllO World!!
This is the Input.
HEllO World!!
enter the Ip:192.168.15.15
192.168.15.15
Enter the IP: 127.0.0.0
>>>> 127.0.0.0
Exploiting...
Enter the IP: 192.158.15.4
>>>> 192.158.15.4
Exploiting...
Enter the IP: exit
>>>> exit
```