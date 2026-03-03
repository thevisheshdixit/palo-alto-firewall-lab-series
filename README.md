Palo Alto VM-Series Firewall Lab Series
Overview

This repository documents hands-on laboratory implementations using the Palo Alto VM-Series Firewall (PAN-OS 11.2) deployed in a VMware Workstation environment.

The objective of this lab series is to build practical, implementation-level experience in enterprise firewall deployment and network security configuration. The labs demonstrate end-to-end setup, policy enforcement, traffic validation, and monitoring in a Layer 3 deployment model.

This project reflects applied knowledge of firewall architecture, network segmentation, NAT, and security policy management.

Lab Environment
Component	Details
Firewall	Palo Alto VM-Series
PAN-OS Version	11.2.0
Virtualization Platform	VMware Workstation
Client OS	Ubuntu 24.04 LTS
Deployment Mode	Layer 3
Network Topology

Ubuntu VM → Palo Alto Firewall → Internet

The Ubuntu client resides in the Trust zone and accesses the internet through the firewall’s Untrust interface using dynamic source NAT (PAT). Traffic is routed via a default route (0.0.0.0/0) configured in the virtual router.

Labs Included

Initial Firewall Setup and Management Configuration

Layer 3 Interface Configuration (WAN and LAN)

Security Zone Configuration

Virtual Router and Static Default Route Configuration

Source NAT Policy (Dynamic IP and Port)

Security Policy Rule Creation

Connectivity Verification (ICMP Testing)

Internet Access Validation

Traffic Log Analysis and App-ID Verification

Technical Skills Demonstrated

Deployment of Palo Alto VM-Series Firewall

Layer 3 interface configuration and zone-based segmentation

Virtual routing and default route implementation

Dynamic Source NAT (PAT) configuration

Security policy rule management

App-ID based traffic identification

Traffic log analysis and monitoring

End-to-end connectivity troubleshooting

Future Lab Enhancements

Planned expansions to this lab series include:

Application-based traffic blocking using App-ID

URL Filtering implementation

DoS Protection configuration

SSL Decryption setup

Threat Prevention Profile configuration

Zone Protection Profiles

These additions will further simulate enterprise-grade security architecture.

Author

Vishesh Dixit
Network Security Enthusiast | Aspiring Firewall Engineer
