# Sophos XG Firewall SNMP Monitoring Template for Zabbix

<div align="center">

[![Zabbix Version](https://img.shields.io/badge/Zabbix-7.2.0+-red?style=for-the-badge&logo=zabbix)](https://www.zabbix.com/)
[![Template Version](https://img.shields.io/badge/Template_Version-1.0.0-blue?style=for-the-badge)](https://github.com/aierdemsunar/sophos-xg-zabbix-template)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)
[![SNMP Version](https://img.shields.io/badge/SNMP-v2c%20%7C%20v3-orange?style=for-the-badge)](https://www.sophos.com/)
[![GitHub Stars](https://img.shields.io/github/stars/aierdemsunar/sophos-xg-zabbix-template?style=for-the-badge)](https://github.com/aierdemsunar/sophos-xg-zabbix-template/stargazers)
[![GitHub Issues](https://img.shields.io/github/issues/aierdemsunar/sophos-xg-zabbix-template?style=for-the-badge)](https://github.com/aierdemsunar/sophos-xg-zabbix-template/issues)
[![Contributions Welcome](https://img.shields.io/badge/Contributions-Welcome-brightgreen?style=for-the-badge)](CONTRIBUTING.md)

<h1>🔥 Advanced Sophos XG Firewall Monitoring Template 🔥</h1>

**The most comprehensive SNMP monitoring solution for Sophos XG Firewall on Zabbix platform**

[Features](#-features) • [Installation](#-installation) • [Configuration](#-configuration) • [Support](#-support) • [License](#-license)

</div>

---

## 📋 Table of Contents

- [About](#-about)
- [Features](#-features)
- [Screenshots](#-screenshots)
- [Requirements](#-requirements)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [Template Components](#-template-components)
- [Monitoring Capabilities](#-monitoring-capabilities)
- [Auto-Discovery Rules](#-auto-discovery-rules)
- [Dashboard & Visualization](#-dashboard--visualization)
- [Troubleshooting](#-troubleshooting)
- [Contributing](#-contributing)
- [Credits](#-credits)
- [License](#-license)
- [Support & Contact](#-support--contact)

---

## 🌟 About

This professional-grade Zabbix template provides **comprehensive monitoring** for Sophos XG Firewall appliances through SNMP protocol. Developed by **Ali Erdem Sunar** at **Pinet Bilişim A.Ş.**, this template offers deep insights into your firewall's performance, security status, and overall health.

### 🎯 Key Benefits

- ✅ **Complete Monitoring**: Track 100+ metrics from your Sophos XG
- ✅ **Auto-Discovery**: Automatically detect interfaces, VPN tunnels, and WiFi APs
- ✅ **Real-time Alerts**: Get notified about critical issues instantly
- ✅ **Beautiful Dashboards**: Pre-configured visualizations for quick insights
- ✅ **Enterprise Ready**: Battle-tested in production environments
- ✅ **Easy Installation**: Simple setup with detailed documentation

### 🏢 Developer Information

<table>
<tr>
<td align="center">
<img src="https://github.com/aierdemsunar.png" width="100px;" alt="Ali Erdem Sunar"/><br />
<sub><b>Ali Erdem Sunar</b></sub><br />
<a href="https://github.com/aierdemsunar" title="GitHub">💻</a> 
<a href="mailto:aerdemsunar@pinet.com.tr" title="Email">📧</a>
<a href="https://www.linkedin.com/in/aierdemsunar" title="LinkedIn">💼</a>
</td>
<td>
<strong>Company:</strong> Pinet Bilişim A.Ş.<br />
<strong>Website:</strong> <a href="https://www.pinet.com.tr">www.pinet.com.tr</a><br />
<strong>Email:</strong> info@pinet.com.tr<br />
<strong>Phone:</strong> +90 (312) 911 9113<br />
<strong>Location:</strong> Ankara, Turkey<br />
<strong>Year:</strong> 2025
</td>
</tr>
</table>

---

## 🚀 Features

### 📊 Comprehensive Monitoring
- **21 Service Health Checks**: Monitor all critical Sophos services
- **9 License Types**: Track expiration and status of all licenses
- **High Availability**: Complete HA cluster monitoring
- **Real-time Performance**: CPU, Memory, Disk, and Network metrics
- **Traffic Analytics**: Protocol-based traffic statistics

### 🔍 Smart Auto-Discovery
- **Network Interfaces**: Automatic port discovery with traffic metrics
- **VPN Tunnels**: IPSec tunnel detection and monitoring
- **WiFi Access Points**: AP discovery with client tracking
- **VPN Policies**: Policy detection with encryption details
- **WiFi Clients**: Client discovery with connection details

### 🎨 Professional Dashboards
- Pre-configured overview dashboard
- Real-time performance graphs
- Service status widgets
- Traffic statistics visualization
- Custom graph prototypes

### ⚡ Advanced Features
- **SNMP Trap Support**: Capture and process SNMP traps
- **Intelligent Alerting**: Multi-level trigger system
- **Flexible Macros**: Easy customization
- **Value Mapping**: Human-readable status displays
- **Tag Support**: Modern Zabbix tag system

---

## 📸 Screenshots

<div align="center">

### Main Dashboard
![Sophos XG Dashboard](https://via.placeholder.com/800x400?text=Sophos+XG+Dashboard+Screenshot)

### Service Status
![Service Status](https://via.placeholder.com/800x400?text=Service+Status+Screenshot)

### Performance Graphs
![Performance Graphs](https://via.placeholder.com/800x400?text=Performance+Graphs+Screenshot)

</div>

---

## 📋 Requirements

### System Requirements
- **Zabbix Server**: Version 7.2.0 or higher
- **Sophos XG Firewall**: SFOS v18.0 or higher
- **Protocol**: SNMP v2c or v3
- **Network**: UDP port 161 (SNMP) and 162 (Traps)

### Compatibility Matrix
| Sophos XG Version | Template Version | Status |
|-------------------|------------------|---------|
| v18.0+ | 1.0.0 | ✅ Fully Supported |
| v17.5 | 1.0.0 | ⚠️ Limited Support |
| < v17.5 | 1.0.0 | ❌ Not Supported |

---

## 📥 Installation

### Step 1: Enable SNMP on Sophos XG

#### Via Web Admin Console:
```
1. Navigate to: System → Administration → SNMP
2. SNMP Service: Enable ✓
3. SNMP Version: Select v2c or v3
4. Community String: Set your community (default: public)
5. Allowed Hosts: Add your Zabbix server IP
6. Apply changes
```

#### Via CLI (SSH):
```bash
configure
system snmp
set status enable
set version v2c
set community YourCommunityString
set allowed-hosts add host=<ZABBIX_SERVER_IP>
commit
```

### Step 2: Install MIB File on Zabbix Server

```bash
# Download the template repository
git clone https://github.com/aierdemsunar/sophos-xg-zabbix-template.git
cd sophos-xg-zabbix-template

# Copy MIB file to system MIB directory
sudo cp sophos-xg.mib /usr/share/snmp/mibs/

# Restart SNMP daemon
sudo systemctl restart snmpd

# Verify MIB installation
snmptranslate -On SFOS-FIREWALL-MIB::sfosDeviceName
```

### Step 3: Import Template to Zabbix

1. Log in to Zabbix Web Interface
2. Navigate to: **Configuration** → **Templates** → **Import**
3. Click **Choose File** and select `sophos-xg-firewall-template.yaml`
4. Configure import options:
   - ✓ Create new templates
   - ✓ Create new items
   - ✓ Create new triggers
   - ✓ Create new graphs
   - ✓ Create new discovery rules
   - ✓ Create new dashboards
5. Click **Import**

### Step 4: Create Host and Apply Template

```yaml
Host Configuration:
  Host name: sophos-xg-fw01
  Visible name: Sophos XG Firewall 01
  Groups: 
    - Network devices
    - Firewalls
  Templates:
    - Sophos XG Firewall SNMP
  Interfaces:
    - Type: SNMP
      IP address: 192.168.1.1
      Port: 161
      SNMP version: SNMPv2
  Macros:
    - {$SNMP_COMMUNITY}: YourCommunityString
```

---

## ⚙️ Configuration

### Essential Macros

| Macro | Default | Description | Recommended Range |
|-------|---------|-------------|-------------------|
| `{$SNMP_COMMUNITY}` | public | SNMP community string | - |
| `{$DISK_UTIL_WARN}` | 85 | Disk warning threshold (%) | 80-90 |
| `{$DISK_UTIL_CRIT}` | 95 | Disk critical threshold (%) | 90-98 |
| `{$MEMORY_UTIL_WARN}` | 85 | Memory warning threshold (%) | 80-90 |
| `{$MEMORY_UTIL_CRIT}` | 95 | Memory critical threshold (%) | 90-98 |
| `{$LICENSE_EXPIRY_WARN_DAYS}` | 30 | License expiry warning (days) | 15-60 |

### SNMP Configuration Best Practices

1. **Security**: Always use SNMPv3 in production environments
2. **Performance**: Limit SNMP access to Zabbix server only
3. **Monitoring**: Enable SNMP traps for real-time alerts
4. **Bandwidth**: Adjust polling intervals based on link capacity

---

## 📦 Template Components

### 🔍 Items (130+)

<details>
<summary>Click to expand full item list</summary>

#### Device Information
- Device Name, Type, Serial Number
- Firmware Version with Change Detection
- WebCat and IPS Database Versions
- System Date and Uptime

#### System Performance
- CPU Utilization
- Memory Usage (RAM)
- Swap Usage
- Disk Usage (per partition)
- Live User Count

#### Service Monitoring (21 Services)
- **Email**: POP3, IMAP4, SMTP
- **Security**: AV, AS, IPS, WebCat
- **Network**: DNS, HTTP, FTP, SSH
- **VPN**: SSL VPN, IPSec VPN
- **System**: Apache, Tomcat, Database, NTP
- **Cluster**: HA, Garner, Drouting, DGD

#### License Tracking (9 Types)
- Base Firewall License
- Network Protection
- Web Protection
- Email Protection
- Web Server Protection
- Zero-Day Protection (Sandstorm)
- Enhanced Support
- Enhanced Plus Support
- Central Orchestration

</details>

### ⚠️ Triggers (45+)

<details>
<summary>Click to expand trigger list</summary>

#### Critical (Disaster)
- Disk usage > 95%
- Memory usage > 95%
- HA in faulty state
- Critical service down

#### High Severity
- Disk usage > 85%
- Memory usage > 85%
- Swap usage > 80%
- Important service down
- License expired

#### Warning
- Swap usage > 50%
- License expiring soon
- VPN tunnel down
- High WiFi client count

</details>

### 📊 Graphs & Dashboards

- **System Performance**: CPU, Memory, Disk trends
- **Network Traffic**: Interface utilization graphs
- **Service Status**: Service availability overview
- **VPN Statistics**: Tunnel status and traffic
- **License Timeline**: Expiration tracking

---

## 🔄 Auto-Discovery Rules

### 1. Network Interface Discovery
```yaml
Discovery Key: ifDescr
Update Interval: 1h
Items Created:
  - Interface Status
  - Traffic In/Out (bps)
  - Errors In/Out
  - Discards In/Out
  - Bandwidth Utilization
```

### 2. IPSec VPN Tunnel Discovery
```yaml
Discovery Key: sfosIPSecVpnConnName
Update Interval: 5m
Items Created:
  - Connection Status
  - Active Tunnel Count
  - Tunnel Activation State
```

### 3. WiFi Access Point Discovery
```yaml
Discovery Key: sfosWifiApName
Update Interval: 5m
Items Created:
  - AP Connection Status
  - Connected Client Count
  - Signal Strength
```

---

## 🛠️ Troubleshooting

### Common Issues & Solutions

#### 1. No Data Collection
```bash
# Test SNMP connectivity
snmpwalk -v2c -c public <SOPHOS_IP> sysDescr

# Check firewall rules
sudo iptables -L -n | grep 161

# Verify Zabbix can reach Sophos
zabbix_get -s <SOPHOS_IP> -k system.uptime
```

#### 2. Discovery Not Working
- Enable SNMP bulk operations on Sophos
- Increase discovery timeout in template
- Check Zabbix server performance

#### 3. Missing Metrics
- Verify Sophos firmware version (v18+ required)
- Ensure all services are licensed
- Check SNMP view permissions

### Debug Commands
```bash
# Enable Zabbix debug logging
zabbix_server -R log_level_increase

# Monitor SNMP traffic
tcpdump -i any -n port 161 -vv

# Check Zabbix item errors
grep "item.*sophos" /var/log/zabbix/zabbix_server.log
```

---

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md).

### How to Contribute
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Setup
```bash
# Clone repository
git clone https://github.com/aierdemsunar/sophos-xg-zabbix-template.git

# Install development dependencies
pip install -r requirements-dev.txt

# Run tests
python -m pytest tests/

# Validate template
zabbix_template_validator sophos-xg-firewall-template.yaml
```

---

## 👥 Credits

### Primary Developer
- **Ali Erdem Sunar** - *Initial work and maintenance* - [GitHub](https://github.com/aierdemsunar)

### Company
- **Pinet Bilişim A.Ş.** - *Enterprise IT Solutions* - [Website](https://www.pinet.com.tr)

### Special Thanks
- Sophos Community for MIB documentation
- Zabbix Team for the excellent monitoring platform
- All contributors and testers

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2025 Ali Erdem Sunar / Pinet Bilişim A.Ş.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction...
```

---

## 💬 Support & Contact

### 🐛 Bug Reports & Feature Requests
Please use [GitHub Issues](https://github.com/aierdemsunar/sophos-xg-zabbix-template/issues)

### 📧 Professional Support
**Pinet Bilişim A.Ş.**
- 🌐 Website: [www.pinet.com.tr](https://www.pinet.com.tr)
- 📧 Email: [info@pinet.com.tr](mailto:info@pinet.com.tr)
- 📞 Phone: +90 (312) 911 9113
- 📍 Address: Ankara, Turkey

### 🌟 Show Your Support
If this template helps you, please consider:
- ⭐ Starring the repository
- 🐦 Sharing on social media
- 💰 [Sponsoring development](https://github.com/sponsors/aierdemsunar)

---

<div align="center">

### 🏷️ Keywords
`zabbix` `zabbix-template` `sophos` `sophos-xg` `sophos-firewall` `snmp` `snmp-monitoring` `network-monitoring` `firewall-monitoring` `monitoring` `observability` `infrastructure-monitoring` `network-security` `vpn-monitoring` `wifi-monitoring` `license-monitoring` `high-availability` `dashboard` `alerting` `enterprise-monitoring`

---

Made with ❤️ by [Ali Erdem Sunar](https://github.com/aierdemsunar) at [Pinet Bilişim](https://www.pinet.com.tr)

</div> 