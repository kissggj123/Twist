## A Light Script For You To Setup Shadowsocks-libev Server with High-Speed Connections and Powerful Features

## Twist Features
- **Fast, Secured and Stable Connections by Shadowsocks**
- **Multithreading** Support
- **TCP Fast Open** Support
- **Simple Obfs** Support
- **IPv4 & IPv6** Support
- **Optimised Performance** Using Google BBR TCP Controler and Support UDP Transfer
- **High Security** Support AEAD Cipher & Encryption
- **Newest Features** Support TLS Obfs & Obfs URI in simple-obfs
- **Fine Compatibility** Support Various Shadowsocks Based Clients
- **One-key Installation** and QRCode Scan to Connect on Your Devices
- **SS Scheme & QRCode** Basic Connect Information Auto Generate and Shows Full Connect Information
- **Highly Concealed** It is able to Fake as a Web Server Using Apache and Enabled Fail2ban to Ban Force Crackers

## Server Requirements
- Ubuntu 18.04(Bionic Beaver), 17.10(Artful Aardvark), 17.04(Zesty), 16.10(Yakkety), 16.04(Xenial)
- Debian 9(Stretch), 8(Jessie) 
- Cent OS 7, 6
- Red Hat 7, 6
- Fedora 26, 25
- Arch Linux
- Raspbian

## Set Up your Shadowsocks-libev Server
Please **Run Command** below on your server to **Install Twist**
```bash
sudo wget https://raw.githubusercontent.com/Unbinilium/Twist/master/twist -O twist.sh && chmod -x twist.sh && bash twist.sh
```

## Attention
Please make sure that your server was able to **Connect to the Internet and Opened these Inboard & Outboard Ports** below. It required by shadowsocks-libev services based on your configurations. And It will be automatically configured on your System Side but will not be on the Server Management Console
```txt
UDP 443
TCP 443
```

## Custom
Change the default Configurations by editing Twish before install, the manual of shadowsocks-libev Configurations is at <a href="https://github.com/shadowsocks/shadowsocks/wiki/Configuration-via-Config-File" target="_blank">Shadowsocks-libev Wiki</a>
```bash
sudo nano twist.sh       # Edit the value below on 'function *config'
```
If you have already Installed Twist, try this by editing Shadowsocks Config File that Installed on your Server Instead the Install Script 
```bash
sudo twist custom  # Edit the value in json format
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
 OBFS="tls"                       # Obfs method using tls or http
 OBFSHOST="mzstatic.com"          # Obfs host address
 OBFSURI="/"                      # Obfs specify the client request path uri
 BBR="enable"                     # Google BBR for low delay network to get faster speed
 FWS="enable"                     # Fake as a apache web server for concealing
 ABB="enable"                     # Uses Fail2ban to ban force crackers
```

## Simple Obfs
Here is the deafult Configurations of Simple Obfs, Simple Obfs will not be run without configure it on your Clients Side manually. And You could use Shadowsocks without set up Simple Obfs on your Clients. If you used the Schemes or QRCode Configurations to setup your Clients, Simple Obfs will not be Configured
```txt
OBFS="tls"
OBFSHOST="mzstatic.com"
OBFSURI="/"
```

## Check and Change Shadowsocks-libev Status
- Check If Shadowsocks-libev is running on your Server
```bash
twist status        # Check Shadowsocks Status
```
- Change the Status of Shadowsocks-libev by these Commands
```bash
sudo twist start    # Start Shadowsocks Service
sudo twist stop     # Stop Shadowsocks Service
sudo twist restart  # Restart Shadowsocks Service
```

## Setup Shadowsocks-libev for Connect on your Devices
It requires a Shadowsocks based Client on your Device and you need to manually set up or use the URL-Scheme or QRCode in Shadowsocks Clients

## Update Twist
Please **Run Command** to Update Twist
```bash
sudo twist update
```
You can also Update Twist automaticly by using ```crond``` Service
```bash
echo "0 0 1 * * root bash /usr/bin/twist update" >> /etc/crontab
```
The Command means **Twist will automaticly check updates on the first day of every month**


## Uninstall Twist
Please **Run Command** to Uninstall Twist
```bash
sudo twist uninstall
```

## Author
<a href="https://github.com/Unbinilium" target="_blank">Unbinilium</a> --  This Script is mainly using OpenSource Software <a href="https://github.com/shadowsocks/shadowsocks-libev" target="_blank">Shadowsocks-libev</a>
