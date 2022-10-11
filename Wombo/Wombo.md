# Wombo

Machine: [Wombo](https://portal.offensive-security.com/labs/practice)\
Difficulty: Intermediate\


## Enumeration
What ports are open?
*** insert screenshots of open ports ***


What are the versions of the services?
22/ssh - OpenSSH 7.4p1\ 
80/http - nginx 1.10.3\
6379/redis - Redis key-value store 5.0.9\
8080/http-proxy
27017/mongod - MongoDB 4.0.18\

ssh - At first glance this version of ssh does not seem to be vulnerable to anything of use. If I do find creds, I may try to ssh in as a particular otherwise we can probably just ignore this port. 

http - This is a webpage being so I go ahead and start running a couple of directory scans. While those scans are running in the background, I went ahead and research the version of nginx to see what I can find. I used a combination of google and searchsploit. According to this [site](https://www.cybersecurity-help.cz/vdb/SB2021052543), this version of nginx is vulnerable to RCE due to what appears to be a buffer overflow. Nothing came back from the directory scan and the webpage is just the normal page for nginx.


redis - From a bit of research I find that this version might be vulnerable to unauthenticated code execution. I found a metsploit module for it on [exploit db](https://www.exploit-db.com/exploits/47195), but I will try to not use metasploit if possible. I found a python script that is supposed to perform this exploit, link [here](https://github.com/Ridter/redis-rce).

http proxy - 

*** Insert screenshot of page *** 


*** Insert screenshot of robots.txt ***

The /admin/ directory brings us to a login page and the /reset/ directory leads to a page that prompts users to enter their email to get a new password setup. The /reset/ does not seem of any interest because I have no need to have the page send an email to me and I don't see burpsuite being of any use in this situation.  The /admin/ page could be of interest because we might be able to brute force login and get a shell that way.

mongodb - This version does not appear to have any vulnerabilites that will help.


