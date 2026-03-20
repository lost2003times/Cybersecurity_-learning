___
- These is a Hack the box machine which was released on 12th March, 2026. These machine was based on Linux and the difficulty rating was medium on the box.
- The server used for the VPN was Europe 3 from hack the box.
- The Ip for the first time I used the machine was : 10.129.9.100 

## Enumeration
### The Nmap scan: 
![](Principal.md_Attachments/Screenshot%202026-03-18%20200014.png)
- The open ports which were important was 22/tcp which is open ssh with the ssh-host keys : ECDSA and ED25519; and 8080/tcp which seems to be an web page.
- And there is one more important detail which is : X-Powered by: pac4j -jwt/6.0.3

### The web page: 
![](Principal.md_Attachments/Screenshot%202026-03-18%20200517.png)

- Got this from the page source : 
![](Principal.md_Attachments/Screenshot%202026-03-19%20115939.png)
- And then found the RSA token: 
![](Principal.md_Attachments/Screenshot%202026-03-19%20121256.png)

### Directory Scan:
- Then I started a directory scan with the help of ffuf.
![](Principal.md_Attachments/Screenshot%202026-03-18%20202440.png)

![](Principal.md_Attachments/Screenshot%202026-03-18%20202454.png)

- Here I found 2 names which can be useful later.

### About the CVE-2026-29000

- Then I search about the pac4j jwt.
![](Principal.md_Attachments/Screenshot%202026-03-19%20120445.png)
## Manual Exploitation

- As we found the RSA key we can try to generate one by writing a python script.
![](Principal.md_Attachments/Screenshot%202026-03-19%20124548.png)

![](Principal.md_Attachments/Screenshot%202026-03-19%20131108.png)
### Burp Suite 

![](Principal.md_Attachments/Screenshot%202026-03-19%20133226%201.png)

- We were Unauthorized so we need to make sure we are generating the token for the role which is authorized.

![](Principal.md_Attachments/Screenshot%202026-03-19%20135203.png)

![](Principal.md_Attachments/Screenshot%202026-03-19%20135220.png)

![](Principal.md_Attachments/Screenshot%202026-03-19%20135120.png)

- Now we know Admin role is required and we have that information from the source page of the website.

![](Principal.md_Attachments/Screenshot%202026-03-19%20135335.png)

### Updated Python script

![](Principal.md_Attachments/Screenshot%202026-03-20%20133650.png)

![](Principal.md_Attachments/Screenshot%202026-03-19%20140517.png)

![](Principal.md_Attachments/Screenshot%202026-03-19%20140914.png)

![](Principal.md_Attachments/Screenshot%202026-03-19%20140928.png)

- With these we received some important information, we found the username for ssh along with the password which we will used to get a shell.

## Getting a shell

![](Principal.md_Attachments/Screenshot%202026-03-19%20150655.png)

- As we get into shell I know we have the User flag so I started working on getting the root flag first. 

![](Principal.md_Attachments/Screenshot%202026-03-19%20150712.png)

- There we found the ssh file and then we generate a key to be used to get a root shell.

![](Principal.md_Attachments/Screenshot%202026-03-19%20150727.png)

![](Principal.md_Attachments/Screenshot%202026-03-19%20150750.png)

- And there we found the root shell and we got the root.txt 
-  Along with that I retrieved the user.txt as well. 
![](Principal.md_Attachments/Screenshot%202026-03-19%20150813.png)
**Now we have both the user flag and the root flag.**
