#  Cybersecurity Lab Environment Setup

## Building an isolated virtual lab for penetration testing and ethical hacking practice

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/VirtualBox-v7.2.14-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Virtualization-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />
</p>

## Project overview
This project is about setup a small and controlled **Cybersecurity and Penetration lab environment** using  **virtual Box and Kali Linux**
The main purpose of the lab is to create a safe place where I can learn and practice cybersecurity activities such as network scanning, reconnaissance, vulnerability assessment, packet analysis, and penetration-testing techniques.

The lab uses a private VirtualBox NAT Network so that additional virtual machines can be added later and used as authorized target machines.

*Ethical Use: This lab is intended for education and authorized security testing only. I will only test systems that I own or have explicit permission to test.*

## Objectives 
The main objectives of this week1 project are:
- Install and configure VirtualBox v7.2.14.
- Download and configure Kali Linux 2026.2.
- Create a dedicated VirtualBox NAT Network.
- Configure kali Linux networking.
- Understand NAT Network, gateway, DHCP, and static IP addressing.
- Verify connectivity between the kali VM and virtual gateway.
- Test interne connectivity and DNS resolution.
- Create a clean VM snapshot for recovery.
- Document problems and their solutions.
- Prepare the environment for future cybersecurity labs.


## Purpose of the Lab

A cybersecurity lab gives me a controlled environment where I can safely experiment without directly affecting production systems.

The lab can later be used for:

- Network reconnaissance

- Port scanning

- Vulnerability assessment

- Packet analysis

- Web security testing

- Exploitation practice

- Security-tool experimentation

- Security monitoring and analysis

Future target VMs can be connected to the same NAT Network for authorized testing.

## Lab Architecture
![](image.png)


## Lab Configuration

| 🧩 Component       | ⚙️ Configuration   |
| ------------------ | ------------------  |
| 🖥️ Host OS         | Windows 11         |
| 🧠 Host RAM        | 32 GB               |
| ⚡ Processor       | Intel Core i7      |
| 🧰 Hypervisor      | VirtualBox 7.2.14  |
| 🐉 Security OS     | Kali Linux 2026.2  |
| 🧠 Kali RAM        | 2048 MB            |
| 🌐 Virtual Network | NAT Network        |
| 📡 Network Address | 10.0.0.0/24        |
| 🐧 Kali IP Address | 10.0.0.2/24        |
| 🚪 Default Gateway | 10.0.0.1           |
| 🌍 DNS Server      | 8.8.8.8            |
| 🔮 Future VM Range | 10.0.0.3–10.0.0.99 |

---
## Lab Setup Procedure

Step 1. Install 7-Zip

7-Zip was installed so that the Kali Linux virtual-machine archive could be extracted when required.

Tool: 7-Zip

Step 2. Install VirtualBox

Oracle VirtualBox was installed as the virtualization platform.

The installed version used in this project is:

VirtualBox 7.2.14

Screenshot:

Step 3. Create the NAT Network

A dedicated NAT Network was created in VirtualBox.

The network configuration was:

Network Name: NATNetwork
IPv4 Prefix:  10.0.0.0/24
Gateway:      10.0.0.1
DHCP:         Enabled
IPv6:         Disabled

The NAT Network allows virtual machines connected to the same network to communicate with each other while also providing NAT-based external connectivity.

Screenshot:

Step 5. Import Kali Linux

Kali Linux 2026.2 was imported into VirtualBox.

The VM was configured with:

Operating System: Kali Linux 2026.2
Network Adapter:  Adapter 1
Attached to:      NAT Network
Network:          NATNetwork
Adapter Type:     Intel PRO/1000 MT Desktop

The VM was started successfully after the VirtualBox virtualization configuration was corrected.

Screenshot:

Step 6. Configure the Kali Network

The Kali network interface was checked using:

ip addr show eth0

and:

ip -4 addr show

The network route was checked using:

ip route

The expected network design is:

Network:     10.0.0.0/24
Gateway:     10.0.0.1
Kali IP:     10.0.0.X/24
DNS:         8.8.8.8

## Lab Verification

The following tests will be performed after the final IP configuration is completed.

| ✅ Test                | 🧾 Command                  | 🎯 Expected Result                 |
| --------------------- | --------------------------- | ---------------------------------- |
| 🌐 Check IPv4 address | `ip -4 addr show eth0`      | Kali has the expected IPv4 address |
| 🛣️ Check routing      | `ip route`                  | Default route uses `10.0.0.1`      |
| 📡 Test gateway        | `ping -c 4 10.0.0.1`        | Successful replies                 |
| 🌍 Test Internet       | `ping -c 4 8.8.8.8`         | Successful replies                 |
| 🔎 Test DNS            | `nslookup networkwalks.com` | Domain resolves                    |
| 🧰 Verify Nmap         | `nmap --version`            | Nmap version displayed             |
| 📦 Check interface     | `ip link show eth0`         | Interface is UP                    |
| 🔗 Check neighbors     | `ip neigh`                  | Gateway appears in neighbor table  |

Example Verification Commands

ip -4 addr show eth0

ip route

ping -c 4 10.0.0.1

ping -c 4 8.8.8.8

nslookup networkwalks.com

nmap --version

💾 Snapshot and Backup Strategy

After completing the basic lab configuration, a clean VirtualBox snapshot should be created.

Recommended snapshot name:

Clean Kali - Network Setup

The snapshot provides a known-good recovery point.

Before performing major experiments such as:

Exploitation

Malware analysis

Network configuration changes

Security-tool testing

Vulnerability testing

a new snapshot should be created.

Important VM files should also be backed up separately when necessary.

💡 What I Learned

Through this project, I learned how to build a basic virtual cybersecurity laboratory from the ground up.

1. VirtualBox Networking

I learned how VirtualBox connects a virtual machine to a NAT Network and how the virtual network provides a gateway and DHCP service.

2. NAT Network vs NAT

I learned that a NAT Network is useful when multiple VMs need to communicate with each other while still having external network connectivity.

3. Static IP Configuration

I learned how to configure and verify:

IPv4 address

Subnet mask

Gateway

DNS

Routing

6. VM Snapshots

I learned that snapshots are useful for maintaining a clean recovery point before performing risky cybersecurity experiments.

7. Documentation

I learned that documenting the configuration, commands, screenshots, errors, and solutions is an important part of a professional cybersecurity project.

🔐 Security & Ethical Use

This laboratory is intended strictly for:

Education

Cybersecurity training

Authorized penetration testing

Security research in controlled environments

I will only test systems that I own or have explicit permission to test.

🔗 Tools & Resources

7-Zip: https://7-zip.org/download.html

VirtualBox: https://virtualbox.org/wiki/Downloads

Kali Linux: https://kali.org/get-kali

NetworkWalks: https://networkwalks.com/


# Author

Rosan Shrestha

Cybersecurity Learner | IT Engineering Graduate

Program: Cybersecurity / Ethical Hacking TrainingOrganization: NetworkWalksProject: Cybersecurity Lab Environment SetupWeek: 01

LinkedIn:

[Add your LinkedIn profile link here]
