
---
	Once you have set up your VPN, start up the machine.

### Task 1: Deploy the Machine

1.  Deploy the machine : Start the machine.

### Task 2: Reconnaissance

1. Scan the machine, how many ports are open? 
	2
	Open the Zenmap and do an Intense Scan with the given IP.
2.  What version of Apache is running?
	2.4.29
	 Just check its version from the output of the zenmap scan.
3.  What service is running on port 22?
	 ssh
	 Check the zenmap output of scan.
4.  Find directories on the web server using the GoBuster tool.
	- Use the code for using GoBuster : 
	- gobuster dir -u <ip> -w /usr/share/dirbuster/wordlists/directory-list-lowercase-2.3-medium.txt
5. 
