# OSCP

**Some info**

cory is a difficult machime

"big 3" in the course are called pain, sufference and humble

exploit 8478 pain oscp [https://www.exploit-db.com/exploits/8478/](https://www.exploit-db.com/exploits/8478/)

exam: 5 machines, must root 4. the hardest is buffer overflow from scratch

**Should learn:**

* python
* buffer overflow
* port forwaring and pivoting
* practice post exploitation

**Read **_**Jollyfrog's tale**_  
[http://www.techexams.net/forums/security-certifications/110760-oscp-jollyfrogs-tale-5.html](http://www.techexams.net/forums/security-certifications/110760-oscp-jollyfrogs-tale-5.html)

### OSCP-like Vulnhub VMs

Before starting the PWK course I solved some of the Vulnhub VMs so I don't need to start from rock bottom on the PWK lab. Below is a list of Vulnhub VMs I solved, most of them are similar to what you'll be facing in the lab. I've written walkthroughs for a few of them as well, but try harder first ;\)

[http://www.abatchy.com/2017/02/oscp-like-vulnhub-vms.html](http://www.abatchy.com/2017/02/oscp-like-vulnhub-vms.html)

**  
Beginner friendly:**  
All these are \*nix based

```
Kioptrix: Level 1 (#1) 
Kioptrix: Level 1.1 (#2) 
Kioptrix: Level 1.2 (#3) 
Kioptrix: Level 1.3 (#4) 
FristiLeaks: 1.3 
Stapler: 1
PwnLab: init
 Intermediate:
Kioptrix: 2014
Brainpan: 1
Mr-Robot: 1  
HackLAB: Vulnix
VulnOS: 2
SickOs: 1.2
/dev/random: scream 
pWnOS: 2.0
SkyTower: 1 
IMF
```

**Windows **  
There aren't many Windows machines around due to licensing. Few options:  
Metasploitable 3, will download a trial version of Windows Server.  
[https://github.com/magnetikonline/linuxmicrosoftievirtualmachines](https://github.com/magnetikonline/linuxmicrosoftievirtualmachines) you can download Windows VMs legally then hack your way through them through an unpatched vulnerability or setting up a vulnerable software.

Set up your own lab. Default Windows XP SP0 will give you the chance to try out a few remote exploits, or doing some privilege escalation using weak services.  
/dev/random: Sleepy \(Uses VulnInjector, need to provide you own ISO and key.\)  
Bobby: 1 \(Uses VulnInjector, need to provide you own ISO and key.\)  
[https://github.com/g0tmi1k/VulnInjector](https://github.com/g0tmi1k/VulnInjector)

**Printing proof**

```
Linux:
echo " ";echo "uname -a:";uname -a;echo " ";echo "hostname:";hostname;echo " ";echo "id";id;echo " ";echo "ifconfig:";/sbin/ifconfig -a;echo " ";echo "proof:";cat /root/proof.txt 2>/dev/null; cat /Desktop/proof.txt 2>/dev/null;echo " "

Windows:
echo. & echo. & echo whoami: & whoami 2> nul & echo %username% 2> nul & echo. & echo Hostname: & hostname & echo. & ipconfig /all & echo. & echo proof.txt: & type "C:\Users\Administrator\Desktop\proof.txt" 2> nul & type "C:\Documents and Settings\Administrator\Desktop\proof.txt" 2> nul & type %USERPROFILE%\Desktop\proof.txt 2> nul
```



