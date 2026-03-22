___
- These is a hack the box machine with medium difficulty and these machine was released on 21th Feb, 2026.
- The vpn server used for this machine was Europe 4 tcp.
- I did the machine with the help of the walkthrough blog after I was stuck at the SQL queries.
## Enumeration

### Nmap Scan: 

![](Interpreter.md_Attachments/Screenshot%202026-03-21%20155959.png)

- Port 80 is open so we first go and have a look at that.

![](Interpreter.md_Attachments/Screenshot%202026-03-21%20160109.png)

- After clicking on "Launch Mirth Connect Administrator" one java file gets downloaded on the kali.

![](Interpreter.md_Attachments/Screenshot%202026-03-21%20160822.png)

- After doing a quick search about "Mirth Connect Administrator 4.4.0" we found this CVE-2023-43208.

![](Interpreter.md_Attachments/Screenshot%202026-03-21%20161007.png)

## Exploitation

- We found an github repository which was built for this CVE so we git clone it.

![](Interpreter.md_Attachments/Screenshot%202026-03-21%20224440.png)

![](Interpreter.md_Attachments/Screenshot%202026-03-21%20224506.png)

- Then we check if the connection is being through and as soon as we confirm it with this command :
```
python3 detection.py http://10.129.244.184
python3 CVE-2023-43208.py -u https://10.129.244.184 -c 'touch /tmp/proof'
```

