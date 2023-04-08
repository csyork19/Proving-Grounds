#  Djinn3 
Machine: [Djinn3](https://portal.offensive-security.com/labs/play)\
Difficulty: Hard


## Enumeration
What ports are open? 
```
PORT      STATE SERVICE VERSION
22/tcp    open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 e64423acb2d982e79058155e4023ed65 (RSA)
|   256 ae04856ecb104f554aad969ef2ce184f (ECDSA)
|_  256 f708561997b5031018667e7d2e0a4742 (ED25519)
80/tcp    open  http    lighttpd 1.4.45
|_http-title: Custom-ers
|_http-server-header: lighttpd/1.4.45
5000/tcp  open  http    Werkzeug httpd 1.0.1 (Python 3.6.9)
|_http-title: Site doesn't have a title (text/html; charset=utf-8).
|_http-server-header: Werkzeug/1.0.1 Python/3.6.9
31337/tcp open  Elite?
```


### Credentials discovered (if any)

### Ports Info
#### SSH 22
This version is not vulnerable. However, this might be leveraged if we find user credentials via other means of enumeration. 
#### Http 80
Version: Lighttpd 1.4.45
Version Vulnerable? Yes but not that would be useful in this ctf situation.

Webpage frameworks used? If so, vulnerable?
Themes used? If so, vulnerable?
Anything standout in the page source? 


*** Insert screenshot of the home page *** 

I ran a gobuster scan using the below command. While the scan was happening, I performed manual enumeration on the webpage. There are no robots.txt or cgi-bin folder present, and most of the links on the webpage are not linked to anything. 

```
gobuster dir -u http://192.168.125.102 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -t 40 -x .sh,.txt,.html
```

Nikto Scan:
```
└─$ nikto -h http://192.168.125.102
- Nikto v2.5.0
---------------------------------------------------------------------------
+ Target IP:          192.168.125.102
+ Target Hostname:    192.168.125.102
+ Target Port:        80
+ Start Time:         2023-04-07 21:01:46 (GMT-4)
---------------------------------------------------------------------------
+ Server: lighttpd/1.4.45
+ /: The anti-clickjacking X-Frame-Options header is not present. See: https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options
+ /: The X-Content-Type-Options header is not set. This could allow the user agent to render the content of the site in a different fashion to the MIME type. See: https://www.netsparker.com/web-vulnerability-scanner/vulnerabilities/missing-content-type-header/
+ No CGI Directories found (use '-C all' to force check all possible dirs)
+ OPTIONS: Allowed HTTP Methods: OPTIONS, GET, HEAD, POST .
+ /#wp-config.php#: #wp-config.php# file found. This file contains the credentials.
+ 8102 requests: 0 error(s) and 4 item(s) reported on remote host
+ End Time:           2023-04-07 21:09:46 (GMT-4) (480 seconds)
---------------------------------------------------------------------------
+ 1 host(s) tested

```

Wp-scan:



#### Http 5000
Version: Werkzeug httpd 1.0.1 (Python 3.6.9)
Version Versionable? Werkzeug httpd 1.0.1 (Python 3.6.9)

I ran a directory scan but I did not get much information back. However, I did find that the werkzeug may be vulnerable to this, https://www.exploit-db.com/exploits/43905. THe page did show some information that is useful to the 31337 port.
```
gobuster dir -u http://192.168.125.102:5000 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -t 40 -x .sh,.txt,.html
```
I tried to to LFI on the page with the 'id' parameter, but I was not successful. 

Nikto Scan:
```
└─$ nikto -h http://192.168.125.102:5000                    
- Nikto v2.5.0
---------------------------------------------------------------------------
+ Target IP:          192.168.125.102
+ Target Hostname:    192.168.125.102
+ Target Port:        5000
+ Start Time:         2023-04-07 21:33:57 (GMT-4)
---------------------------------------------------------------------------
+ Server: Werkzeug/1.0.1 Python/3.6.9
+ /: The anti-clickjacking X-Frame-Options header is not present. See: https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options
+ /: The X-Content-Type-Options header is not set. This could allow the user agent to render the content of the site in a different fashion to the MIME type. See: https://www.netsparker.com/web-vulnerability-scanner/vulnerabilities/missing-content-type-header/
+ No CGI Directories found (use '-C all' to force check all possible dirs)
+ Python/3.6.9 appears to be outdated (current is at least 3.9.6).
+ OPTIONS: Allowed HTTP Methods: GET, HEAD, OPTIONS .
+ /#wp-config.php#: #wp-config.php# file found. This file contains the credentials.
+ 8102 requests: 0 error(s) and 5 item(s) reported on remote host
+ End Time:           2023-04-07 21:49:19 (GMT-4) (922 seconds)
---------------------------------------------------------------------------
+ 1 host(s) tested

```


#### 31337 Elete ?
I am able to login using netcat and normal credentials.
```
nc -nv 192.168.125.102 31337
```
Creds: guest/guest.

```
$ nc -nv 192.168.125.102 31337
(UNKNOWN) [192.168.125.102] 31337 (?) open
username> guest
password> guest

Welcome to our own ticketing system. This application is still under 
development so if you find any issue please report it to mail@mzfr.me

Enter "help" to get the list of available commands.

```

                                    


#### SSH 7744
This version is not vulnerable. However, this might be leveraged if we find user credentials via other means of enumeration. 

https://www.exploit-db.com/exploits/17465


## Exploit

## Local/User Flag


## Root Flag
