# SunsetNoontide

Machine: [SunsetNoontide](https://portal.offensive-security.com/labs/play)\
Difficulty: Warm up




## Enumeration

What operating system is on this machine? Linux
What ports/services are on running on this machine?
![Results!](screenshots/1.png)

I wasn't aware what this port or service is used for so I had to do alittle research to find more information. After some research online, I find that this service is vulnerable to I use searchsploit to see what I can find. So there is an exploit available for us to use, so I started up metasploit, set the options, and set the payload. Now when I run the payload I will get a reverse shell!\
![Results!](screenshots/2.png)\

![Results!](screenshots/3.png)\

![Results!](screenshots/4.png)\



## Flags
User:
![Results!](screenshots/4.png)

Root:
![Results!](screenshots/5.png)
