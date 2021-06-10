
__Basic Commands:__

```console
help
date
cal
man
df--------------Show Curent Disk Space
Free -----------Show Current Free Space
uname -r --------Kernel Version
cat /etc/*release ----Check Distro Version
```

__Changing Directories__


```console
pwd------------Print Working Directory
cd--------------Change Directory
cd Desktop------Change to Destop
cd--------------Change to Home 
cd - -----------Change me back to previous Dir
cd ~ -----------Change to Back to Home Dir
clear ----------Clear The Terminal
Exit -----------Exit The Terminal
```



__Listing FIles__

```console
ls -------------------------------List All The Files and Folders
ls Documents --------------------List Inside The Documents
ls Documents pictures -----------List all Inside The Documents and Pictures
ls -l  --------------------------Gives a little bit more information
ls -lt --------------------------Give list with Modification Time
ls --help -----------------------List Help commands
```


__Searching Files__
```console
find /root -name imran--------------find files/dir in root with name imran.
find /root/imxx -name *.py ---------find all the files/dir with .py extension in /root/imxx directory.
```


			



__Controlling Processes__

```console
gedit
ps-------------------Show Running Processe
Jobs ----------------Show Running Jobs
gedit & -------------Starts Job without Keeping terminal in Listning and Gives Pid
bg %1 --------------Resume a Paused Programm
kill 2973 ----------Kill Process with pID 2973
killall gedit ------Kill all gedit processes
pstree --------------Give a Relatioship Grid of all the processes
xload ---------------Load of Your system 
```


__History__
```console
history --------------Shows History COmmand
hostory | less -------show less History
!! -------------------Execute The last Command
TAB TAB TAB -------------------Autocomplete Commands
```


__Creat Your Own Commands:__
```console
alias imran'service apache2 start'  ------Creat Command 'imran' To start apache 2
unalias imran -----------------------------Delete The Alias.
\aliased_commad----------------------------Returns Back Original Command.
	eg alias clear'ls -l' ------------Clear commands with list the files
		\clear 		-----------this time it clears The Screen
```

__Type of Commands__
```console
type command --------------Show me which type of Commands is it
	type ls
	type cd
which ls ------------------Found command
aprapos nmap --------------Search manual page for nmap
whatis ls ----------------What is ls
```


__File Modulation__
```console

file file.* ---------------show file type
wc file.txt --------------print line count, Bite count, and Word Count
wc file.txt -w -------------print no of words in file
wc file.txt -l ------------Print no. of line in File
wc file.txt -c ------------Print no of bites in File
```



__Using Pipes -[ | ]-__
```console
ls Desktop | sort
ls Desktop |less
ls Desktop | wc -l 
ls /usr | sort | wc -l
ls /usr /usr/bin | sort | wc -l 
```



__Pipes With Grep__
```console
ls Desktop |sort|grep zip  ------------------Show Text in ls with zip
ls Desktop | head -n 5     ------------------Show first five line of Output
```



__ACCESS__
```console
su -    --------------Create New Login Session for User ROOT
su -c 'ls Desktop' ---Execute only one commands donot create login session
```



__using Echo__
```console
echo imran
echo "imran"
echo * 
echo D*
echo *D
echo [[:upper:]]* --------Show Everthing That starts with Upper Case.
echo *[[:lower:]] --------Show Everything That ends with Lowercase.
echo /usr/*      ----------Show Availabe paths
echo .*          ----------Show all Hidden Files
ls -d .[!.]*     ----------Show All Hidden Files in Presentable Way.
echo ~           ----------Show You Current User name
echo ~root	------------Show Current Usernames HomeDir
```






__Using Echo For Maths__
```console
echo $((5+7)) -------------Add 5+712
echo $(($((5+2)) *3 )) -----Add 5+7 * 7 21
```



__Using History__

```console
History is Stored into .bashistory and Stores last 500 Commands
history | less ----------Show History last 10 Commands
!4              --------Execute commands number in History
Ctrl+r  ----------------Search and Exe in history
Ctrl+P -----------------Show Previous Commands one by one
Ctrl+n -----------------Show Next Commands one by one
!!      --------------Execute Last Command
```



__Using Permissions:__
```console
id ---------Show My Identity
ls -l ------Check Permissions to list of files and Filders
	- regular File
	c character special file
	l symbolic file
	d directory
	- Simple Regular file
 ```
 
 
__Changing Permissions:__
```console
0	------------ 000  ---
3	------------ 011  -wx
7	-------------111  rwx
6 	-------------110  rw-

chmod 000 imx.txt -------change mode to -- -- --
chmod 777 imx.txt -------Change mode to rwx-rwx-rwx
```

__Processes__
```console
ps ------------show current Processes
ps x ---------Show All Processe Running
ps aux --------Show Processe with extra Information
top -----------Give a Detailed View of Your Processes
```



__input/output__
```console
ls -l /usr/bin > imran.txt ----------send ls -l /usr/bin output to imran.txt
ls -l >>imran.txt --------------------Send ls -l to imran text with overight.
cat > imran.txt heyy -----------------Write a Data heyy to imran.txt
```

__WildCards__
```console
*	------------Match Any Charters with Your Query
?	------------Match Any Single Char
[abc]   ------------Mathc Set Of Charters
[!abc]  ------------Match Set of Charter Except abc
cat i*  ------------cat all file starting with i
cat im? ------------cat all files starts with im and has one more char like imu imx ims
```




