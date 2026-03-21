___
- These is a hack the box machine which was released on 5th June 2021, it was a staff picked machine which has an easy difficulty. 
- The server used for this machine was Europe 4 tcp (udp server does not work properly for these machine.)
- I did the guided path of the machine.
## Enumeration 

### Nmap Scan: 
```
┌──(kali㉿kali)-[~]
└─$ nmap -A -T4 10.129.11.145    
Starting Nmap 7.98 ( https://nmap.org ) at 2026-03-20 15:01 -0400
Nmap scan report for 10.129.11.145
Host is up (0.022s latency).
Not shown: 997 closed tcp ports (reset)
PORT   STATE SERVICE VERSION
21/tcp open  ftp     vsftpd 3.0.3
22/tcp open  ssh     OpenSSH 8.2p1 Ubuntu 4ubuntu0.2 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   3072 fa:80:a9:b2:ca:3b:88:69:a4:28:9e:39:0d:27:d5:75 (RSA)
|   256 96:d8:f8:e3:e8:f7:71:36:c5:49:d5:9d:b6:a4:c9:0c (ECDSA)
|_  256 3f:d0:ff:91:eb:3b:f6:e1:9f:2e:8d:de:b3:de:b2:18 (ED25519)
80/tcp open  http    Gunicorn
|_http-server-header: gunicorn
|_http-title: Security Dashboard
Device type: general purpose|router
Running: Linux 5.X, MikroTik RouterOS 7.X
OS CPE: cpe:/o:linux:linux_kernel:5 cpe:/o:mikrotik:routeros:7 cpe:/o:linux:linux_kernel:5.6.3
OS details: Linux 5.0 - 5.14, MikroTik RouterOS 7.2 - 7.5 (Linux 5.6.3)
Network Distance: 2 hops
Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE (using port 53/tcp)
HOP RTT      ADDRESS
1   21.70 ms 10.10.14.1
2   21.79 ms 10.129.11.145

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 13.84 seconds
```


![](Cap.md_Attachments/Screenshot%202026-03-20%20210631.png)


![](Cap.md_Attachments/Screenshot%202026-03-20%20210450.png)

![](Cap.md_Attachments/Screenshot%202026-03-20%20210644.png)

![](Cap.md_Attachments/Screenshot%202026-03-20%20210505.png)

![](Cap.md_Attachments/Screenshot%202026-03-20%20210758.png)

## Exploitation

![](Cap.md_Attachments/Screenshot%202026-03-20%20210725.png)

![](Cap.md_Attachments/Screenshot%202026-03-20%20211523.png) 

- We got the access of the nathan shell by getting the password from the wireshark and then we found the user.txt, **we got our user flag.**

![](Cap.md_Attachments/Screenshot%202026-03-20%20211843.png)

- Now to get the root flag we use linPeas on the nathan shell.
- To do that we start the server on our machine and then use wget on nathan shell to transfer the linpeas file.

![](Cap.md_Attachments/Screenshot%202026-03-20%20210922.png)

![](Cap.md_Attachments/Screenshot%202026-03-20%20210825.png)

![](Cap.md_Attachments/Screenshot%202026-03-20%20211543.png)

- Here we escalated the linpeas privilege so we can run it and find the information about the path to the binary which can be abused to obtain root privileges.

![](Cap.md_Attachments/Screenshot%202026-03-20%20211609.png)![](Cap.md_Attachments/Screenshot%202026-03-20%20211711.png)

- We found the path : 
```
/usr/bin/python3.8
```

![](Cap.md_Attachments/Screenshot%202026-03-20%20211735.png)

**We got the root flag.**

