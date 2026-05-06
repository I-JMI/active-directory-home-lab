# 💻 Windows Server 2022 Active Directory Home Lab

![Windows Server](https://img.shields.io/badge/Windows_Server-2022-blue)
![Windows 10](https://img.shields.io/badge/Windows_10-Pro-blue)
![Active Directory](https://img.shields.io/badge/Active_Directory-Lab-success)
![VirtualBox](https://img.shields.io/badge/Oracle_VirtualBox-Virtualization-orange)

---

# 🔹 Overview

Built a virtualized Windows enterprise environment using **Windows Server 2022**, **Windows 10 Pro**, and **Active Directory Domain Services (AD DS)** within Oracle VirtualBox.

This lab simulated a real-world corporate network by deploying a Domain Controller responsible for centralized authentication, identity management, DNS resolution, and workstation domain integration.

The project demonstrates hands-on experience with:

- Active Directory deployment
- Domain Controller promotion
- DNS troubleshooting
- Windows domain administration
- User account management
- Domain-joined workstation configuration
- Enterprise network simulation
- Windows authentication workflows

The goal of this lab was to strengthen practical system administration and IT support skills commonly used in Help Desk, Desktop Support, and Junior System Administrator roles.

---

# 🔹 Core Skills Demonstrated

- Active Directory Administration
- Domain Controller Deployment
- DNS Troubleshooting
- Windows Server Administration
- Windows 10 Domain Integration
- User Provisioning & Authentication
- Static IP Configuration
- Virtual Network Configuration
- Troubleshooting & Root Cause Analysis
- Virtualization using Oracle VirtualBox

---

# 🔹 Environment & Infrastructure

| Component | Technology |
| :--- | :--- |
| Hypervisor | Oracle VirtualBox |
| Server OS | Windows Server 2022 |
| Client OS | Windows 10 Pro |
| Directory Services | Active Directory Domain Services (AD DS) |
| DNS Services | Windows DNS |
| Network Type | Internal Virtual Network |
| Domain Name | `jaimiesupport.local` |

---

# 🌐 Phase 1 – Virtual Network Configuration

To simulate a real-world enterprise environment, both virtual machines were isolated within a private internal network.

A dedicated VirtualBox internal network named `lab-network` was configured to allow secure communication between the Domain Controller and Windows 10 client workstation.

---

## 🔹 VirtualBox Internal Network Configuration

### Internal Network Setup
![Network Settings](vbox-internal-network.png)

*Configuring VirtualBox internal networking for isolated lab communication.*

### Windows 10 Client Network Adapter
![Client Network Settings](vbox-client-network.png)

*Connecting the Windows 10 workstation to the internal enterprise network.*

---

## 🔹 Static IP Address Assignment

Static IP addressing was manually configured to ensure consistent DNS communication and domain connectivity.

| Device | IP Address |
| :--- | :--- |
| Domain Controller | `10.0.0.1` |
| Windows 10 Client | `10.0.0.2` |

### Server Static IP Configuration
![Server Static IP Configuration](server-ip-config.png)

*Configuring static IPv4 settings for the Domain Controller.*

---

# 🏢 Phase 2 – Active Directory Domain Services Deployment

Active Directory Domain Services (AD DS) was installed on the Windows Server 2022 virtual machine to establish centralized identity and authentication management.

The server was promoted to a Domain Controller for the new forest:

```text
jaimiesupport.local
```

During promotion, DNS services were automatically installed and configured to support domain name resolution throughout the environment.

---

## 🔹 Active Directory Installation Process

### AD DS Installation Progress
![Active Directory Installation Progress](ad-install-progress.png)

*Installing Active Directory Domain Services on Windows Server 2022.*

### Successful Domain Administrator Login
![Verified Domain Administrator Login](server-domain-login.png)

*Verifying successful Domain Controller promotion and administrative authentication.*

---

# 🧠 Phase 3 – Troubleshooting & DNS Resolution

## 🔹 Problem Encountered

While attempting to join the Windows 10 workstation to the domain, the client machine initially failed to communicate with the Domain Controller.

The issue was diagnosed as a DNS resolution problem preventing the workstation from locating the domain services.

---

## 🔹 Root Cause Analysis

The Windows 10 client was not using the Domain Controller as its primary DNS server, preventing proper domain name resolution and authentication.

---

## 🔹 Resolution

The client workstation's IPv4 configuration was manually updated to point its DNS settings to the Domain Controller (`10.0.0.1`).

Once DNS communication was corrected, domain connectivity and authentication were successfully established.

---

### Domain Join Failure
![Domain Join Error](domain-join-error.png)

*Initial domain join failure caused by improper DNS configuration.*

### DNS Configuration Fix
![DNS Fix on Client](dns-fix-on-client.png)

*Updating client DNS settings to communicate with the Domain Controller.*

---

# ✅ Phase 4 – Active Directory Validation & Authentication Testing

After resolving DNS communication issues, the Windows 10 workstation successfully joined the domain and authenticated against Active Directory.

---

## 🔹 Active Directory User Management

A domain user account was created within Active Directory Users & Computers (ADUC).

### Active Directory User List
![AD User List](ad-user-list.png)

*Managing domain user accounts within Active Directory.*

---

## 🔹 Domain Membership Verification

The Windows 10 workstation successfully joined the `jaimiesupport.local` domain.

### System Properties Confirmation
![System Properties Success](system-properties-success.png)

*Verifying successful workstation domain membership.*

---

## 🔹 Successful User Authentication

The domain user successfully authenticated through Active Directory and logged into the Windows 10 workstation.

### Windows 10 Domain User Login
![Windows 10 Domain User Login](client-domain-login.png)

*Authenticating with Active Directory domain credentials.*

### Authentication Verification
![WhoAmI Victory](whoami-victory.png)

*Using the `whoami` command to verify successful domain authentication.*

---

# 🔹 Skills Demonstrated

## Active Directory Administration

- Domain Controller deployment
- User account creation and management
- Domain authentication workflows
- Windows domain integration

## Networking & DNS

- Static IP addressing
- Internal virtual network configuration
- DNS troubleshooting and resolution
- Client-server communication validation

## Windows System Administration

- Windows Server 2022 deployment
- Windows 10 workstation configuration
- Administrative authentication management
- Domain services configuration

## Technical Troubleshooting

- Root cause analysis
- DNS diagnostics
- Domain connectivity troubleshooting
- Authentication issue resolution

---

# 🧠 What I Learned

- How enterprise environments use Active Directory for centralized authentication
- Importance of DNS within domain environments
- Fundamentals of Domain Controller deployment
- Windows client domain join procedures
- Troubleshooting methodology for authentication and connectivity issues
- Importance of proper network and DNS configuration in enterprise systems

---

# 🚀 Future Improvements

- Add Group Policy Objects (GPO) for workstation management
- Deploy multiple organizational units (OUs)
- Implement roaming profiles and shared folders
- Expand environment with additional client workstations
- Integrate PowerShell automation for user provisioning
- Add DHCP services for automated IP assignment

---

# 📌 Notes

All systems, configurations, troubleshooting activities, and deployments were performed within a controlled virtual lab environment for educational and portfolio purposes to demonstrate hands-on Windows system administration and Active Directory support skills.
