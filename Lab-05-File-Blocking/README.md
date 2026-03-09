# Palo Alto Firewall – File Blocking Lab

## Overview
This lab demonstrates how to configure a **File Blocking Security Profile** on a Palo Alto VM-Series Firewall to prevent users from downloading potentially dangerous file types such as executables, scripts, and archives.

The file blocking profile is applied to a **Security Policy** so that all outbound traffic from the internal network is inspected and restricted files are blocked.

---

## Lab Environment

| Component | Details |
|----------|--------|
| Firewall | Palo Alto VM-Series |
| PAN-OS Version | 11.2 |
| Hypervisor | VMware Workstation |
| Client Machine | Ubuntu 24.04 |

---

## Topology

```
Ubuntu Client → Palo Alto Firewall → Internet
```

---

## Blocked File Types

```
exe
bat
jar
vbs
pe
scr
zip
```

---

## Configuration Summary

1. **Create File Blocking Profile**
   - Navigate to  
   `Objects → Security Profiles → File Blocking`
   - Create profile **File-Blocking-Profile**
   - Add rules to block high-risk file types.

2. **Attach Profile to Security Policy**
   - Navigate to  
   `Policies → Security`
   - Edit rule **Trust → Untrust**
   - Attach **File-Blocking-Profile**

3. **Commit Configuration**
   - Apply the configuration to enforce the policy.

---

## Testing

Attempt to download a test file:

```
http://ipv4.download.thinkbroadband.com/5MB.zip
```

Expected Result:

The firewall blocks the download and resets the connection.

---

## Result

The Palo Alto firewall successfully blocks restricted file downloads and logs the event in firewall traffic logs.

---

## Author

**Vishesh Dixit**
