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

- As we found the RSA key we can 

