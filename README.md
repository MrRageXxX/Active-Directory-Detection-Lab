# Active Directory Detection Lab

## Overview

This project demonstrates the deployment of an Active Directory home lab using Windows Server 2022 and a domain-joined Windows 10 endpoint. Windows Security logs were forwarded to Splunk to monitor authentication activity and investigate successful and failed logon events.

## Lab Components

- Windows Server 2022 Domain Controller
- Active Directory Domain Services (AD DS)
- DNS Server
- Windows 10 Domain Client
- Splunk Enterprise
- Splunk Universal Forwarder

## Tasks Performed

- Installed and configured Active Directory Domain Services
- Created the `corp.local` domain
- Configured DNS services
- Created Organizational Units (OUs)
- Created domain users
- Joined Windows 10 to the domain
- Forwarded Windows Security logs to Splunk
- Monitored authentication events

## Detection Queries

### Failed Logons (4625)

```spl
index=main source="WinEventLog:Security" EventCode=4625
```

### Successful Logons (4624)

```spl
index=main source="WinEventLog:Security" EventCode=4624
```

## Screenshots

See the screenshots folder for:
- Domain user authentication
- Domain-joined client
- Active Directory Users and Computers
- DNS configuration
- Failed logon detection
- Successful logon detection

## Skills Demonstrated

- Active Directory Administration
- Windows Server 2022
- DNS Management
- Windows Authentication
- Splunk SIEM
- Security Monitoring
- Log Analysis
