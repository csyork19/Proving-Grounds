# Crane
Proving Grounds Practice
Difficulty - Easy

## Enumeration
```
PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
| ssh-hostkey: 
|   2048 3780014a438630c979e7fb7f3ba41edd (RSA)
|   256 b618a1e198fb6cc687554510c6d445b9 (ECDSA)
|_  256 ab8f2de8a204e7b765d3fe5e931e0367 (ED25519)
80/tcp   open  http    Apache httpd 2.4.38 ((Debian))
| http-cookie-flags: 
|   /: 
|     PHPSESSID: 
|_      httponly flag not set
| http-title: SuiteCRM
|_Requested resource was index.php?action=Login&module=Users
| http-robots.txt: 1 disallowed entry 
|_/
|_http-server-header: Apache/2.4.38 (Debian)
3306/tcp open  mysql   MySQL (unauthorized)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
```

### Port 22 SSH
SSH Version - OpenSSH 7.9p1
This does not appear to be vulnerable.


### Port 80 HTTP
HTTP Version - Apache httpd 2.4.38

This webserver is running SuiteCRM. Surely enough, I was able to login to the webpage by trying the username/password of "admin:admin"!  I explored the site, but I didn't find much information beside that the SuiteCRM version 7.12.3 is vulnerable to a RCE.  


[!Results](screenshots/1.png)


The login/password is admin/admin.
### Port 3306 MySQL
I was unable to login to MySQL even though 

### 33060 Socks5
I did not find any information from this service running on the port.

## Exploit
The target machine is vulnerable to this CVE, CVE-2022-23940. The version of suite CRM, 7.12.3, allows authenitcated RCE. Given I can login using admin credentials, I can run the exploit for the CVE and get a reverse shell.

[!Results](screenshots/2.png)

### Local Flag

[!Results](screenshots/3.png)

### Root Flag
I tried manual privesc but did not have any success. I transfered linpeas to the victim machine from my target machine by starting a python server that hosted the linpeas.sh file.  After running linpeas, I discovered that the user, wwww-data, can run the ```service``` command as sudo with no password. Using GTFOBins, I was able to run service as sudo to escalate my privileges to root.

[!Results](screenshots/4.png)

[!Results](screenshots/5.png)