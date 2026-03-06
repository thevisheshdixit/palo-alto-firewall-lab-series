# Palo Alto VM-Series Firewall Lab Series

---

## Overview

This repository documents hands-on laboratory implementations using the **Palo Alto VM-Series Firewall (PAN-OS 11.2)** deployed in a **VMware Workstation virtual lab environment**.

The objective of this lab series is to build **practical, implementation-level experience in enterprise firewall deployment and network security configuration** using Palo Alto Next-Generation Firewall technologies.

The labs simulate a **real-world network architecture**, where a client system accesses the internet through a firewall that enforces security policies, performs NAT translation, identifies applications, and protects the network from potential threats.

This project serves as a **learning portfolio demonstrating practical firewall configuration, traffic inspection, and network security enforcement**.

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


                 Internet
                     |
                     |
             ethernet1/1 (Untrust)
             Palo Alto Firewall
             ethernet1/2 (Trust)
                     |
                     |
                 Ubuntu VM


The Ubuntu client resides in the **Trust zone** and sends traffic to the firewall through **ethernet1/2**.  
The firewall then forwards the traffic through **ethernet1/1 (Untrust)** to the internet using **Dynamic Source NAT (PAT)**.

All outbound traffic is routed using the **default route (0.0.0.0/0)** configured in the firewall's **virtual router**.

---

## IP Addressing Structure

| Device | Interface | IP Address | Zone |
|------|------|------|------|
| Ubuntu VM | eth0 | 192.168.x.x | Trust |
| Firewall (LAN) | ethernet1/2 | 192.168.x.x | Trust |
| Firewall (WAN) | ethernet1/1 | DHCP | Untrust |
| Management | MGT | 192.168.x.x | Management |

---

## Repository Structure

```
palo-alto-firewall-lab-series
│
├── Lab-01-Initial-Setup
│   ├── README.md
│   ├── Lab-01-Palo-Alto-Initial-Setup.pdf
│   └── screenshots
│
├── Lab-02-AppID-Control
│   ├── README.md
│   ├── Lab-02-AppID-Control.pdf
│   └── screenshots
│
├── Lab-03-DoS-Protection
│   ├── README.md
│   ├── Lab-03-DoS-Protection.pdf
│   └── screenshots
│
├── Lab-04-URL-Filtering
│   ├── README.md
│   ├── Palo-Alto-URL-Filtering.pdf
│   └── screenshots
│
└── README.md
```

Each lab folder contains:

- Step-by-step configuration documentation  
- Detailed explanation of the firewall feature  
- Validation screenshots  
- Lab report in PDF format  

---

## Labs Included

### 1. Initial Firewall Setup

This lab demonstrates the **initial deployment and base configuration of the Palo Alto VM-Series firewall**.

Configuration includes:

- Management interface configuration
- Initial CLI access
- Base system setup
- Interface activation

---

### 2. Layer 3 Network Configuration

Configured the firewall to operate in **Layer 3 mode**.

Tasks performed:

- LAN interface configuration
- WAN interface configuration
- Security zone creation (Trust / Untrust)
- Interface-to-zone mapping

---

### 3. Virtual Router & Routing

Configured routing inside the firewall.

Tasks performed:

- Virtual router creation
- Static default route configuration (`0.0.0.0/0`)
- Internet gateway routing

---

### 4. Source NAT Configuration

Implemented **Dynamic Source NAT (PAT)** to allow internal clients to access external networks.

Configuration includes:

- NAT policy creation
- Dynamic IP and Port translation
- Outbound traffic translation

---

### 5. Security Policy Implementation

Configured **zone-based firewall policies** to control traffic flow.

Tasks performed:

- Security policy rule creation
- Allow outbound internet traffic
- Policy rule validation

---

### 6. App-ID Based Application Control

Implemented **application-aware security policies** using Palo Alto **App-ID**.

Capabilities tested:

- Application identification
- Traffic classification
- Application-based policy enforcement
- Traffic log monitoring

---

### 7. URL Filtering

Configured **URL filtering policies** to restrict access to specific websites.

Blocked websites:

- YouTube
- Facebook

Validation was performed by attempting access from the Ubuntu client and verifying **URL filtering logs**.

---

### 8. DoS Protection

Configured **Denial-of-Service (DoS) protection policies** to protect the firewall and network resources.

Configured features:

- DoS protection profiles
- Flood protection rules
- Traffic monitoring
- Policy enforcement validation

---

## Technical Skills Demonstrated

This lab series demonstrates practical experience with:

- Palo Alto VM-Series Firewall deployment
- Layer 3 interface configuration
- Security zone segmentation
- Virtual router configuration
- Static routing
- Source NAT (PAT)
- Security policy rule creation
- Application identification using App-ID
- URL filtering configuration
- DoS protection configuration
- Traffic log monitoring
- Firewall troubleshooting

---

## Validation Performed

The following tests were performed during the labs:

- Verified ICMP connectivity between Ubuntu and firewall
- Confirmed outbound internet access through NAT
- Verified NAT translation in traffic logs
- Confirmed App-ID detection for applications
- Verified security rule matches
- Confirmed URL filtering blocking behavior
- Validated DoS protection policy enforcement

---

## Future Enhancements

Planned labs for further learning include:

- SSL Decryption
- Threat Prevention Profiles
- Antivirus & Anti-Spyware Profiles
- File Blocking
- WildFire Integration
- Zone Protection Profiles
- GlobalProtect VPN
- Advanced Application Control

---

## Author

**Vishesh Dixit**

Network Security Enthusiast | Aspiring Firewall Engineer

Focused on building **hands-on expertise in Next-Generation Firewall technologies, enterprise network security, and practical lab-based learning**.
