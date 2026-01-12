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

---
# NMAP

This tools scans the network ports for a target. default behaviour is to check the top most common 1000 ports for TCP operations. 
`nmap <host:port>` means it will perform scan 
Sample output :
```
PORT    STATE SERVICE
21/tcp  open  ftp
22/tcp  open  ssh
80/tcp  open  http
139/tcp open  netbios-ssn
445/tcp open  microsoft-ds
```

PORT -> port number and connection type  
STATE -> can have values open, filtered(allowed only through some kind of a firewall) etc.  
SERVICE -> name of the service running on the port 


`-sC` : run scripts to try to get more information about the target   
`--script <script name>` : run a specific script
`-sV` : perform a version scan  
`-p<port>` : scan a specific port 
`-p-` : scan all the 65535 TCP ports  

## Banner Grabbing 
Often a service will look to identify itself by displaying a banner once a connection is initiated
Using NMAP : `nmap -sV --script banner -p<port> <host>`  
Using netcat : `nc -nv <host> <port>`  


# Metasploit Framework 

- Contains built-in exploits for publically available vulnerabilities 
- Running reconnaissance scripts to enumerate remote hosts and compromised targets
- Verification scripts to test the existence of a vulnerability without actually compromising the target
- Meterpreter, which is a great tool to connect to shells and run commands on the compromised targets
- Many post-exploitation and pivoting tools

after searching for exploits you can `use` it.
`options` shows multiple option available to exploit. Required parameters can be filled depending on the target host.
`exploit` or `run` runs according to parameters configured. 
