# Networking Commands — Troubleshooting Notes

## Description

This document summarizes my understanding of common networking commands used for troubleshooting and analyzing network connectivity, DNS resolution, and traffic.

---

## 1. Ping

**What I understood:**

The `ping` command is used to check whether a destination is reachable over the network. It sends ICMP packets to the destination and displays the response time. This helps identify connectivity problems and gives an idea of network latency.

---

## 2. Traceroute

**What I understood:**

The `traceroute` command shows the path taken by packets from my computer to the destination. It displays the different network hops (routers) that the packets pass through and helps identify where delays or connectivity problems may occur.

---

## 3. Netstat

**What I understood:**

The `netstat` command displays information about network connections and network-related activity on my computer. It can be used to view active connections, listening ports, and the network addresses involved.

---

## 4. Telnet / Netcat

**What I understood:**

The Telnet command can be used to test connectivity to a specific network port. Since Telnet was not available by default on my Mac, I used `nc` (Netcat) as an equivalent to test whether a connection to Google's port 80 could be established.

---

## 5. Tcpdump

**What I understood:**

The `tcpdump` command captures and displays network packets traveling through a network interface. It can be used to observe and analyze network traffic, including information about source, destination, protocols, and packets.

---

## 6. Nslookup

**What I understood:**

The `nslookup` command is used to query DNS and find the IP address associated with a domain name. For example, it can resolve `google.com` to one of Google's IP addresses.

---

## 7. Dig

**What I understood:**

The `dig` command is used to perform detailed DNS queries. It provides more information about the DNS response, including the records returned, such as the IP address associated with a domain.

---

## 8. Curl

**What I understood:**

The `curl` command is used to communicate with a web server using protocols such as HTTP and HTTPS. Using `curl -I` allows me to retrieve the HTTP response headers and verify whether the web server can be reached successfully.

---

## 9. ARP

**What I understood:**

The `arp` command displays the ARP table, which contains mappings between IP addresses and MAC addresses of devices known on the local network. This helps understand how devices are identified and communicated with within the local network.

---

## 10. Network Configuration — macOS Equivalent

**What I understood:**

The original resource uses `systemctl` to check network services, but `systemctl` is a Linux command and is not available on macOS. I used `networksetup -getinfo Wi-Fi` instead to view the network configuration of my Wi-Fi connection, such as the IP address, subnet mask, router, and other network information.

---

## Conclusion

**What I understood:**

Through these commands, I learned how different networking tools can be used to troubleshoot and understand network communication. `ping` checks connectivity, `traceroute` shows the path taken by packets, DNS tools resolve domain names, `tcpdump` helps analyze packets, and `arp` shows local IP-to-MAC mappings. Together, these commands provide a practical way to understand and troubleshoot network connectivity.