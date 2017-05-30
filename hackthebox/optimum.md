## optimum 10.10.10.8

windows server 2012

nmap port 80

hfs 2.3 server. finnes exploit

kjørte i metasploit exploit/windows/http/rejetto\_hfs\_exec

sett srvhost til samme som lhost men ikke srvport

user.txt **d0c39409d7b994a9a1389ebf38ef5f73**

```
                                        Update           KB2959936  11/22/2014
```

[http://support.microsoft.com/?kbid=2896496](http://support.microsoft.com/?kbid=2896496)  Update           KB2896496  11/22/2014

[http://support.microsoft.com/?kbid=2919355](http://support.microsoft.com/?kbid=2919355)  Update           KB2919355  11/22/2014

[http://support.microsoft.com/?kbid=2920189](http://support.microsoft.com/?kbid=2920189)  Security Update  KB2920189  11/22/2014

[http://support.microsoft.com/?kbid=2928120](http://support.microsoft.com/?kbid=2928120)  Security Update  KB2928120  11/22/2014

[http://support.microsoft.com/?kbid=2931358](http://support.microsoft.com/?kbid=2931358)  Security Update  KB2931358  11/22/2014

[http://support.microsoft.com/?kbid=2931366](http://support.microsoft.com/?kbid=2931366)  Security Update  KB2931366  11/22/2014

[http://support.microsoft.com/?kbid=2933826](http://support.microsoft.com/?kbid=2933826)  Security Update  KB2933826  11/22/2014

[http://support.microsoft.com/?kbid=2938772](http://support.microsoft.com/?kbid=2938772)  Update           KB2938772  11/22/2014

[http://support.microsoft.com/?kbid=2949621](http://support.microsoft.com/?kbid=2949621)  Hotfix           KB2949621  11/22/2014

[http://support.microsoft.com/?kbid=2954879](http://support.microsoft.com/?kbid=2954879)  Update           KB2954879  11/22/2014

[http://support.microsoft.com/?kbid=2958262](http://support.microsoft.com/?kbid=2958262)  Update           KB2958262  11/22/2014

[http://support.microsoft.com/?kbid=2958263](http://support.microsoft.com/?kbid=2958263)  Update           KB2958263  11/22/2014

[http://support.microsoft.com/?kbid=2961072](http://support.microsoft.com/?kbid=2961072)  Security Update  KB2961072  11/22/2014

[http://support.microsoft.com/?kbid=2965500](http://support.microsoft.com/?kbid=2965500)  Update           KB2965500  11/22/2014

[http://support.microsoft.com/?kbid=2966407](http://support.microsoft.com/?kbid=2966407)  Update           KB2966407  11/22/2014

[http://support.microsoft.com/?kbid=2967917](http://support.microsoft.com/?kbid=2967917)  Update           KB2967917  11/22/2014

[http://support.microsoft.com/?kbid=2971203](http://support.microsoft.com/?kbid=2971203)  Update           KB2971203  11/22/2014

[http://support.microsoft.com/?kbid=2971850](http://support.microsoft.com/?kbid=2971850)  Security Update  KB2971850  11/22/2014

[http://support.microsoft.com/?kbid=2973351](http://support.microsoft.com/?kbid=2973351)  Security Update  KB2973351  11/22/2014

[http://support.microsoft.com/?kbid=2973448](http://support.microsoft.com/?kbid=2973448)  Update           KB2973448  11/22/2014

[http://support.microsoft.com/?kbid=2975061](http://support.microsoft.com/?kbid=2975061)  Update           KB2975061  11/22/2014

[http://support.microsoft.com/?kbid=2976627](http://support.microsoft.com/?kbid=2976627)  Security Update  KB2976627  11/22/2014

[http://support.microsoft.com/?kbid=2977629](http://support.microsoft.com/?kbid=2977629)  Security Update  KB2977629  11/22/2014

[http://support.microsoft.com/?kbid=2981580](http://support.microsoft.com/?kbid=2981580)  Update           KB2981580  11/22/2014

[http://support.microsoft.com/?kbid=2987107](http://support.microsoft.com/?kbid=2987107)  Security Update  KB2987107  11/22/2014

[http://support.microsoft.com/?kbid=2989647](http://support.microsoft.com/?kbid=2989647)  Update           KB2989647  11/22/2014

[http://support.microsoft.com/?kbid=2998527](http://support.microsoft.com/?kbid=2998527)  Update           KB2998527  11/22/2014

[http://support.microsoft.com/?kbid=3000850](http://support.microsoft.com/?kbid=3000850)  Update           KB3000850  11/22/2014

[http://support.microsoft.com/?kbid=3003057](http://support.microsoft.com/?kbid=3003057)  Security Update  KB3003057  11/22/2014

[http://support.microsoft.com/?kbid=3014442](http://support.microsoft.com/?kbid=3014442)  Update           KB3014442  11/22/2014

MS16-032 SYSTEM Privilege Escalation

prøvd å laste opp ps1-script og får kjørt det, men prosessen ligger i bakgrunnen.- sjekk ps kommando

må finne en måte å få reverse shell fra powershellet

`use exploit/windows/local/ms16_032_secondary_logon_handle_privesc`

tror denne er riktig.



`use post/multi/recon/local_exploit_suggester `**` `  **



