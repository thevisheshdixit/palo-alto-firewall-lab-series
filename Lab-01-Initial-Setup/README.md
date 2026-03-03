
# Lab 01 – Initial Setup and Base Configuration

📄 File: `Lab-01-Initial-Setup/Lab-01-Initial-Setup.pdf`

This lab covers complete deployment and foundational configuration of the Palo Alto VM-Series firewall.

### Configuration Scope

- Management IP configuration via CLI
- Layer 3 interface setup (WAN & LAN)
- Security zone creation (Trust / Untrust)
- Virtual Router configuration
- Static default route (0.0.0.0/0)
- Dynamic Source NAT (PAT)
- Security policy configuration (Trust → Untrust)
- Connectivity verification (ICMP & Web access)
- Traffic log validation (App-ID, NAT Applied, Action)

### Validation Performed

- Successful ICMP ping from Ubuntu
- Verified outbound internet access
- Confirmed NAT translation in logs
- Confirmed application identification via App-ID

This lab demonstrates foundational firewall deployment and traffic flow validation.
