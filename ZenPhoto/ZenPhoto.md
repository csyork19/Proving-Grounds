# ZenPhoto

Machine: [ZenPhoto](https://portal.offensive-security.com/labs/practice)\
Difficulty: Intermediate\


## Enumeration
What ports are open?
'''
PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH 5.3p1 Debian 3ubuntu7 (Ubuntu Linux; protocol 2.0)
23/tcp   open  ipp     CUPS 1.4
80/tcp   open  http    Apache httpd 2.2.14 ((Ubuntu))
3306/tcp open  mysql   MySQL (unauthorized)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
'''

ssh - I do not see anything vulnerable for this version of ssh.
http - The webpage is underconstruction and the directory scan results are shown below. Also, the version that is running on the port is vulnerable to a number of things, but I don't know if it pertains to this machine: https://www.rapid7.com/db/modules/auxiliary/dos/http/apache_mod_isapi/

ipp - I am not familar with this service nor am I familar with the verison so I had to do some research. CUPS is .......It might be vulnerable to possible remote command execution: https://www.exploit-db.com/exploits/41233
https://www.exploit-db.com/exploits/34152.  IPP is the only protocol that CUPS supports natively and is supported by most network printers and print servers.

reddis- possible rce:https://github.com/Ridter/redis-rce

mysql- there do not appear to be any users 




## Exploitation Attempts
In the directory scan, I did find a page that uses ZenPhoto. I did not know that it is a theme used in a page. This leads me to believe this is the vulnerable https://www.exploit-db.com/exploits/18083. I exectuted the script but I did not get anything at first but it was due to the parameter that I was passing to the php payload. I managaged to get a shell as www-data, but I am trying to upgrade this shell or get a different shell somehow.

Possible user 'saned' from cat /etc/passwd. 


## Exploit

### Local/User flag
*** Insert screenshot of local flag ***

### Root Flag




