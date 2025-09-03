___ 
We started off with the visit of the IP we have identified with the nmap scan and we see an default web page which is considered a poor hygiene for a web page owner so we get some of the indications from this kind of a web page, first is that, there are other files or directories behind this page and the second is that we get not much but some information from this page is this :

![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%204%20-%20Scanning%20and%20Enumeration/assests/Pasted%20image%2020250903214807.png)

After that, we have used Nikto but there are a few things about Nikto:

Nikto is good for a quick, old-school scan for common issues but if the web app has a WAFs (Web Application Firewalls) then it will be blocked off immediately as Nikto is not stealthy, its very loud so it will be detected if there's firewall.

As we are doing this scans on Kioptrix its alright as its an old machine.

```
nikto -h //https:192.168.15.8

nikto -h 192.168.15.8
```

-h : hosts 

The complete output is there in the assessment but here is the important thing we can use is this : ==mod_ssl/2.8.4 - mod_ssl 2.8.7 and lower are vulnerable to a remote buffer overflow which may allow a remote shell.==

___ 
After that we used dirbuster as we know there might be some directories and we used this settings : 

![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%204%20-%20Scanning%20and%20Enumeration/assests/Pasted%20image%2020250903220636.png)

We found a lot of directories but there was not much there but still there was one thing which we might end up using : 

![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%204%20-%20Scanning%20and%20Enumeration/assests/Pasted%20image%2020250903221051.png)

___

Now we come for the port 139 which is the SMB port commonly used in work environments and used for file sharing so we might have a shot here.
For that we will be using metasploit :
```
msf console
search smb 
```

Then i looked for auxilary smb version scan it looked something like this :

==397  auxiliary/scanner/smb/smb_versiondetection==
```
use 397 (can use this as well  auxiliary/scanner/smb/smb_versiondetection)
info
show options 
set rhosts 192.168.15.8
run
```

We didnt got much but we got this 

192.168.15.8:139      -   Host could not be identified: ==Unix (Samba 2.2.1a)==
 ___
 We tried if we can get access using this info with smbclient
 ```
 smbclient -L //192.168.15.8
 ```

```
        Sharename       Type      Comment
        ---------       ----      -------
        IPC$            IPC       IPC Service (Samba Server)
        ADMIN$          IPC       IPC Service (Samba Server)

```

