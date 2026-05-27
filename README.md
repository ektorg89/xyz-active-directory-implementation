# XYZ Company — Active Directory Implementation Manual 2026

Technical documentation for the Windows Server 2016 Active Directory lab deployment for XYZ Company (domain: `xyz.local`, NetBIOS: `XYZ_Company`).

---

## Overview

This manual covers the full configuration of an Active Directory environment including domain controller promotion, DNS, DHCP, organizational units, user and computer accounts, security groups, Group Policy, and shared folder permissions. The lab was completed across four sessions in April 2026.

**Domain Controller:** WIN-FGVB4CUDPU2 / XYZ-DC1  
**Server IP:** 10.0.0.1 / DC IP: 10.2.0.6  
**Domain:** xyz.local

---

## Contents

| File / Folder | Description |
|---------------|-------------|
| `Manual-2026 Final.docx` | Final version of the implementation manual |
| `Manual-2026 Final.pdf` | PDF export of the final manual |
| `screenshots/` | 77 lab screenshots documenting each configuration step |

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
- Per-user settings: logon hours, logon message, address, job title

### Computer Accounts
- `MKTG-PC1`, `MKTG-PC2`, `Finance-DB`, `IT-Fileserver`

### Security Groups
- Marketing Users / Marketing Resources
- Sales Users / Sales Resources
- Finance Users / Finance Resources
- IT Users / IT Resources
- Help Desk Users / Help Desk Resources
- Network Support Users / Network Support Resources
- Print Operators

### Group Policy
- **Marketing Policy** linked to Marketing OU
  - Software deployment: 7-Zip 24.09 x64
  - Desktop wallpaper enforcement (custom path)
  - Logon message configuration
  - Control Panel, Run menu, Recycle Bin, My Documents icon restrictions
  - Remove username from Start Menu
- Group Policy Modeling used to verify applied policies

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

---

## Screenshots

77 screenshots document each stage of the lab, organized by session date:

| Session | Date | Coverage |
|---------|------|----------|
| Session 1 | April 7 | AD DS install, domain setup, DNS zones, DHCP scope, NetBIOS, network settings, user creation (MCowan), security groups |
| Session 2 | April 14 | Computer accounts, DHCP reservations, user management, logon hours, logon message, password/lockout policies, GPO restrictions, shared folder |
| Session 3 | April 21 | IP addressing, software deployment GPO |
| Session 4 | April 28 | Full OU structure, all security groups, Marketing GPO (all policies), Group Policy Modeling, DNS/DHCP final state, user review |

**Sample screenshots by topic:**

- `Active Directory Domain Services Install Abr7.PNG` — AD DS role installation
- `Organizational Units Abr28.PNG` — Final OU hierarchy
- `Marketing Policy Abr28.PNG` — GPO linked to Marketing OU
- `Group Policy Modeling Abr28.PNG` — Policy simulation results
- `Software Installation Abr28.PNG` — 7-Zip deployment via GPO
- `Sharing Folder Abr14.PNG` — Reports share permissions
- `Applied GPO's Abr28.PNG` — Confirmed applied policies
