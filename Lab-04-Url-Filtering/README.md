# Palo Alto Firewall – URL Filtering Lab

## Overview
This lab demonstrates how to configure **URL Filtering on a Palo Alto Firewall** to block access to specific social media websites such as **YouTube and Facebook**.

The configuration is performed by creating a **Custom URL Category**, applying it to a **URL Filtering Profile**, and attaching the profile to a **Security Policy**.

This lab simulates a real-world scenario where organizations restrict access to certain websites to enforce security policies and improve productivity.

---

## Lab Objective

Configure URL filtering on a Palo Alto Firewall to:

- Block access to **youtube.com**
- Block access to **facebook.com**
- Apply filtering using a **URL Filtering Profile**
- Verify blocked traffic using **Firewall Logs**

---

## Lab Environment

| Component | Details |
|----------|--------|
| Virtualization Platform | VMware Workstation |
| Firewall | Palo Alto VM-Series |
| PAN-OS Version | 11.2.0 |
| Firewall Management IP | 192.168.1.15 |
| Client Machine | Ubuntu 24.04 LTS |
| Client IP | 192.168.2.1 |
| Test Browser | Brave |

---

## Network Topology

```
Ubuntu VM  →  Palo Alto Firewall  →  Internet
```

The Ubuntu client machine accesses the internet through the Palo Alto firewall where security policies and URL filtering are enforced.

---

## Configuration Steps

### 1. Create Custom URL Category

Navigate to:

```
Objects → Custom Objects → URL Category
```

Create a new category:

```
Name: block-social-media
```

Add the following URLs:

```
youtube.com
*.youtube.com
facebook.com
*.facebook.com
```

---

### 2. Create URL Filtering Profile

Navigate to:

```
Objects → Security Profiles → URL Filtering
```

Create a new profile:

```
Name: block-social-media-yt-fb
```

Under **Custom URL Categories**, set the action:

```
block-social-media → BLOCK
```

---

### 3. Attach Profile to Security Policy

Navigate to:

```
Policies → Security
```

Edit the rule allowing traffic from:

```
Trust → Untrust
```

Under the **Actions** tab attach the URL filtering profile:

```
block-social-media-yt-fb
```

---

### 4. Commit Configuration

Click **Commit** in the top-right corner of the firewall interface to apply the configuration.

---

## Testing

### Test YouTube Blocking

From the Ubuntu client machine open the browser and access:

```
https://youtube.com
```

Expected Result:

The site fails to load because the firewall blocks it.

---

### Test Facebook Blocking

Open:

```
https://facebook.com
```

Expected Result:

The connection is reset or blocked by the firewall.

---

## Log Verification

Navigate to:

```
Monitor → URL Filtering
```

Verify that the firewall logs show:

- URL access attempts
- Action: **block-url**
- Source IP of the client

---

## Result

The Palo Alto firewall successfully blocks access to **YouTube and Facebook** from the client machine. All access attempts are logged in the URL Filtering logs.

---

## Conclusion

This lab demonstrates how **Palo Alto URL Filtering** can be implemented to control web access within a network. By creating a custom URL category and applying it through a URL filtering profile in a security policy, administrators can enforce web usage policies effectively.

---

## Author

**Vishesh Dixit**

Network Security Enthusiast | Aspiring Firewall Engineer
