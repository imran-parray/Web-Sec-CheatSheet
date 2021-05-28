__Where to look for Bugs__


- login
- reset password
- 2fA
- Confirmation codes
- Sign up


__using Null Chars__

```js
%00, %0d%0a, %09, %0C, %20, %0
```
```js
>brute force using abc@xyz.com
	after some time
	you got blocked
>try abc@xyz.com%00
```

__Host Header injection:__ 

```console
Change Host:www.newsite.com
Change Host:localhost
Change Host:127.0.0.1
```


__Changing cookies__
```js
For example if it blocks by 15 Requests
Change session on 14 req and try 
```


__X-forwaded-forwaded-For__
```js
add Header X-Forwaded-For:198.168.43.1

- Ping Website and Get the Ip address of The server
- Change The X-Forwaded-For:[Website-ip]
```

__2x-X-forwaded-forwaded-For__

```js
add 2 headers
add Header X-Forwaded-For:
add Header X-Forwaded-For:198.168.43.1
```

__Checking Mobile App__

```js
same Endpoint in mobile app
```

