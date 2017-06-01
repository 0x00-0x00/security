## beep 10.10.10.7

linux-maskin

`PORT      STATE SERVICE`

`22/tcp    open  ssh`

`25/tcp    open  smtp`

`80/tcp    open  http`

`110/tcp   open  pop3`

`111/tcp   open  rpcbind`

`143/tcp   open  imap`

`443/tcp   open  https`

`993/tcp   open  imaps`

`995/tcp   open  pop3s`

`3306/tcp  open  mysql`

`4445/tcp  open  upnotifyp`

`10000/tcp open  snet-sensor-mgmt`

http med sql. nice

apache 2.2.3 men ingen exploits

111/tcp   open  rpcbind    2 \(RPC \#100000\)

\| rpcinfo:

\|   program version   port/proto  service

\|   100000  2            111/tcp  rpcbind

\|   100000  2            111/udp  rpcbind

\|   100024  1            753/udp  status

\|\_  100024  1            756/tcp  status

143/tcp   open  imap       Cyrus imapd 2.3.7-Invoca-RPM-2.3.7-7.el5\_6.4

\|\_imap-capabilities: RENAME Completed URLAUTHA0001 SORT=MODSEQ OK QUOTA ACL CONDSTORE CATENATE SORT LISTEXT THREAD=REFERENCES ID NAMESPACE ATOMIC IDLE X-NETSCAPE ANNOTATEMORE STARTTLS THREAD=ORDEREDSUBJECT IMAP4rev1 LITERAL+ MAILBOX-REFERRALS RIGHTS=kxte UIDPLUS MULTIAPPEND LIST-SUBSCRIBED IMAP4 CHILDREN BINARY UNSELECT NO

443/tcp   open  ssl/http   Apache httpd 2.2.3 \(\(CentOS\)\)

\| http-robots.txt: 1 disallowed entry

\|\_/

\|\_http-server-header: Apache/2.2.3 \(CentOS\)

\|\_http-title: Elastix - Login page

\| ssl-cert: Subject: commonName=localhost.localdomain/organizationName=SomeOrganization/stateOrProvinceName=SomeState/countryName=--

\| Not valid before: 2017-04-07T08:22:08

\|\_Not valid after:  2018-04-07T08:22:08

\|\_ssl-date: 2017-05-29T06:36:45+00:00; -1h02m39s from scanner time.

993/tcp   open  ssl/imap   Cyrus imapd

\|\_imap-capabilities: CAPABILITY

995/tcp   open  pop3       Cyrus pop3d

3306/tcp  open  mysql      MySQL \(unauthorized\)

4445/tcp  open  upnotifyp?

10000/tcp open  http       MiniServ 1.570 \(Webmin httpd\)

\[+\] 10.10.10.7:25         - 10.10.10.7:25 Users found: , adm, bin, daemon, fax, ftp, games, gdm, gopher, haldaemon, halt, lp, mail, news, nobody, operator, postgres, postmaster, sshd, sync, uucp, webmaster, www





post: running services

linux\_exploit\_suggester

