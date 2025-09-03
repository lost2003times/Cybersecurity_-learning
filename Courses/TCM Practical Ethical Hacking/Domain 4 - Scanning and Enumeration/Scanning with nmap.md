___
### Installing Kioptrix :

It is a machine on which we are gonna learn about various tools and methodology.
Installing it was the same way as all the other machines.
We downloaded the ova from the drive folder of Tcm sec and then imported the machine to the virtual box.
Its login credentials are told because the machine is too old and we can just identify the IP of the machine.
For future use, the credentials are: username - john , password - TwoCows2

### Scanning with Nmap :

I would like to explain the command which we are gonna use the most which is :
```
nmap -T4 -p- -A <IP>
```
nmap : its our tool,
T4 : its the speed to check the ports there are 5 levels of speed from 1 to 5 but sir recommends and also used the T4 in the regular use,
-p- : it means that scan all the ports, all 65000, by default it only scans a few ports like 1000 or something which does include all the ports which are used frequently but its good to scan it all,
-A : It means that scan everything,
<IP> : This is where we are supposed to type the IP which we want to scan, for example : 192.168.4.0/24
