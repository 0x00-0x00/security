# popcorn 10.10.10.6

linux

22/tcp open  ssh     OpenSSH 5.1p1 Debian 6ubuntu2 **ingen exploits**

80/tcp open  http    Apache httpd 2.2.12 \(\(Ubuntu\)\) **ingen exploits**

dirb test og **torrent**

[http://10.10.10.6/torrent/login.php](http://10.10.10.6/torrent/login.php)

laste opp en torrent. prøve å finne et sted å laste opp bilde, obfuscate kode i bildet - funker ikke

`admin' or '1'='1`

`admin' or '1'='1`

adminpanel ingenting

må nok få tilgang til databse på en eller annen måte

torrent/database/ fant sql fil. inneholder hashet passord 1844156d4166d94387f1a4ad031ca5fa som blir admin12

kjører authenticated dirb

