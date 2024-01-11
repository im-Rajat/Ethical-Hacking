# Ethical Hacking Basics


## What is MAC Address and How to change it

- MAC Address is a physical address specific to a device  
- Check MAC Address using ifconfig command in ether section

***ifconfig*** : This command lists all the interfaces

When in monotor mode Check MAC Address using ifconfig command in unspec section (First 6 between -, replace - with :)

**How to change MAC Address (To change wlan0 MAC Address) :-**

```
Ifconfig wlan0 down
Ifconfig wlan0 hw ether 00:11:22:33:44:55 (New MAC Address)
Ifconfig wlan0 upa
```

MAC Address will revert back to original when machine will restart

<hr>

## Wireless Modes (Managed and Monitor)

- Managed mode will capture only those packet which has our destination MAC Address.
- Monitor Mode can capture any packet within our range.

***iwconfig*** : To check mode

**How to change to Monitor Mode :-**

```
Ifconfig wlan0 down
Airmon-ng check kill
Iwconfig wlan0 mode monitor
Iwconfig wlan0 up
```

<hr>

## Sniffing Basics

**Packet Sniffing Basics**

```Airodump-ng mon0``` (mon0 can be wlan0, or anything)  
Above command will capture all packets within the range.

To sniff 5GHz band also  
```Airodump-ng --band a mon0``` (```--band abg``` (For both 2.4 and 5 GHZ network))

**Targetted Packet Sniffing**

```Airodump-ng --bssid 00:11:22:33:44:55 --channel 2 --write test mon0```

<hr>

