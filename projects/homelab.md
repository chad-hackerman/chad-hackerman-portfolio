# Cybersecurity Homelab

**Documentation Status:** Complete

**Infrastructure Status:** Active

**Tech Stack:** Proxmox 8.1, pfSense, Security Onion, Kali Linux, ELK Stack

[Documentation](https://github.com/chad-hackerman/homelab)

---

## Project Overview

Complete security testing environment for hands-on practice with enterprise security tools and attack simulation.

**Purpose:** Create isolated environment for:
- Penetration testing practice
- Security tool evaluation
- Attack simulation and defense
- Certification exam preparation

---

## Infrastructure Components

### Hardware
- 2x Dell R720 servers (Proxmox cluster)
- 128GB RAM total
- 4TB storage (RAID 10)
- Dedicated gigabit switch

### Virtual Machines
- **pfSense** - Network firewall and routing
- **Security Onion** - Network security monitoring
- **Kali Linux** - Penetration testing platform
- **ELK Stack** - Log aggregation and analysis
- **Windows Server 2022** - Active Directory lab
- **Ubuntu Server** - Various web services

---

## Network Architecture

```mermaid
graph TB
    Internet((Internet)) --> WAN

    subgraph pfSense ["🔥 pfSense Firewall"]
        WAN[WAN Interface]
        LAN[LAN Interface]
        VLAN10[VLAN 10 - Management]
        VLAN20[VLAN 20 - Attack Network]
        VLAN30[VLAN 30 - Target Network]
    end

    WAN --> LAN
    LAN --> VLAN10
    LAN --> VLAN20
    LAN --> VLAN30

    subgraph MGMT ["🔒 Management Network (10.0.10.0/24)"]
        PROXMOX1[Proxmox Node 1<br/>10.0.10.11]
        PROXMOX2[Proxmox Node 2<br/>10.0.10.12]
        ELK[ELK Stack<br/>10.0.10.20]
        SO[Security Onion<br/>10.0.10.30]
    end

    subgraph ATTACK ["⚔️ Attack Network (10.0.20.0/24)"]
        KALI[Kali Linux<br/>10.0.20.10]
    end

    subgraph TARGET ["🎯 Target Network (10.0.30.0/24)"]
        WIN[Windows Server 2022<br/>AD DC - 10.0.30.10]
        UBUNTU[Ubuntu Server<br/>10.0.30.20]
        VULN[Vulnerable VMs<br/>10.0.30.50-99]
    end

    VLAN10 --> MGMT
    VLAN20 --> ATTACK
    VLAN30 --> TARGET

    SO -.->|Mirror Port - Traffic Analysis| TARGET
    ELK -.->|Log Ingestion| TARGET
    ELK -.->|Log Ingestion| MGMT
```

Three security zones:
- **Management Network** - Administrative access only
- **Attack Network** - Kali and offensive tools
- **Target Network** - Vulnerable systems for testing

---

## Learning Outcomes

Through this homelab, I've gained hands-on experience with:
- Enterprise firewall configuration and rules
- SIEM deployment and log analysis
- Network segmentation and VLANs
- IDS/IPS configuration and tuning
- Active Directory security hardening

---

## Photos

![Cybersecurity homelab featuring server rack with cable management](../images/homelab-photo.jpg)

---

[← Back to Main Portfolio](../README.md)
