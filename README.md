# Awesome-Next-Generation-Antivirus-NGAV

## Top Next-Generation Antivirus (NGAV) Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Behavioral Detection, EDR-Adjacent Protection & Self-Hosted Endpoint Security*  

**Last updated: November 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Next-Generation Antivirus (NGAV)**. These tools move beyond signature-based detection to identify malicious behavior—fileless attacks, ransomware encryption patterns, exploit chains, and in-memory threats—using machine learning, behavioral analytics, and kernel-level telemetry.



**Examples** include CrowdStrike Falcon Prevent, SentinelOne Singularity Control, Microsoft Defender Antivirus, Sophos Intercept X, Trend Micro Apex One, Carbon Black Endpoint, Bitdefender GravityZone, Trellix Endpoint, Malwarebytes Endpoint Protection, and Cortex XDR (the category leaders).



**Open-source emphasis**: NGAV is a domain where open-source tooling is **experimental and fragmented, but genuinely emerging for Linux and Windows**. The strongest active projects are **Warden** (a Rust-based EDR/NGAV for Linux workstations with fanotify real-time blocking, YARA scanning, and ransomware detection—hardened through adversarial testing) , **Amaru** (a Windows 11 antivirus with Rust-native file monitoring, YARA rules, and Radare2 static analysis, though explicitly experimental) , and **Sentinel Antivirus** (a cross-platform Python scanner with YARA, PE ML classification, and sandbox analysis) . For Linux-specific NGAV, **AegorX** provides signed threat feeds, fanotify/inotify monitoring, and a terminal dashboard . The critical caveat: **no open-source project matches the integrated kernel-level self-protection and cloud-delivered ML models** of CrowdStrike Falcon or SentinelOne—Warden explicitly lacks kernel self-protection and anti-tamper, meaning a privileged attacker can stop it . Open-source NGAV is best understood as **detection engineering tooling and second-opinion scanning**, not a hardened production replacement for commercial EDR/NGAV suites .



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [Sector Overview & Market Dynamics](#sector-overview--market-dynamics)

- [SaaS/Hosted Platforms](#saashosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## Sector Overview & Market Dynamics

The global Endpoint Security and Next-Generation Antivirus (NGAV) market is valued at approximately **$18B to $23B in 2026** (projected to reach $35B–$40B+ by the early 2030s at an estimated CAGR of **9%–12%**). The sector is **moderately concentrated to oligopolistic** at the top enterprise tier—dominated by heavyweight platform players such as Microsoft, CrowdStrike, and Palo Alto Networks benefiting from strong platform integration and cloud telemetry flywheels—while remaining **moderately fragmented** across mid-market, SMB, and specialized Linux/OT infrastructure where niche NGAV and emerging open-source detection engineering agents compete.

## SaaS/Hosted Platforms

| Product | Company Size / Valuation | Starting Pricing | Free Tier / Free Trial Limits | Description |
| :--- | :--- | :--- | :--- | :--- |
| **[Microsoft Defender Antivirus](https://www.microsoft.com/en-us/security/business/microsoft-defender)** | ~$3.1T Market Cap / >$245B Rev | $3.00/user/month (Standalone Defender for Endpoint P1) | Built-in free on Windows (consumer edition); Enterprise P1/P2 has a 90-day free trial (up to 250 licenses) | Built-in NGAV for Windows with cloud-delivered protection, behavior monitoring, and machine learning; integrated with Defender for Endpoint for EDR capabilities. |
| **[Carbon Black Endpoint](https://www.broadcom.com/)** | ~$800B Market Cap (Broadcom) / ~$51B Rev | ~$26.00/endpoint/year (~$2.17/endpoint/mo) | 30-day free trial (requires enterprise partner/sales request; full feature access for test lab) | Broadcom/VMware's endpoint protection with behavioral detection, NGAV, and EDR capabilities; positioned for enterprise environments. |
| **[Cortex XDR](https://www.paloaltonetworks.com/)** | ~$115B Market Cap / ~$8B Rev | ~$70.00/endpoint/year (~$5.83/endpoint/mo MSRP) | 30-day free trial (full cloud management console and agent testing for up to 50 endpoints) | Palo Alto's extended detection and response platform with NGAV capabilities, behavioral analytics, and cross-domain correlation. |
| **[CrowdStrike Falcon Prevent](https://www.crowdstrike.com/)** | ~$75B Market Cap / ~$3.9B Rev | $8.99/device/month ($59.99/device/year for Falcon Go) | 15-day free trial (Falcon Pro/Go, full prevention access for up to 100 endpoints) | Cloud-native NGAV powered by the Falcon platform's lightweight sensor; uses AI and behavioral analytics to block malware, ransomware, and fileless attacks without signature updates. |
| **[SentinelOne Singularity Control](https://www.sentinelone.com/)** | ~$7.5B Market Cap / ~$800M Rev | $6.00/endpoint/month ($69.00/endpoint/year for Singularity Core) | 30-day free trial (includes full behavioral NGAV, autonomous mitigation, and rollback for test endpoints) | Autonomous AI-powered NGAV with behavioral AI models that detect and respond to threats in real-time; includes rollback and remote shell capabilities. |
| **[Trend Micro Apex One](https://www.trendmicro.com/)** | ~$6.5B Market Cap / ~$1.7B Rev | ~$28.50/user/year (~$2.38/user/mo) | 30-day free trial (includes complete SaaS console and protection for up to 100 seats) | Enterprise endpoint protection with NGAV, EDR, and XDR capabilities; includes virtual patching and application control. |
| **[Sophos Intercept X](https://www.sophos.com/)** | ~$4.0B Valuation (Thoma Bravo) / ~$1.2B Rev | $28.00/user/year (~$2.33/user/mo for Advanced) | 30-day free trial (full access to Sophos Central management and all Intercept X features) | NGAV with deep learning malware detection, anti-ransomware (CryptoGuard), and exploit prevention; available in endpoint and server editions. |
| **[Trellix Endpoint](https://www.trellix.com/)** | ~$1.8B Rev (Symphony Technology Group) | ~$42.00/endpoint/year (~$3.50/endpoint/mo) | 30-day free trial (guided trial with cloud ePO management for enterprise evaluation) | Endpoint protection suite (formerly McAfee/FireEye) with NGAV, EDR, and threat intelligence integration. |
| **[Malwarebytes Endpoint Protection](https://www.malwarebytes.com/)** | ~$1.5B Valuation / ~$250M Rev | $69.99/device/year (~$5.83/device/mo) | 14-day free trial (full multi-vector protection & cloud console for up to 100 devices) | Endpoint security with anti-malware, anti-exploit, and ransomware mitigation; positioned for small to mid-sized teams. |
| **[Bitdefender GravityZone](https://www.bitdefender.com/)** | ~$1.2B Valuation / ~$220M Rev | $20.99/device/year (~$1.75/device/mo for Business Security) | 30-day free trial (full GravityZone Cloud Console for up to 100 devices) | Business endpoint security with layered NGAV (machine learning, behavioral analysis, anti-exploit) and ransomware remediation. |


## Open-Source GitHub Projects

- **[osquery](https://github.com/osquery/osquery)** [![GitHub stars](https://img.shields.io/github/stars/osquery/osquery?style=social&color=white)](https://github.com/osquery/osquery/stargazers)  
  Operating system instrumentation framework (SQL-based analytics) that exposes an entire operating system as a high-performance relational database. Used extensively in endpoint security telemetry, continuous behavioral monitoring, compliance checking, and detection engines.

- **[Wazuh](https://github.com/wazuh/wazuh)** [![GitHub stars](https://img.shields.io/github/stars/wazuh/wazuh?style=social&color=white)](https://github.com/wazuh/wazuh/stargazers)  
  Open-source security platform providing unified XDR, EDR, and endpoint security. Features signature and behavioral malware detection, file integrity monitoring (FIM), anomaly detection, rootkit detection, and real-time active response actions.

- **[YARA](https://github.com/VirusTotal/yara)** [![GitHub stars](https://img.shields.io/github/stars/VirusTotal/yara?style=social&color=white)](https://github.com/VirusTotal/yara/stargazers)  
  The de facto pattern matching Swiss army knife for malware researchers, behavioral detection rules, and NGAV engines. Used across nearly every modern open-source and commercial antivirus pipeline to classify and identify malware artifacts.

- **[ClamAV](https://github.com/Cisco-Talos/clamav)** [![GitHub stars](https://img.shields.io/github/stars/Cisco-Talos/clamav?style=social&color=white)](https://github.com/Cisco-Talos/clamav/stargazers)  
  The long-standing open-source antivirus engine toolkit (GPL) designed for trojan, virus, and malware detection; provides a multi-threaded daemon, command-line scanner, and signature database serving as foundational scanning plumbing for higher-level security tools.

- **[Tracee](https://github.com/aquasecurity/tracee)** [![GitHub stars](https://img.shields.io/github/stars/aquasecurity/tracee?style=social&color=white)](https://github.com/aquasecurity/tracee/stargazers)  
  Linux runtime security and behavioral detection engine powered by eBPF. Captures kernel-level system events and evaluates threat signatures and MITRE ATT&CK behaviors in real time to detect malware, container breakouts, and suspicious process executions.

- **[Velociraptor](https://github.com/Velocidex/velociraptor)** [![GitHub stars](https://img.shields.io/github/stars/Velocidex/velociraptor?style=social&color=white)](https://github.com/Velocidex/velociraptor/stargazers)  
  Advanced digital forensics and endpoint incident response (DFIR) platform with continuous endpoint monitoring capabilities, endpoint telemetry collection, and deep VQL-based forensic investigation queries.

- **[OpenEDR](https://github.com/ComodoSecurity/openedr)** [![GitHub stars](https://img.shields.io/github/stars/ComodoSecurity/openedr?style=social&color=white)](https://github.com/ComodoSecurity/openedr/stargazers)  
  Full-featured open-source endpoint detection and response agent (Windows/Linux) that continuously analyzes behavioral telemetry, process creation, file modifications, and network connections to detect evasive malware and fileless attacks.

- **[Fibratus](https://github.com/rabbitstack/fibratus)** [![GitHub stars](https://img.shields.io/github/stars/rabbitstack/fibratus?style=social&color=white)](https://github.com/rabbitstack/fibratus/stargazers)  
  Windows-only behavioral detection and kernel event-driven monitoring engine on ETW (Event Tracing for Windows); combines behavioral rules with YARA in-memory scanning, filament-based Python detection logic, and process execution tracking.

- **[Rustinel](https://github.com/Karib0u/rustinel)** [![GitHub stars](https://img.shields.io/github/stars/Karib0u/rustinel?style=social&color=white)](https://github.com/Karib0u/rustinel/stargazers)  
  Cross-platform (Windows/Linux/macOS) endpoint detection agent written in Rust that normalizes ETW, eBPF, and Endpoint Security telemetry and evaluates Sigma rules, YARA signatures, and IOC lists, outputting alerts locally in ECS NDJSON format without cloud reliance.

- **[owLSM](https://github.com/Cybereason-Public/owLSM)** [![GitHub stars](https://img.shields.io/github/stars/Cybereason-Public/owLSM?style=social&color=white)](https://github.com/Cybereason-Public/owLSM/stargazers)  
  Kernel-level behavioral prevention research project running Sigma-like behavioral rules directly inside the Linux kernel via eBPF LSM (Linux Security Modules) hooks to proactively block malicious operations in real time.

- **[Warden](https://github.com/Spellskite-coding/Warden)** [![GitHub stars](https://img.shields.io/github/stars/Spellskite-coding/Warden?style=social&color=white)](https://github.com/Spellskite-coding/Warden/stargazers)  
  Hardened open-source EDR/NGAV for Linux workstations (Rust) featuring real-time fanotify-based execution blocking (denies malicious file opens before execution), YARA rule scanning, heuristic ransomware detection via directory encryption thresholds, and hardened systemd sandboxing.

- **[Amaru](https://github.com/CripterHack/Amaru)** [![GitHub stars](https://img.shields.io/github/stars/CripterHack/Amaru?style=social&color=white)](https://github.com/CripterHack/Amaru/stargazers)  
  Open-source antivirus for Windows 11 (Rust with Tauri GUI) utilizing real-time file monitoring, YARA rule matching, Radare2 static analysis for PE headers/suspicious strings, and Windows Filtering Platform (WFP) kernel-level file filtering.

- **[Sentinel Antivirus](https://github.com/mukti-sys/sentinel-antivirus)** [![GitHub stars](https://img.shields.io/github/stars/mukti-sys/sentinel-antivirus?style=social&color=white)](https://github.com/mukti-sys/sentinel-antivirus/stargazers)  
  Cross-platform modular antivirus engine (Python, Windows/Linux/macOS) featuring YARA rules, PE machine learning classifiers, sub-100ms in-memory emulation sandboxing, Job Object detonation sandboxing, and interactive management dashboards.

- **[OTX-Sec](https://github.com/AnorialTheReal/otx-sec)** [![GitHub stars](https://img.shields.io/github/stars/AnorialTheReal/otx-sec?style=social&color=white)](https://github.com/AnorialTheReal/otx-sec/stargazers)  
  Linux antivirus and threat intelligence enrichment platform providing file/process/network monitoring, AlienVault OTX, VirusTotal, and MalwareBazaar lookups, static PE entropy scanning, and GUI threat review.

- **[AegorX](https://github.com/jacobtblalock3-cmd/AegorX)** [![GitHub stars](https://img.shields.io/github/stars/jacobtblalock3-cmd/AegorX?style=social&color=white)](https://github.com/jacobtblalock3-cmd/AegorX/stargazers)  
  Linux-focused NGAV with signature scanning, YARA, ML, and real-time fanotify blocking mode, accompanied by Ed25519-signed threat feeds, hash-chained audit logging, and terminal dashboards.


## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- NGAV platforms handling endpoint security must comply with organizational security policies; **open-source NGAV tools are experimental and explicitly not production-ready**—Amaru warns against production use , OTX-Sec says it should not be the only antivirus , and Rustinel lacks kernel self-protection . **Do not rely on any open-source NGAV as your sole endpoint protection.**

- **Open-source NGAV is fundamentally limited compared to commercial EDR/NGAV**—no open-source project matches the integrated kernel-level self-protection, anti-tamper, and cloud-delivered ML models of CrowdStrike Falcon or SentinelOne. **Warden explicitly documents that a privileged attacker can stop it** . Choose open-source NGAV for detection engineering, second-opinion scanning, and Linux-specific hardening—not as a replacement for enterprise endpoint protection.

- Verify license terms for commercial use; Warden is open-source (check repository) , Amaru is open-source (check repository) , AegorX uses Apache-2.0 , and OTX-Sec uses AGPL-3.0 .



---



**Made for security engineers, detection engineers, and teams exploring open-source endpoint protection.**  

Let's make NGAV more open, but with clear eyes about the experimental status and kernel self-protection gaps that separate these tools from commercial endpoint security.
