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
- Debian 9(Stretch) &  8(Jessie) 
- Cent OS 7 & 6
- Red Hat 7 & 6
- Fedora 26 & 25
- Arch Linux

## Set Up your Shadowsocks-libev Server
Please **Run Bash Command** Below on Your Server to **Install Twist**
```bash
sudo wget https://raw.githubusercontent.com/Unbinilium/Twist/master/twist -O twist.sh && chmod -x twist.sh && bash twist.sh
```

## Attention
Please make sure that Your Server was able to **Connect to the Internet And Opened these Inboard Ports** below,It required by Shadowsocks-libev Services. It will be Automatically Configured on Your Server but not on the Server Management Console
```txt
UDP 443
TCP 443
```

## Custom
Change the Default Settings by Editing Twish before install, Manual of Shadowsocks-libev Configurations is at <a href="https://github.com/shadowsocks/shadowsocks/wiki/Configuration-via-Config-File" target="_blank">Shadowsocks-libev Wiki</a>
```bash
sudo nano twist.sh       # Edit the value below on 'function *config'
```
If you have already Installed Twist, Try this by Editing Shadowsocks Config File that Installed on your Server Instead the Install Script 
```bash
sudo twistconfig custom  # Edit the value in json format
```
Edit Values in Value="**HERE**", Save and Run Twist after You have Confirmed it is Correct
```txt
 PORT="443"                       # Server port
 LOACL="127.0.0.1"                # The address that server listens
 LOCALPORT="1080"                 # Local port of loacl address that server listens
 PASSWORD=""                      # Password used for encryption, auto generate if left free 
 DNS="8.8.8.8"                    # Default DNS server address of Google Public DNS
 TIMEOUT="600"                    # Drop connections if it not using in seconds
 METHOD="chacha20-ietf-poly1305"  # Encryption, AEAD is better than OTA
 OBFS="tls"                       # Obfs method using tls or http
 OBFSHOST="mzstatic.com"          # Obfs host address
 WORKERS="1024"                   # Workers using, larger provides faster speed but less memory
 BBR="enable"                     # Google BBR for low delay network to get faster speed
 FWS="enable"                     # Fake as a apache web server for concealing
 ABB="enable"                     # Uses Fail2ban to ban force crackers
```

## Simple Obfs
Here is the Deafult Configuration of Simple Obfs, Simple Obfs will not be Running without Configure it on Your Clients Manually. And You Can also Use Shadowsocks without Set Up Simple Obfs on Your Clients. If You Use Schemes or QR Code Configurations on Your Clients, Simple Obfs will not be Configured
```txt
OBFS="tls"
OBFSHOST="mzstatic.com"
```

## Check and Change Shadowsocks-libev Status
- Check If Shadowsocks-libev is Running on Your Server
```bash
twistconfig status        # Check Shadowsocks status
```
- Change the Status of Shadowsocks-libev by these Command
```bash
sudo twistconfig start    # Start Shadowsocks Service
sudo twistconfig stop     # Stop Shadowsocks Service
sudo twistconfig restart  # Restart Shadowsocks Service
```

## Setup Shadowsocks-libev for Connect on your Devices
It is Required a Shadowsocks Client on Your Device for Manually Set up or Use URL-Scheme & QRCode in Shadowsocks Client Apps

## Update Twist
Please **Run Bash Command** to Update Twist While You Once Downloaded it on Your Server
```bash
sudo twistconfig update
```

## Uninstall Twist
Please **Run Bash Command** to Uninstall Twist While You Once Downloaded it on Your Server
```bash
sudo twistconfig uninstall
```

## Author
<a href="https://github.com/Unbinilium" target="_blank">Unbinilium</a> --  This Script is Using OpenSource Software <a href="https://github.com/shadowsocks/shadowsocks-libev" target="_blank">Shadowsocks-libev</a>
