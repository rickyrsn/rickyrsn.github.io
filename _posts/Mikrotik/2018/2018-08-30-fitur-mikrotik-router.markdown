---
layout: post
title:  "Fitur Mikrotik Router"
date:   2018-08-30 15:30:00 +0700
---
### Penanganan Protokol TCP/IP
* Firewall and NAT – stateful packet filtering; Peer-to-Peer protocol filtering; source and destination NAT; classification by source MAC, IP addresses, ports, protocols, protocol options, interfaces, internal marks, content, matching frequency
* Routing – Static routing; Equal cost multi-path routing; Policy based routing (classification by source and destination addresses and/or by firewall mark); RIP v1 / v2, OSPF v2, BGP v4
* Data Rate Management – per IP / protocol / subnet / port / firewall mark; HTB, PCQ, RED, SFQ, byte limited queue, packet limited queue; hierarchical limitation, CIR, MIR, contention ratios, dynamic client rate equalizing (PCQ)
* HotSpot – HotSpot Gateway with RADIUS authentication/accounting; data rate limitation; traffic quota; real-time status information; walled-garden; customized HTML login pages; iPass support; SSL secure authentication
* Point-to-Point tunneling protocols – PPTP, PPPoE and L2TP Access Concentrators and clients; PAP, CHAP, MSCHAPv1 and MSCHAPv2 authentication protocols; RADIUS authentication and accounting; MPPE encryption; compression for PPPoE; data rate limitation; PPPoE dial on demand
* Simple tunnels – IPIP tunnels, EoIP (Ethernet over IP)
* IPsec – IP security AH and ESP protocols; Diffie-Hellman groups 1,2,5; MD5 and SHA1 hashing algorithms; DES, 3DES, AES-128, AES-192, AES-256 encryption algorithms; Perfect Forwarding Secresy (PFS) groups 1,2,5
* Web proxy – FTP, HTTP and HTTPS caching proxy server; transparent HTTP caching proxy; SOCKS protocol support; support for caching on a separate drive; access control lists; caching lists; parent proxy support
* Caching DNS client – name resolving for local use; Dynamic DNS Client; local DNS cache with static entries
* DHCP – DHCP server per interface; DHCP relay; DHCP client; multiple DHCP networks; static and dynamic DHCP leases
Universal Client – Transparent address translation not depending on the client’s setup
* VRRP – VRRP protocol for high availability
* UPnP – Universal Plug-and-Play support
* NTP – Network Time Protocol server and client; synchronization with GPS system
* Monitoring/Accounting – IP traffic accounting, firewall actions logging
* SNMP – read-only access
* M3P – MikroTik Packet Packer Protocol for Wireless links and Ethernet
* MNDP – MikroTik Neighbor Discovery Protocol; also supports Cisco Discovery Protocol (CDP)
* Tools – ping; traceroute; bandwidth test; ping flood; telnet; SSH; packet sniffer

### Layer 2 Connectivity

* Wireless – IEEE802.11a/b/g wireless client and Access Point; Wireless Distribution System (WDS) support; virtual AP; 40 and 104 bit WEP; access control list; authentication on RADIUS server; roaming (for wireless client); Access Point bridging
* Bridge – spanning tree protocol; multiple bridge interfaces; bridge firewalling
* VLAN – IEEE802.1q Virtual LAN support on Ethernet and WLAN links; multiple VLANs; VLAN bridging
* Synchronous – V.35, V.24, E1/T1, X.21, DS3 (T3) media types; sync-PPP, Cisco HDLC, Frame Relay line protocols; ANSI-617d (ANDI or annex D) and Q933a (CCITT or annex A) Frame Relay LMI types
* Asynchronous – serial PPP dial-in / dial-out; PAP, CHAP, MSCHAPv1 and MSCHAPv2 authentication protocols; RADIUS authentication and accounting; onboard serial ports; modem pool with up to 128 ports; dial on demand
* ISDN – ISDN dial-in / dial-out; PAP, CHAP, MSCHAPv1 and MSCHAPv2 authentication protocols; RADIUS authentication and accounting; 128K bundle support; Cisco HDLC, x75i, x75ui, x75bui line protocols; dial on demand
* SDSL – Single-line DSL support; line termination and network termination modes

### Hardware requirements
* CPU and motherboard – advanced 4th generation (core frequency 100MHz or more), 5th generation (Intel Pentium, Cyrix 6X86, AMD K5 or comparable) or newer uniprocessor Intel IA-32 (i386) compatible (multiple processors are not supported)
* RAM – minimum 48 MB, maximum 1 GB; 64 MB or more recommended
* Hard Drive/Flash – standard ATA interface controller and drive (SCSI and USB controllers and drives are not supported; RAID controllers that require additional drivers are not supported) with minimum of 64 MB space

### Hardware needed for installation time only
> Depending on installation method chosen the router must have the following hardware:

* Floppy-based installation – standard AT floppy controller and 3.5” disk drive connected as the first floppy disk drive (A); AT, PS/2 or USB keyboard; VGA-compatible video controller card and monitor
* CD-based installation – standard ATA/ATAPI interface controller and CD drive supporting “El Torito” bootable CDs (you might need also to check if the router’s BIOS supports booting from this type of media); AT, PS/2 or USB keyboard; VGA-compatible video controller card and monitor
* Floppy-based network installation – standard AT floppy controller and 3.5” disk drive connected as the first floppy disk drive (A); PCI Ethernet network interface card supported by MikroTik RouterOS (see the Device Driver List for the list)
* Full network-based installation – PCI Ethernet network interface card supported by MikroTik RouterOS (see the Device Driver List for the list) with PXE or EtherBoot extension booting ROM (you might need also to check if the router’s BIOS supports booting from network)

### Configuration Possibilities
> RouterOS provides powerful command-line configuration interface. You can also manage the router through WinBox – the easy-to-use remote configuration GUI for Windows -, which provides all the benefits of the command-line interface, without the actual “command-line”, which may scare novice users. 

Major features:
* Clean and consistent user interface
* Runtime configuration and monitoring
* Multiple connections
* User policies
* Action history, undo/redo actions
* Safe mode operation
* Scripts can be scheduled for executing at certain times, periodically, or on events. All command-line commands are supported in scripts

When router is not configured, there are only two ways to configure it:
* Local terminal console – AT, PS/2 or USB keyboard and VGA-compatible video controller card with monitor
* Serial console – First RS232 asynchronous serial port (usually, onboard port marked as COM1), which is by default set to 9600bit/s, 8 data bits, 1 stop bit, no parity

After the router is configured, it may be managed through the following interfaces:
* Local teminal console – AT, PS/2 or USB keyboard and VGA-compatible video controller card with monitor
* Serial console – any (you may choose any one; the first, also known as COM1, is used by default) RS232 asynchronous serial port, which is by default set to 9600bit/s, 8 data bits, 1 stop bit, no parity
* Telnet – telnet server is running on 23 TCP port by default
* SSH – SSH (secure shell) server is running on 22 TCP port by default (available only if security package is installed)
* MAC Telnet – MikroTik MAC Telnet potocol server is by default enabled on all Ethernet-like interfaces
* Winbox – Winbox is a RouterOS remote administration GUI for Windows, that use 3986 TCP port (or 3987 if security package is installed)
