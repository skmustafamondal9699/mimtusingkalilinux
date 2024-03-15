# mimtusingkalilinux
GitHub Documentation for Ettercap Configuration
Introduction

This document provides guidance on configuring Ettercap for network monitoring and ARP poisoning. Ettercap is a comprehensive suite for man-in-the-middle attacks on LAN. It features sniffing of live connections, content filtering on the fly, and many other interesting tricks.
System Configuration

Ensure your system meets the following requirements:

    Operating System: Linux
    Ethernet Interface: eth0
    IPv4 Address: 10.0.2.15/255.255.255.0
    MAC Address: 08:00:27:D7:DA:60
    IPv6 Address: fe80::a00:27ff:fed7:da60/64

SSL Dissection

For SSL dissection to function properly, ensure you have a valid redir_command_on script in the etter.conf file. Without this, Ettercap might not work correctly.
IPv6 Configuration

Verify that /proc/sys/net/ipv6/conf/eth0/use_tempaddr is set to 0. This ensures proper functionality of Ettercap in handling IPv6 traffic.
Privileges

Ettercap drops privileges to the effective user ID (EUID) 65534 and effective group ID (EGID) 65534 for security reasons.
Plugins and Protocol Dissectors

    Plugins: 34
    Protocol Dissectors: 42

Ports Monitored

Ettercap monitors 57 ports for network traffic.
Fingerprints and Services

    MAC Vendor Fingerprint: 28230
    TCP OS Fingerprint: 1766
    Known Services: 2182

Lua Scripts

If Lua scripts are required for your use case, ensure to specify them for Ettercap to load.
Unified Sniffing

Ettercap initiates unified sniffing upon startup.
ARP Poisoning

Ettercap performs ARP poisoning for intercepting traffic. Below are the ARP poisoning victims:
Group 1

    IP Address: 10.0.2.4
    MAC Address: 52:54:00:12:35:04

Group 2

    IP Address: 10.0.2.2
    MAC Address: 52:54:00:12:35:02

Target Selection

Ettercap adds hosts to target lists for interception. For instance:

    Host 10.0.2.4 added to TARGET1
    Host 10.0.2.2 added to TARGET2

Scanning

Ettercap performs scanning to identify hosts on the network. It randomizes 255 hosts for scanning and then scans the entire netmask for 255 hosts.
Conclusion

This documentation covers essential configuration details and functionalities of Ettercap for network monitoring and ARP poisoning. Ensure to customize the configuration according to your specific requirements and security considerations.
