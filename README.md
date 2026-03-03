# Palo Alto VM-Series Firewall Lab Series

---

## Overview

This repository documents hands-on laboratory implementations using the **Palo Alto VM-Series Firewall (PAN-OS 11.2)** deployed in a VMware Workstation environment.

The objective of this lab series is to build practical, implementation-level experience in enterprise firewall deployment and network security configuration. The labs demonstrate end-to-end setup, policy enforcement, traffic validation, and monitoring in a Layer 3 deployment model.

This project reflects applied knowledge of:

- Firewall architecture  
- Network segmentation  
- Dynamic Source NAT (PAT)  
- Security policy enforcement  
- Traffic monitoring and App-ID validation  

---

## Lab Environment

| Component | Details |
|-----------|----------|
| Firewall | Palo Alto VM-Series |
| PAN-OS Version | 11.2.0 |
| Virtualization Platform | VMware Workstation |
| Client OS | Ubuntu 24.04 LTS |
| Deployment Mode | Layer 3 |

---

## Network Topology

Ubuntu VM → Palo Alto Firewall → Internet  

The Ubuntu client resides in the **Trust** zone and accesses the internet through the firewall’s **Untrust** interface using dynamic Source NAT (PAT). Traffic is routed via a default route (`0.0.0.0/0`) configured in the virtual router.

---

## IP Addressing Structure

| Device | Interface | IP Address | Zone |
|--------|------------|------------|------|
| Ubuntu VM | eth0 | 192.168.x.x | Trust |
| Firewall (LAN) | ethernet1/2 | 192.168.x.x | Trust |
| Firewall (WAN) | ethernet1/1 | DHCP | Untrust |
| Management | MGT | 192.168.x.x | Management |

---

## Labs Included

- Initial Firewall Setup and Management Configuration  
- Layer 3 Interface Configuration (WAN and LAN)  
- Security Zone Configuration  
- Virtual Router and Static Default Route Configuration  
- Source NAT Policy (Dynamic IP and Port)  
- Security Policy Rule Creation  
- Connectivity Verification (ICMP Testing)  
- Internet Access Validation  
- Traffic Log Analysis and App-ID Verification  

---

## Technical Skills Demonstrated

- Palo Alto VM-Series deployment  
- Layer 3 interface configuration  
- Zone-based segmentation  
- Static routing configuration  
- Dynamic Source NAT (PAT)  
- Security policy rule management  
- App-ID traffic identification  
- Traffic log validation  
- End-to-end troubleshooting  

---

## Validation Performed

- Verified ICMP connectivity between Ubuntu and firewall  
- Confirmed outbound internet access via NAT  
- Validated NAT translation in traffic logs  
- Confirmed App-ID detection  
- Verified security rule match and action  

---

## Future Enhancements

- Application-based blocking using App-ID  
- URL Filtering configuration  
- DoS Protection policy setup  
- SSL Decryption implementation  
- Threat Prevention profiles  
- Zone Protection profiles  

---

## Author

**Vishesh Dixit**  
Network Security Enthusiast | Aspiring Firewall Engineer
