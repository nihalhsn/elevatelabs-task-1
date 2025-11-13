**Objective:**

To scan my local network using **Nmap** in Kali Linux, identify open ports, analyze services, check security risks, and observe packets using **Wireshark**.



**My Network Details**

My IP: 172.20.10.2

Subnet: /28

Network Range: 172.20.10.0 – 172.20.10.15

Hosts found: 4



Commands I Used

sudo nmap -sS 172.20.10.0/28

sudo nmap -sS 172.20.10.0/28 -oN scan\_result.txt



Nmap Results

Host: 172.20.10.1

Open ports:

21/tcp open ftp

53/tcp open domain

49152/tcp open unknown

62078/tcp open iphone-sync



Host: 172.20.10.2

All ports closed



Host: 172.20.10.3

All ports closed



Host: 172.20.10.10

All ports filtered



Explanation of Open Ports

Port 21: FTP, insecure because it sends passwords in plain text.

Port 53: DNS service, can be used for DNS spoofing.

Port 49152: Dynamic UPnP port, risk of unauthorized access.

Port 62078: iPhone sync service, can allow pairing attacks if hotspot is weak.



Wireshark Observations

I saw SYN packets from Kali.

SYN/ACK packets from open ports on 172.20.10.1.

RST packets from closed ports.

Filtered ports showed no response.

DNS packets seen on port 53.

iPhone sync packets on port 62078.



Security Risks Identified

FTP exposes credentials.

DNS can be spoofed.

UPnP/dynamic ports can be exploited.

iPhone sync service available to hotspot users.



How to Fix Risks

Disable FTP.

Disable UPnP.

Use a strong hotspot password.

Turn off hotspot when not using it.

Update device regularly.



Files Included

scan_result.txt

wireshark_notes.txt

screenshots folder

