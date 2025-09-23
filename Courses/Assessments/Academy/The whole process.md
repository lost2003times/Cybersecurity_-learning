___

- We scan the IP with Nmap and we find out that there is a apache server running and the anonymous ftp server login is available.
- We go to the apache server on the IP but there is nothing much so we decide to search for the directories in the server and for that we use FFuF where we find out about the academy login page. (We can also use dirbuster or gobuster but they will take more time)
- Until the scan is going on we look into the Ftp server and we find out one note.txt file so we transfer it to our machine.
- Inside that txt file we find out login credentials but the password is hashed so we use Search that hash and we find out the password.
- We use this credentials to login into the academy login page.
- There we found the option to upload a photo so we decide to use reverse shell php from pentest monkey and it works for us and we get into.

![](file:///C:/Users/jayma/Pictures/Screenshots/Screenshot%202025-09-20%20213519.png)

- Through that we transfer the linpeas.sh into the victim's system and then use it to search the shell and we find out another credentials as Grimmie as there is suspicious backup file in that.
- We use Shh to login into the grimmie.
![](file:///C:/Users/jayma/Pictures/Screenshots/Screenshot%202025-09-20%20213244.png)

- We understood that this file runs itself in sometime so we decide to get confirmation about it using the tool named as pspy64.
- We download it onto our machine as transfer it my broadcasting our server using python.

![](file:///C:/Users/jayma/Pictures/Screenshots/Screenshot%202025-09-20%20213310.png)

![](file:///C:/Users/jayma/Pictures/Screenshots/Screenshot%202025-09-20%20213446.png)

- We confirmed that this file runs in some interval of times so now we are gonna use reverse shell of one liner which will give us the root access when it will run.

![](file:///C:/Users/jayma/Pictures/Screenshots/Screenshot%202025-09-20%20214024.png)

![](file:///C:/Users/jayma/Pictures/Screenshots/Screenshot%202025-09-20%20213424.png)

- Now we added that code into the backup.sh and now we will wait for the file to run.

![](file:///C:/Users/jayma/Pictures/Screenshots/Screenshot%202025-09-20%20213208.png)

- There we go we get the root access and also we captured the flag.