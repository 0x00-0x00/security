# **lame **10.10.10.3

`root@kali:~# nmap -sS 10.10.10.3`

`Starting Nmap 7.40 ( https://nmap.org ) at 2017-05-26 09:05 EDT`

`Nmap scan report for 10.10.10.3`

`Host is up (0.053s latency).`

`Not shown: 996 filtered ports`

`PORT    STATE SERVICE`

`21/tcp  open  ftp`

`22/tcp  open  ssh`

`139/tcp open  netbios-ssn`

`445/tcp open  microsoft-ds`

vsftpd 2.3.4, prøvde metasploit uten hell

ssh erOpenSSH 4.7p1 - ingen vulns

port 139 smb har version 3.0.20 [https://www.rapid7.com/db/modules/exploit/multi/samba/usermap\_script](https://www.rapid7.com/db/modules/exploit/multi/samba/usermap_script)

**shell! og root!**

flag: **92caac3be140ef409e45721348a4e9df**

home/user/makis/user.txt **69454a937d94f5f0225ea00acd2e84c5**

