## A Light Script For You To Setup Shadowsocks-libev Server with High-Speed Connections

## Twist Features
- **Fast, Secured and Stable Connections**
- Supported **IPv4 & IPv6** Environment and Connections
- **Optimised Performance** Using Google BBR TCP Controler and Supported UDP Port
- **One-key Installation** and One-key Setup on your Devices

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
Please make sure that Your Server was able to **Connect to the Internet And Opened these Ports** below,It required by Shadowsocks-libev Services
```port
UDP 443
TCP 443
```

## Setup Shadowsocks-libev for Connect on your Devices
It is Required a Shadowsocks Client on Your Device for Manually Set up or Use URL-Scheme

## Author
<a href="https://github.com/Unbinilium" target="_blank">Unbinilium</a> --  This Project is Using OpenSource Software <a href="https://github.com/shadowsocks/shadowsocks-libev" target="_blank">Shadowsocks-libev</a> and <a href="https://github.com/jedisct1/libsodium" target="_blank">Libsodium</a>.
