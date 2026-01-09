# Common Terms

## VPN
A virtual private network (VPN) allows us to connect to a private (internal) network and access hosts and resources as if we were directly connected to the target private network. It is a secured communications channel over shared public networks to connect to a private network 


Connect to VPN with OpenVPN
```
sudo openvpn user.ovpn
Verify : `ifconfig` and see if `tun` adapter
```

`netstat -rn` shows networks accessible

## Shell

the shell is a program that takes input from the user via the keyboard and passes these commands to the operating system to perform a specific function.

## Port 
Ports are virtual points where network connections begin and end. They are software-based and managed by the host operating system

- TCP and UDP
The Consentual Photos vs Unsolicited Dick Pics
- Common Ports cheat sheet [1](https://www.stationx.net/common-ports-cheat-sheet/) [2](https://web.archive.org/web/20240315102711/https://packetlife.net/media/library/23/common-ports.pdf)
- [nmap default ports](https://nullsec.us/top-1-000-tcp-and-udp-ports-nmap-default/) 
- OWASP top 10 [2025](https://owasp.org/Top10/2025/)

## Tools 
- ssh : Secure Shell (SSH) is a network protocol that runs on port 22 by default and provides users such as system administrators a secure way to access a computer remotely. Example :  `ssh Bob@10.10.10.10`
- netcat : network utility for interacting with TCP/UDP ports. Ex: `netcat <ip> <port>`Banner Grabbing, and can help identify what service is running on a particular port.
-  socat: which has a few features that netcat does not support, like forwarding ports and connecting to serial devices.
-  tmux : Terminal multiplexers, expanding a standard Linux terminal's features, like having multiple windows within one terminal and jumping between them
- Vim : the one with (Esc -> :q!)
- nmap : Maps out the ports available for communication on a target device 
-  