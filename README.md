# Windows Server 2022 & Active Directory Home Lab

## 📋 Project Overview
This project involved building a virtualized enterprise network environment. I successfully deployed a Domain Controller to manage centralized identity and authentication for a Windows 10 workstation.

## 🛠️ Environment Details
- **Hypervisor:** Oracle VirtualBox
- **Network Type:** Internal Network (`lab-network`)
- **Domain Name:** `jaimiesupport.local`[cite: 1]
- **Server IP:** `10.0.0.1`[cite: 1]
- **Workstation IP:** `10.0.0.2`[cite: 1]

## 🧠 Lessons Learned & Troubleshooting
### The DNS Handshake
The most significant challenge was a connection failure when joining the Windows 10 Client to the domain[cite: 1]. I diagnosed this as a DNS resolution issue. By manually configuring the Client's IPv4 settings to point to the Server's IP as the primary DNS, I established a successful "handshake" between the machines[cite: 1].

## 🖼️ Success Evidence
### 1. Active Directory User Created
I created a user account for **John Doe** (`jdoe`) within the AD DS database[cite: 1].

### 2. Domain Membership Verified
The workstation successfully joined the `jaimiesupport.local` domain[cite: 1].

### 3. Successful Authentication
Logged in as `jdoe` and verified identity using the `whoami` command[cite: 1].
