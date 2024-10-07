# Vault
Proving Grounds - Practice

## Enumeration

```
PORT     STATE SERVICE       VERSION
53/tcp   open  domain?
88/tcp   open  kerberos-sec  Microsoft Windows Kerberos (server time: 2024-06-09 14:00:11Z)
135/tcp  open  msrpc         Microsoft Windows RPC
139/tcp  open  netbios-ssn   Microsoft Windows netbios-ssn
389/tcp  open  ldap          Microsoft Windows Active Directory LDAP (Domain: vault.offsec0., Site: Default-First-Site-Name)
445/tcp  open  microsoft-ds?
464/tcp  open  kpasswd5?
593/tcp  open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
636/tcp  open  tcpwrapped
3268/tcp open  ldap          Microsoft Windows Active Directory LDAP (Domain: vault.offsec0., Site: Default-First-Site-Name)
3269/tcp open  tcpwrapped
3389/tcp open  ms-wbt-server Microsoft Terminal Services
| rdp-ntlm-info: 
|   Target_Name: VAULT
|   NetBIOS_Domain_Name: VAULT
|   NetBIOS_Computer_Name: DC
|   DNS_Domain_Name: vault.offsec
|   DNS_Computer_Name: DC.vault.offsec
|   DNS_Tree_Name: vault.offsec
|   Product_Version: 10.0.17763
|_  System_Time: 2024-06-09T14:02:27+00:00
|_ssl-date: 2024-06-09T14:03:07+00:00; +2s from scanner time.
| ssl-cert: Subject: commonName=DC.vault.offsec
| Not valid before: 2024-02-17T05:45:56
|_Not valid after:  2024-08-18T05:45:56
Service Info: Host: DC; OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:
| smb2-security-mode: 
|   3:1:1: 
|_    Message signing enabled and required
| smb2-time: 
|   date: 2024-06-09T14:02:28
|_  start_date: N/A
|_clock-skew: mean: 1s, deviation: 0s, median: 0s

```

### DNS port 53

### Kerberos port 88 

### Msrpc port 135

### SMB 139/445

### Ldap 389





## Exploit

### Local Flag 

### Root Flag
