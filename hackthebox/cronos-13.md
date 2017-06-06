### cronos 10.10.10.13

linux

`22/tcp open  ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.1 (Ubuntu Linux; protocol 2.0)`

`53/tcp open  domain  ISC BIND 9.10.3-P4-Ubuntu`

`80/tcp open  http    Apache httpd 2.4.18 ((Ubuntu))`

root@kali:~\# dnsrecon -d 10.10.10.13 -t zonewalk

\[\*\] Performing NSEC Zone Walk for 10.10.10.13

\[\*\] Getting SOA record for 10.10.10.13

\[\*\] Name Server 75.127.96.89 will be used

\[\*\]      A 10.10.10.13 10.10.10.13

\[\*\]      A aaa no\_ip

\[\*\] 2 records found

use auxiliary/gather/enum\_dns

[https://www.exploit-db.com/docs/12389.pdf](https://www.exploit-db.com/docs/12389.pdf)

[https://pentestlab.blog/tag/dns-enumeration/](https://pentestlab.blog/tag/dns-enumeration/)



root@kali:~\# host -t ns 10.10.10.13 10.10.10.13

Using domain server:

Name: 10.10.10.13

Address: 10.10.10.13\#53

Aliases: 



13.10.10.10.in-addr.arpa domain name pointer **ns1.cronos.htb.**



