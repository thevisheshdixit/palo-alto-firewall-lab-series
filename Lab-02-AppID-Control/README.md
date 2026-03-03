# Lab 02 – App-ID Based Application Control

📄 File: `Lab-02-AppID-Control/Lab-02-AppID-Based-Control.pdf`

This lab implements application-layer blocking using Palo Alto App-ID technology.

### Objective

Block Facebook and YouTube traffic for a specific internal host in the Trust zone.

### Configuration Scope

- Security policy rule creation
- Source-based restriction (specific Ubuntu IP)
- Application-based filtering:
  - facebook
  - youtube
  - youtube-base
  - google-base
  - google-video
  - quic
- Service set to application-default
- Action configured as Deny
- Logging enabled at session end

### Validation

- Browser access attempts blocked
- Traffic logs show action: deny/reset-both
- Rule name verification in logs
- App-ID correctly identified blocked applications

This lab demonstrates application-layer inspection and granular traffic control using App-ID.
