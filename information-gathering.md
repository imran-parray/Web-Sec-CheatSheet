Google
======
site: site.com inurl:login,register,upload,logout,redirect,redir,goto,admin
site: site.com inurl:&
site: site.com ext:php,asp,aspx,jsp,jspa,txt,swf



Publics sites:
===============

https://pentest-tools.com/
https://virustotal.com/
http://whois.webhosting.info/
https://www.shodan.io/
https://crt.sh/?q=%25taregt.com
https://dnsdumpster.com/
https://censys.io
http://dnsgoodies.com




Github
======

using github
trufflehog http://www.github.com/invis/jshjsd.git
“badoo.com” API_key
“badoo.com” secret_key
“badoo.com” aws_key
“badoo.com” Password 
“badoo.com” FTP
“badoo.com” login 
“badoo.com” github_token 
"badoo.com" password
"badoo.com" dev
"api.badoo.com"







SubDomain Enumeration Process
=============================
https://virustotal.com 
https://dnsdumpster.com/
subdomain Bruteforce
	-sublist3r
	-knockpy
	-aquatone
	-massdns

Takeover Check
	-Manually
	-sub6.py
	-aquatone -takeover
	-EyeWitness





Finding S3 Buckets
==================

site:amazonaws.com -s3 badoo
site:amazonaws.com inurl:badoo
Google: site:s3.amazonaws.com + hackme.tld
Github: “hackme.tld” + “s3”
$cd imxx ; ruby lazys2.rb hackerone






Using Archieve.org
==================
cd /imxx/wayback-py
python waybackrobots.py http://www.hackerone.com
Download all The links
cd /imxx/JsParser
python handler.py
http://127.0.0.1:8008
paste all the links and wait for the magic to happen.





HTTP TRACE CHECK
================

http methods [curl -vX TRACE "https://gratipay.com"]
use head on restricted areas



Detect Technologies
===================
Mobile Site.
Host tatget.com
nc 127.0.0.1 80
nmap '*' target.com
whatweb
wafw00f
lbd
Nmap ‘*’
httprint
clustered [ clusterd -i 127.0.0.1 -o linux –fingerprint ]
nikto




-->Run a Spider<--
==================


inputScanner
============
>Change Burp to Scope only
>Spider the Host 
>Copy All the Links
>Paste in /opt/lampp/htdocs/InputScanner/url.txt
>open http://127.0.0.1/InputScanner/
>Done !
>Copy output-js.txt from Output folder
>Paste it into ../htdocs/Jscanner/
>Visit http://127.0.0.1/Jscanner/
