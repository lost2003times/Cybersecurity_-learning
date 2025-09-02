
Methods to identify and downloading legit files.

---
## 2025-08-18
**What I studied:**  
- Ensure you are not the **victim of the MITM attack**.
- Don't download files from the public network and if you are unsure then **download using VPN** and still if you are unsure then **use the official websites only**.
- Windows anti virus is good enough but still if you want to use a good antivirus then **Malwarebytes and Bitdefender**. 
- These are very much trusted and also they are light on resources.
- If you ever download files you can check the file on **Virus total** which will scan the file with **multiple antivirus**.
- If you have a big file which is not possible to upload to the Virus total then you can use the checksum method to make sure you have downloaded the file without any virus.
- Download the encryption algorithm known as **MD5** and  you can generate the checksum of the file and compare the checksum with the one you have downloaded.
- There is another way to do this with the help of **cmd**.

**Command for generating the checksum with cmd:**  
```
dir
cd Downloads
dir
CertUtil -hashfile <filename> MD5
```

