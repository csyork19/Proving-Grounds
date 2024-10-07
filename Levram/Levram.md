# Levram 
# Proving Grounds - Practice



## Enumeration

```
PORT     STATE SERVICE  VERSION
22/tcp   open  ssh      OpenSSH 8.9p1 Ubuntu 3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   256 b9:bc:8f:01:3f:85:5d:f9:5c:d9:fb:b6:15:a0:1e:74 (ECDSA)
|_  256 53:d9:7f:3d:22:8a:fd:57:98:fe:6b:1a:4c:ac:79:67 (ED25519)
8000/tcp open  http-alt WSGIServer/0.2 CPython/3.10.6
|_http-cors: GET POST PUT DELETE OPTIONS PATCH
|_http-title: Gerapy
|_http-server-header: WSGIServer/0.2 CPython/3.10.6
| fingerprint-strings: 
|   FourOhFourRequest: 
|     HTTP/1.1 404 Not Found
|     Date: Mon, 07 Oct 2024 03:22:58 GMT
|     Server: WSGIServer/0.2 CPython/3.10.6
|     Content-Type: text/html
|     Content-Length: 9979
|     Vary: Origin
|     <!DOCTYPE html>
|     <html lang="en">
|     <head>
|     <meta http-equiv="content-type" content="text/html; charset=utf-8">
|     <title>Page not found at /nice ports,/Trinity.txt.bak</title>
|     <meta name="robots" content="NONE,NOARCHIVE">
|     <style type="text/css">
|     html * { padding:0; margin:0; }
|     body * { padding:10px 20px; }
|     body * * { padding:0; }
|     body { font:small sans-serif; background:#eee; color:#000; }
|     body>div { border-bottom:1px solid #ddd; }
|     font-weight:normal; margin-bottom:.4em; }
|     span { font-size:60%; color:#666; font-weight:normal; }
|     table { border:none; border-collapse: collapse; width:100%; }
|     vertical-align:top; padding:2px 3px; }
|     width:12em; text-align:right; color:#6
|   GetRequest: 
|     HTTP/1.1 200 OK
|     Date: Mon, 07 Oct 2024 03:22:52 GMT
|     Server: WSGIServer/0.2 CPython/3.10.6
|     Content-Type: text/html; charset=utf-8
|     Vary: Accept, Origin
|     Allow: OPTIONS, GET
|     Content-Length: 2530
|_    <!DOCTYPE html><html lang=en><head><meta charset=utf-8><meta http-equiv=X-UA-Compatible content="IE=edge"><meta name=viewport content="width=device-width,initial-scale=1"><link rel=icon href=/favicon.ico><title>Gerapy</title><link href=/static/css/chunk-10b2edc2.79f68610.css rel=prefetch><link href=/static/css/chunk-12e7e66d.8f856d8c.css rel=prefetch><link href=/static/css/chunk-39423506.2eb0fec8.css rel=prefetch><link href=/static/css/chunk-3a6102b3.0fe5e5eb.css rel=prefetch><link href=/static/css/chunk-4a7237a2.19df386b.css rel=prefetch><link href=/static/css/chunk-531d1845.b0b0d9e4.css rel=prefetch><link href=/static/css/chunk-582dc9b0.d60b5161.css rel=prefetch><link href=/static/css/chun
1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service :
SF-Port8000-TCP:V=7.94SVN%I=7%D=10/6%Time=6703540C%P=x86_64-pc-linux-gnu%r
SF:(GetRequest,AAA,"HTTP/1\.1\x20200\x20OK\r\nDate:\x20Mon,\x2007\x20Oct\x
SF:202024\x2003:22:52\x20GMT\r\nServer:\x20WSGIServer/0\.2\x20CPython/3\.1
SF:0\.6\r\nContent-Type:\x20text/html;\x20charset=utf-8\r\nVary:\x20Accept
SF:,\x20Origin\r\nAllow:\x20OPTIONS,\x20GET\r\nContent-Length:\x202530\r\n
SF:\r\n<!DOCTYPE\x20html><html\x20lang=en><head><meta\x20charset=utf-8><me
SF:ta\x20http-equiv=X-UA-Compatible\x20content=\"IE=edge\"><meta\x20name=v
SF:iewport\x20content=\"width=device-width,initial-scale=1\"><link\x20rel=
SF:icon\x20href=/favicon\.ico><title>Gerapy</title><link\x20href=/static/c
SF:ss/chunk-10b2edc2\.79f68610\.css\x20rel=prefetch><link\x20href=/static/
SF:css/chunk-12e7e66d\.8f856d8c\.css\x20rel=prefetch><link\x20href=/static
SF:/css/chunk-39423506\.2eb0fec8\.css\x20rel=prefetch><link\x20href=/stati
SF:c/css/chunk-3a6102b3\.0fe5e5eb\.css\x20rel=prefetch><link\x20href=/stat
SF:ic/css/chunk-4a7237a2\.19df386b\.css\x20rel=prefetch><link\x20href=/sta
SF:tic/css/chunk-531d1845\.b0b0d9e4\.css\x20rel=prefetch><link\x20href=/st
SF:atic/css/chunk-582dc9b0\.d60b5161\.css\x20rel=prefetch><link\x20href=/s
SF:tatic/css/chun")%r(FourOhFourRequest,279E,"HTTP/1\.1\x20404\x20Not\x20F
SF:ound\r\nDate:\x20Mon,\x2007\x20Oct\x202024\x2003:22:58\x20GMT\r\nServer
SF::\x20WSGIServer/0\.2\x20CPython/3\.10\.6\r\nContent-Type:\x20text/html\
SF:r\nContent-Length:\x209979\r\nVary:\x20Origin\r\n\r\n<!DOCTYPE\x20html>
SF:\n<html\x20lang=\"en\">\n<head>\n\x20\x20<meta\x20http-equiv=\"content-
SF:type\"\x20content=\"text/html;\x20charset=utf-8\">\n\x20\x20<title>Page
SF:\x20not\x20found\x20at\x20/nice\x20ports,/Trinity\.txt\.bak</title>\n\x
SF:20\x20<meta\x20name=\"robots\"\x20content=\"NONE,NOARCHIVE\">\n\x20\x20
SF:<style\x20type=\"text/css\">\n\x20\x20\x20\x20html\x20\*\x20{\x20paddin
SF:g:0;\x20margin:0;\x20}\n\x20\x20\x20\x20body\x20\*\x20{\x20padding:10px
SF:\x2020px;\x20}\n\x20\x20\x20\x20body\x20\*\x20\*\x20{\x20padding:0;\x20
SF:}\n\x20\x20\x20\x20body\x20{\x20font:small\x20sans-serif;\x20background
SF::#eee;\x20color:#000;\x20}\n\x20\x20\x20\x20body>div\x20{\x20border-bot
SF:tom:1px\x20solid\x20#ddd;\x20}\n\x20\x20\x20\x20h1\x20{\x20font-weight:
SF:normal;\x20margin-bottom:\.4em;\x20}\n\x20\x20\x20\x20h1\x20span\x20{\x
SF:20font-size:60%;\x20color:#666;\x20font-weight:normal;\x20}\n\x20\x20\x
SF:20\x20table\x20{\x20border:none;\x20border-collapse:\x20collapse;\x20wi
SF:dth:100%;\x20}\n\x20\x20\x20\x20td,\x20th\x20{\x20vertical-align:top;\x
SF:20padding:2px\x203px;\x20}\n\x20\x20\x20\x20th\x20{\x20width:12em;\x20t
SF:ext-align:right;\x20color:#6");
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

```


### SSH Port 22
OpenSSH 8.9p1 Ubuntu 3 (Ubuntu Linux; protocol 2.0)


### Http-alt Port 8000
*** enter screenshot of the login page ***
Gereapy Version - Gerapy v0.9.7 

I was able to login with default credentials - admin/admin as the username/password respectively. 



## Exploit
I found an RCE on exploit db for the Gerapy version running on the target machine. It is available here - https://www.exploit-db.com/exploits/50640. 
The service running on port 8000 is vulnerable to a remote code execution. More information found here - CVE-2021-43857.
After modifying the exploit that I found online, along with makng some changes on the vulnerable service, I was able to get a reverse shell on the target machine.

For privilege escalation, pay attention to the output of tools such as linpeas. 


### Proof 
![Results!](screenshots/1.png)


