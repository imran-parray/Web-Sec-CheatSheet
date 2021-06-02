__2FA - Forced browsing__
```js
Try accessing different endpoints directly with the avilable token
```

__2FA - Response Manipulation__
```js
change : {succes:"false"} -> {success:"true"}
```

__2FA - Response manipulation status code__
```js
change 403 -> 200
```

__2FA - Reusable Codes__
```js
using the same code twice for bypassing validation
```



__2FA - Lack of bruteforce__
```js
Bruteforce the pin 
```


__2FA - lack of bruteforce with Additional Headers__
```js
try to Bypass ratelimit using these headers:
1.  X-Originating-IP: 127.0.0.1
2.  X-Forwarded-For: 127.0.0.1
3.  X-Remote-IP: 127.0.0.1
4.  X-Remote-Addr: 127.0.0.1
5.  X-Forwarded-Host : 127.0.0.1
6.  X-Client-IP : 127.0.0.1
7.  X-Host : 127.0.0.1
8.  Forwarded: 127.0.0.1
9.  X-Forwarded-By: 127.0.0.1
10.  X-Forwarded-For-IP: 127.0.0.1
11.  X-True-IP: 127.0.0.1
```


__2FA - Cross token usage__
```js
Use the token A on Account B
```




__2FA - Bypass using 0Auth__
```js
Try loggin in using 0Auth this may bypass 2fa
```


__2FA - No limit to send OTP by company__
```js
Send as many as request to the company to waste as much money as can
```


__2FA - Bruteforce - IP based bruteforce__
```js
Try bypassing the rate limit protection using BURPIPROtator Plugin
```


__2FA - Previous OTP not expiring__
```js
1.  Get a OTP 12345
2.  GET a new OTP 877678
3.  Try using the 12345
4.  if its working you can try getting as many as OTP's to increase the chances of bruteforcing
```

__2FA - Password Change__
```js
After changing the password the webapp may not ask for 2FA confirmation
```


