## A Light Script For You To Setup Shadowsocks-libev Server with High-Speed Connections

## Twist Features
- **Fast, Secured and Stable Connections**
- **Multithreading** Support
- **TCP Fast Open** Support
- **Simple Obfs** Support
- **IPv4 & IPv6** Environment Supported and Connections
- **Optimised Performance** Using Google BBR TCP Controler and Supported UDP Transfer
- **High Security** Supported AEAD Auth & Encryption
- **Fine Compatibility** and Support Original Shadowsocks Client
- **One-key Installation** and One-key Setup on your Devices
- **SS Scheme & QRCode** Login Information Auto Generate 
- **Highly Concealed** Fake as a WebServer using Apache and Enabled Fail2ban to Ban Force Crackers

## Server Requirements
- Ubuntu 17.04(Zesty), 16.10(Yakkety), 16.04(Xenial)
- Debian 9(Stretch) and Debian 8(Jessie) 
- CentOS 6 and 7

## Set Up your Shadowsocks-libev Server
Please **Run Bash Command** Below on Your Server to **Install Twist**
```bash
sudo wget https://raw.githubusercontent.com/Unbinilium/Twist/master/twist -O twist.sh && chmod -x twist.sh && bash twist.sh
```

## Attention
Please make sure that Your Server was able to **Connect to the Internet And Opened these Inboard Ports** below,It required by Shadowsocks-libev Services. It will be Automatically Configured on Your Server but not on the Server Management Console
```port
UDP 443
TCP 443
```

## Custom
Change the Default Settings by Editing Twish before install, Manual of Shadowsocks-libev Configurations is at <a href="https://github.com/shadowsocks/shadowsocks/wiki/Configuration-via-Config-File" target="_blank">Shadowsocks-libev Wiki</a>
```TWIST
sudo nano twist.sh  #Edit the value below on 'function *config'
```
Edit Values in Value="**HERE**", Save and Run Twist after You have Confirmed it is Correct
```shadowsocksconfig
 PORT="443"                       #Server port
 LOACL="127.0.0.1"                #The address your local listens
 LOCALPORT="1080"                 #Local port
 PASSWORD=""                      #Password used for encryption, auto generate if left free 
 TIMEOUT="600"                    #Drop connections if it not using in seconds
 METHOD="chacha20-ietf-poly1305"  #Encryption, AEAD is better than OTA
 OBFS="tls"                       #Obfs method
 OBFSHOST="github.com"            #Obfs host
 WORKERS="1024"                   #Workers using, larger provides faster speed but less memory
 BBR="enable"                     #Google BBR for low delay network to get faster speed
 FWS="enable"                     #Fake as a apache web server for concealing(Turn off it if running a Web service on your server)
 ABB="enable"                     #Uses Fail2ban to ban force crackers
```

## Simple Obfs
Here is the Deafult Configuration of Simple Obfs, Simple Obfs will not be Running without Configure it on Your Clients Manually. And You Can also Use Shadowsocks without Set Up Simple Obfs on Your Clients. If You Use Schemes or QR Code Configurations on Your Clients, Simple Obfs will not be Configured
```Simple-Obfs
OBFS="tls"
OBFSHOST="github.com"
```

## Check and Change Shadowsocks-libev Status
- Check If Shadowsocks-libev is Running on Your Server
```shell
/etc/init.d/shadowsocks status
```
- Change the Status of Shadowsocks-libev by these Command
```shell
/etc/init.d/shadowsocks start    #Start Shadowsocks Service
/etc/init.d/shadowsocks stop     #Stop Shadowsocks Service
/etc/init.d/shadowsocks restart  #Restart Shadowsocks Service
```

## Setup Shadowsocks-libev for Connect on your Devices
It is Required a Shadowsocks Client on Your Device for Manually Set up or Use URL-Scheme & QRCode in Shadowsocks Client Apps

## Update Twist
Please **Run Bash Command** to Update Twist While You Once Downloaded it on Your Server
```bash
sudo twist.sh update
```
or Update by Download the Install Script Again
```bash
sudo wget https://raw.githubusercontent.com/Unbinilium/Twist/master/twist -O twist.sh && chmod -x twist.sh && bash twist.sh update
```

## Uninstall Twist
Please **Run Bash Command** to Uninstall Twist While You Once Downloaded it on Your Server
```bash
sudo twist.sh uninstall
```
or Uninstall by Download the Install Script Again
```bash
sudo wget https://raw.githubusercontent.com/Unbinilium/Twist/master/twist -O twist.sh && chmod -x twist.sh && bash twist.sh uninstall
```

## Author
<a href="https://github.com/Unbinilium" target="_blank">Unbinilium</a> --  This Project is Using OpenSource Software <a href="https://github.com/shadowsocks/shadowsocks-libev" target="_blank">Shadowsocks-libev</a> and <a href="https://github.com/jedisct1/libsodium" target="_blank">Libsodium</a>.
