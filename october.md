## october 10.10.10.16

linux

22/tcp open  ssh     OpenSSH 6.6.1p1 Ubuntu 2ubuntu2.8 \(Ubuntu Linux; protocol 2.0\)

80/tcp open  http    Apache httpd 2.4.7 \(\(Ubuntu\)\)

octobercms

**server 2003 sp2 x86**

* Retrieved x-powered-by header: PHP/5.5.9-1ubuntu4.21

  Potentially risky methods: PUT PATCH DELETE

[http://10.10.10.16/backend/backend/auth/signin](http://10.10.10.16/backend/backend/auth/signin)

suid enabled binaries / buffer overflows?

/usr/local/bin/ovrflw

Exploiting /usr/local/bin/ovrflw but NX bit is on and ASLR is enabled on the machine

