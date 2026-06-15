# Active Directory Detection Lab

## Overview

This project demonstrates the deployment of an Active Directory home lab using Windows Server 2022 and a domain-joined Windows 10 endpoint. Windows Security logs were forwarded to Splunk Enterprise to monitor authentication activity and investigate successful and failed logon events.

## Lab Architecture

- Windows Server 2022 Domain Controller
- Active Directory Domain Services (AD DS)
- DNS Server
- Windows 10 Domain Client
- Splunk Enterprise
- Splunk Universal Forwarder

## Tasks Completed

- Installed Windows Server 2022
- Configured Active Directory Domain Services
- Created the `corp.local` domain
- Configured DNS services
- Created Organizational Units (OUs)
- Created domain users (John Smith and Alice Brown)
- Joined Windows 10 to the domain
- Configured Splunk Universal Forwarder
- Forwarded Windows Security logs to Splunk
- Monitored authentication events

## Detection Use Cases

### Failed Logon Detection (4625)

```spl
index=main source="WinEventLog:Security" EventCode=4625
```

### Successful Logon Detection (4624)

```spl
index=main source="WinEventLog:Security" EventCode=4624
```

### Authentication Monitoring

```spl
index=main source="WinEventLog:Security"
| stats count by EventCode
```

## Screenshots

### Domain User Authentication
- Domain user logged in as CORP\jsmith

### Domain Joined Client
- Windows 10 successfully joined to corp.local

### Active Directory Users and Computers
- Employees OU
- John Smith
- Alice Brown

### DNS Configuration
- Forward Lookup Zone for corp.local

### Failed Logon Detection
- Event ID 4625 detected in Splunk

### Successful Logon Detection
- Event ID 4624 detected in Splunk

## Skills Demonstrated

- Active Directory Administration
- Windows Server 2022
- DNS Management
- Domain User Management
- Windows Authentication
- Splunk SIEM
- Security Monitoring
- Log Analysis
- Authentication Event Detection

## Technologies Used

- Windows Server 2022
- Windows 10
- Active Directory Domain Services
- DNS
- Splunk Enterprise
- Splunk Universal Forwarder
