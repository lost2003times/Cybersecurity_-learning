___
- This is a Hack the box machine which is rated as easy and was released on 31st Jan. 
- This is a Linux machine and the VPN server used for this machine was Europe 4 TCP.

## Information Gathering
- Started with Nmap where I found the 22/tcp and 80/tcp ports open. 

![](Facts.md_Attachments/Screenshot%202026-03-23%20174022.png)

![](Facts.md_Attachments/Screenshot%202026-03-23%20174044.png)

- Checked the open ports and found this registration page.

![](Facts.md_Attachments/Screenshot%202026-03-23%20195429.png)


![](Facts.md_Attachments/Screenshot%202026-03-23%20182901.png)

- Then I registered as an user.

![](Facts.md_Attachments/Screenshot%202026-03-23%20183019.png)

![](Facts.md_Attachments/Screenshot%202026-03-23%20183045.png)

![](Facts.md_Attachments/Screenshot%202026-03-23%20183300.png)

## Enumeration 

- Here I found the feature to change passwords. 
- So I try to intercept that request and try to give myself admin role.

![](Facts.md_Attachments/Screenshot%202026-03-23%20183300%201.png)

```
&password[role]=admin
```

- Used burpsuite. 

![](Facts.md_Attachments/Screenshot%202026-03-23%20185911.png)

![](Facts.md_Attachments/Screenshot%202026-03-23%20185206.png)

- Got the admin access and along with that aws access keys : 

![](Facts.md_Attachments/Screenshot%202026-03-23%20190351.png)

