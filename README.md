# Experimental Evaluation of an IPsec-Based VPN

## 📋 About This Project

This repository contains a **Report** for the Advanced Topics in Networks* course (Master in Network and Information Systems Engineering, U.Porto), focused on the implementation and experimental evaluation of an **IPsec-based VPN** across site-to-site and remote access deployment scenarios, using **GNS3** for network virtualization.

## 📁 Repository Structure
├── config-files/    # IPsec/router/client configuration files used in the experiments
└── report-tar.pdf       # Full experimental report

### 🎯 Objectives

- Implement and configure secure VPN tunnels using **IPsec** in a controlled, virtualized environment.
- Validate tunnel functionality (IKE/IPsec Security Associations).
- Evaluate the **performance impact** of IPsec (throughput, latency, overhead, fragmentation) across different configurations.

### 🌐 Deployment Scenarios

1. **Site-to-Site VPN** — Two gateway routers (Cisco IOS) connected via IPsec tunnel mode, using **IKEv1 Main Mode**, **AES-128**, **SHA-1**, and Pre-Shared Key authentication.
2. **Remote Access VPN (vpnc)** — A remote Linux host connecting to a Cisco IOS gateway via **IKEv1 Aggressive Mode**, with **XAUTH** user authentication (fallback to DES due to client compatibility).
3. **Remote Access VPN (StrongSwan)** — A modern alternative using **IKEv2**, **AES-256**, **SHA-256**, **PKI certificate** server authentication, and **EAP-MSCHAPv2** user authentication.

### 🔍 What's Inside the Report

- **VPN & IPsec Fundamentals** — Tunneling mechanisms, deployment models, AH vs. ESP, transport vs. tunnel mode, Security Associations, and anti-replay protection.
- **Experimental Setup** — GNS3 topologies, addressing schemes, and full router/client configuration (ISAKMP policies, transform sets, crypto maps, StrongSwan `swanctl.conf`).
- **Tunnel Validation** — Verification of IKE/IPsec SAs via `show crypto isakmp sa`, `show crypto ipsec sa`, and `swanctl --list-sas`.
- **Performance Evaluation:**
  - **Throughput** (TCP/UDP via `iperf3`)
  - **Tunnel establishment time** (cold start vs. warm start)
  - **ESP packet overhead** (68 / 52 / 72 bytes depending on scenario)
  - **RTT by packet size** and the impact of **packet fragmentation**
- **Comparative Analysis** — Site-to-site vs. remote access, and vpnc vs. StrongSwan across security and performance dimensions.


*Report developed for the Advanced Topics in Networks course, Master in Network and Information Systems Engineering, Universidade do Porto.*
