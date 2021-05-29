__Basic Test__
```console
curl -H "Origen:http://evil.com" --verbose http://www.test.com/example/testpage.php
```

__Server Response__

```http
Access-control-allow-origens:*				---	Vulnerable
Access-control-allow-origens:	[null]			---	Vulnerable
Access-control-allow-origens:http://evil.com		---	Vulnerable

```
__2x-Headers__

```http
Origen:http://evil.com
Origen:http://evil.com
```


__Method2 [No HTTPS]__


```http
Req=> Origen:http://www.google.com
```
```http
Res=>Access-control-allow-origens:http://www.google.com
Res=>Access-control-allow-credentials:true
```
> If it is the respone then the Contents can be loaded from The 
> 


#### Note 


> Note that if you have found an unsecure web app which allows all the domains to make requests to the sensitive infomation on the server try to find out the http method alow while making the request try using DELETE and put request if they are allowed !





__Testing Crossdomain.xml__
```http
<allow-access-from domain="*"/> 	---	Vulnerable Completely
```
