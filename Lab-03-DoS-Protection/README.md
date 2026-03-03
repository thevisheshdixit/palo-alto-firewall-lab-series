# Lab 03 – DoS Protection Configuration & Validation

📄 File: `Lab-03-DoS-Protection/Lab-03-DoS-Protection.pdf`

This lab focuses on implementing Zone Protection and Aggregate DoS Protection profiles to defend against flood-based attacks.

### Configuration Scope

### Zone Protection Profile
- SYN Flood protection
- UDP Flood protection
- ICMP Flood protection
- Alarm, Activate, and Maximum thresholds
- Random Early Drop configuration

### Aggregate DoS Protection Profile
- Threshold-based rate limiting
- Block duration configuration
- Protection applied to specific internal server

### DoS Policy Rule
- Source Zone: Untrust
- Destination Zone: Trust
- Specific protected Ubuntu server
- Action: Protect

### Attack Simulation & Validation

- ICMP and TCP flood traffic generated using hping3
- Flood mode testing (-flood)
- Threat logs confirm:
  - Action: drop
  - Severity: critical
- No successful replies to attack traffic

This lab demonstrates proactive detection and mitigation of denial-of-service attacks using Palo Alto security mechanisms.

---

## Technical Skills Demonstrated

- Palo Alto VM-Series deployment
- Layer 3 firewall architecture
- Zone-based segmentation
- Static routing and traffic forwarding
- Dynamic Source NAT (PAT)
- App-ID application inspection
- Security policy rule evaluation
- Zone Protection configuration
- Aggregate DoS profile implementation
- Threat log analysis
- Attack simulation using hping3
- End-to-end troubleshooting
