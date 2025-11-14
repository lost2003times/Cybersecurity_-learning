___

![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%208%20-%20Attacking%20Active%20Directory%20-%20Post%20Compromise%20Attacks/assests/-20251114-16.png)


```
GetUserSPNs.py MARVEL.local/fcastle:Password1 -dc-ip 192.168.15.18 -request
```

![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%208%20-%20Attacking%20Active%20Directory%20-%20Post%20Compromise%20Attacks/assests/-20251114-15.png)

## Mitigations

- Service Account (SQL) does not require to be running as the Domain Admin
- Do not store the service account password in the description of your Active Directory account
- Strong Passwords
- Least privileges

