
### Introduction

SimpleDNS is a very simple DNS server.<br />
It was made to learn the basics of the DNS protocol.

Features:
* very small
* single-threaded
* all necessary data structures for further features
* very simplistic memory management
* no full protection against malformed requests :|

### Build

<pre>
git clone https://github.com/mwarning/SimpleDNS.git
cd SimpleDNS
cmake .
make
</pre>

### Test

Start SimpleDNS:
<pre>
$./sdns
Listening on port 9000.
</pre>

In another window execute [dig](http://linux.die.net/man/1/dig).
On Debian, dig is part of the dnsutils package.

<pre>
$ dig @127.0.0.1 -p 9000 foo.bar.com 

; <<>> DiG 9.8.4-rpz2+rl005.12-P1 <<>> @127.0.0.1 -p 9000 foo.bar.com
; (1 server found)
;; global options: +cmd
;; Got answer:
;; -&gt;&gt;HEADER&lt;&lt;- opcode: QUERY, status: NOERROR, id: 15287
;; flags: qr; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 0

;; QUESTION SECTION:
;foo.bar.com.                   IN      A

;; ANSWER SECTION:
foo.bar.com.            0       IN      A       192.168.1.1

;; Query time: 0 msec
;; SERVER: 127.0.0.1#9000(127.0.0.1)
;; WHEN: Mon Apr 15 00:50:38 2013
;; MSG SIZE  rcvd: 56
</pre>

### Recommended Reading

The DNS section of the [TCP/IP-Guide](http://www.tcpipguide.com/free/t_TCPIPDomainNameSystemDNS.htm) was very helpful
for understanding the protocol.

