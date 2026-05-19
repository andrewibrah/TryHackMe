#### Network Traffic Analysis (NTA) is a process that encompasses capturing, inspecting, and analyzing data as it flows in a network.

- Visibility and Understanding 
- Logs, Deep packet insepction and flow statistics.

Know what network traffic analysis is
Know what can be observed
Know how to observe network traffic
Know typical network traffic sources and flows

Based on DNS logs, we can retrieve the following information:

- Query and querytype
- Subdomain and top-level domain: We can check tools like abuseDB or VirusTotal to check if the domain is malicious
- Host IP: We can identify the system sending out the DNS queries
- Destination IP: We can use tools like AbuseIPDB(opens in new tab) or VirusTotal(opens in new tab) to verify if the IP is flagged as malicious
- Timestamp: We can build a timeline mapping out the different suspicious queries

*NOTE: hard to draw conclusion from DNS Logs alone*

# What is the name of the technique used to smuggle C2 commands via DNS?
>DNS tunneling

# We will use network traffic analysis to:

- Monitor network performance
- Check for abnormalities in the network. E.g., sudden performance peaks, slow network, etc
- Inspect the content of suspicious communication internally and externally. E.g., exfiltration via DNS, download of a malicious ZIP file over HTTP, lateral movement, etc

> From a SOC perspective
  - Detecting suspicious or malicious activity
  - Reconstructing attacks during incident response
  - Verifying and validating alerts

# TCP/IP Model
*Application*
- Application header information & application data itself (payload)
-  No application data FireWall filtering.

*Transport*
- Application data and header are segmented and encapsulated into smaller pieces
- Transport header, in most cases TCP or UDP
- Session Hijacking

*Internet*
- Segments are encapsulated into datagrams
- IP Header
- Fragmentation attacks

*Link*
- Datagrams are encapsulated into frames
- Link Header
- ARP poisoning

## TCP/IP Encapsulation

> Network Traffic Analysis lets you inspect and find threats in every byte and every layer of TCP/IP.

```
  TCP/IP Encapsulation — Data flows DOWN; headers are added at each layer
  ═══════════════════════════════════════════════════════════════════════════════

  APPLICATION LAYER
  ┌──────────────────────────────────────────────────────────────────────────┐
  │                        Application Header + Data                         │
  └──────────────────────────────────────────────────────────────────────────┘
                                       │
                                       ▼  (Transport layer wraps it)
  TRANSPORT LAYER
  ┌─────────────────────────┬────────────────────────────────────────────────┐
  │    Transport Header     │            Application Header + Data           │
  └─────────────────────────┴────────────────────────────────────────────────┘
                                       │
                                       ▼  (Internet layer wraps it)
  INTERNET LAYER
  ┌──────────────┬──────────────────────────┬──────────────────────────────┐
  │  IP Header   │     Transport Header     │    Application Header + Data │
  └──────────────┴──────────────────────────┴──────────────────────────────┘
                                       │
                                       ▼  (Link layer wraps it)
  LINK LAYER
  ┌───────────┬─────────────┬──────────────────────┬────────────────────────┐
  │Link Header│  IP Header  │   Transport Header   │ Application Header+Data│
  └───────────┴─────────────┴──────────────────────┴────────────────────────┘

  ★ Network Traffic Analysis lets you inspect threats at EVERY layer above.
```

# Look at the HTTP example in the task and answer the following question: What is the size of the ZIP attachment included in the HTTP response? 
>10485760

# Which attack do attackers use to try to evade an IDS?
>fragmentation

# What field in the TCP header can we use to detect session hijacking?
>sequence number

# Network Flows & Sources

A. Intermediary
B. Endpoint

North-South: Traffic that exits or enters the LAN and passes the firewall
East-West: Traffic that stays within the LAN (including LAN that extends to the cloud)

# Intermediary Sources
- Devices which traffic mostly passes.
- Firewalls, switches, web proxies, IDS, IPS, routers, access points, wireless LAN controllers, and many more
- IoI devices
- Routing protocols (EIGRP, OSPF, BGP). 
  > EIGRP and OSPF inside an organization’s
  > BGP route different networks on the internet.
- Management protocols (SNMP, PING)
- Supporting protocols (ARP, STP, DHCP)

# Endpoint Sources
- Devices where traffic originates and ends * take the bulk of the network bandwidth 
- Servers, hosts, IoT devices, printers, virtual machines, cloud resources, mobile phones, tablets, and many more.

# North - South Traffic 
- HTTPS, DNS, SSH, VPN, SMTP, RDP, and many more. 
- Two streams: ingress (inbound) and egress (outbound).

# East-West Traffic
- EW traffic stays within the corporate LAN, often monitored less.
- Attacker will often exploit different services internally to move laterally within the network
- EW Services: 
>Directory, Authentication & Identity Services
>File shares & print services
>Router, switching, and infrastructure services
>Application Communication
>Backup & Replication
>Monitoring & Management
 
# Which category of devices generates the most traffic in a network?
>endpoint

# Before an SMB session can be established, which service needs to be contacted first for authentication?
>kerberos

## What does TLS stand for?
>Transport Layer Security

**Network traffic analysis focuses on combining multiple sources of information, analyzing them, finding patterns, and using the results to inform actions**

# Information 
>Logs
>Full Packet Capture
>Network Statistics
