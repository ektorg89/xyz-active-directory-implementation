# XYZ Company — Active Directory Implementation Manual 2026

Technical documentation for the Windows Server 2016 Active Directory lab deployment for XYZ Company (domain: `xyz.local`, NetBIOS: `XYZ_Company`).

---

## Overview

This manual covers the full configuration of an Active Directory environment including domain controller promotion, DNS, DHCP, organizational units, user and computer accounts, security groups, Group Policy, and shared folder permissions.

**Domain Controller:** WIN-FGVB4CUDPU2 / XYZ-DC1  
**Server IP:** 10.0.0.1 / DC IP: 10.2.0.6  
**Domain:** xyz.local

---

## Contents

| File | Description |
|------|-------------|
| `Manual-2026 Final.docx` | Final version of the implementation manual |
| `Manual-2026 Final.pdf` | PDF export of the final manual |

---

## Topics Covered

### Active Directory Domain Services
- AD DS role installation and domain controller promotion
- Domain configuration (`xyz.local`, NetBIOS: `XYZ_Company`)

### DNS
- Forward and reverse lookup zones
- Host A records, DDNS, WINS lookup
- A Registry DNS configuration

### DHCP
- Scope: `10.0.0.0` — range `10.0.0.1–10.255.255.254`
- Exclusions: `10.0.0.1–10.0.0.50`
- Reservations: Finance-DB, IT-Fileserver

### Organizational Units
| OU | Sub-OUs |
|----|---------|
| Marketing | — |
| Sales | — |
| Finance | — |
| Executives | — |
| Information Technology | Help Desk, Network Support |

### User Accounts
- Moira Cowan, John Harold Smith, Chris Medved, Frank Adili
- Christy Jackson, Mark Manore, Jason Zandri, Mike Aubert, John Smith

### Computer Accounts
- `MKTG-PC1`, `MKTG-PC2`, `Finance-DB`, `IT-Fileserver`

### Security Groups
- Marketing Users / Marketing Resources
- Sales Users / Sales Resources
- Finance Users / Finance Resources
- IT Users / IT Resources
- Help Desk Users / Help Desk Resources
- Network Support Users / Network Support Resources

### Group Policy
- **Marketing Policy** linked to Marketing OU
  - Software deployment: 7-Zip 24.09 x64
  - Desktop wallpaper enforcement
  - Control Panel, Run menu, Recycle Bin, My Documents icon restrictions
  - Remove username from Start Menu

### Security Policies
| Policy | Value |
|--------|-------|
| Account lockout duration | 15 minutes |
| Lockout threshold | 3 attempts |
| Observation window | 5 minutes |
| Minimum password length | 12 characters |
| Password history | 12 passwords |
| Password complexity | Enabled |

### Shared Folder
- Path: `\\XYZ-DC1\Reports`
- Permissions: Marketing Users group
