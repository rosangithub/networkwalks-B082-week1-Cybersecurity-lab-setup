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

# Project overview
This project is about setup a small and controlled **Cybersecurity and Penetration lab environment** using  **virtual Box and Kali Linux**
The main purpose of the lab is to create a safe place where I can learn and practice cybersecurity activities such as network scanning, reconnaissance, vulnerability assessment, packet analysis, and penetration-testing techniques.

The lab uses a private VirtualBox NAT Network so that additional virtual machines can be added later and used as authorized target machines.

*Ethical Use: This lab is intended for education and authorized security testing only. I will only test systems that I own or have explicit permission to test.*

# Objectives 
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


# Purpose of the Lab

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

# Lab Architecture


