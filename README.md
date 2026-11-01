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

- [SaaS/Hosted Platforms](#saas-products)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **[CrowdStrike Falcon Prevent](https://www.crowdstrike.com/)**  

  Cloud-native NGAV powered by the Falcon platform's lightweight sensor; uses AI and behavioral analytics to block malware, ransomware, and fileless attacks without signature updates.



- **[SentinelOne Singularity Control](https://www.sentinelone.com/)**  

  Autonomous AI-powered NGAV with behavioral AI models that detect and respond to threats in real-time; includes rollback and remote shell capabilities.



- **[Microsoft Defender Antivirus](https://www.microsoft.com/en-us/security/business/microsoft-defender)**  

  Built-in NGAV for Windows with cloud-delivered protection, behavior monitoring, and machine learning; integrated with Defender for Endpoint for EDR capabilities.



- **[Sophos Intercept X](https://www.sophos.com/)**  

  NGAV with deep learning malware detection, anti-ransomware (CryptoGuard), and exploit prevention; available in endpoint and server editions.



- **[Trend Micro Apex One](https://www.trendmicro.com/)**  

  Enterprise endpoint protection with NGAV, EDR, and XDR capabilities; includes virtual patching and application control.



- **[Carbon Black Endpoint](https://www.broadcom.com/)**  

  VMware/Broadcom's endpoint protection with behavioral detection, NGAV, and EDR capabilities; positioned for enterprise environments.



- **[Bitdefender GravityZone](https://www.bitdefender.com/)**  

  Business endpoint security with layered NGAV (machine learning, behavioral analysis, anti-exploit) and ransomware remediation.



- **[Trellix Endpoint](https://www.trellix.com/)**  

  Endpoint protection suite (formerly McAfee/FireEye) with NGAV, EDR, and threat intelligence integration.



- **[Malwarebytes Endpoint Protection](https://www.malwarebytes.com/)**  

  Endpoint security with anti-malware, anti-exploit, and ransomware mitigation; positioned for small to mid-sized teams.



- **[Cortex XDR](https://www.paloaltonetworks.com/)**  

  Palo Alto's extended detection and response platform with NGAV capabilities, behavioral analytics, and cross-domain correlation.



## Open-Source GitHub Projects



### Linux-Focused NGAV/EDR



- **[Warden](https://github.com/Spellskite-coding/Warden)**  

  The most security-hardened open-source **EDR/NGAV for Linux workstations** (Rust) . Features: **real-time fanotify-based blocking** (denies malicious file opens before execution) ; **YARA scanning**; **ransomware detection** via per-directory and global thresholds; quarantine with cross-process manifest locking; setuid-bit stripping; **hardened systemd sandboxing** (ProtectSystem=strict, NoNewPrivileges, RestrictSUIDSGID) . **Security model validated through adversarial testing**: the project documents real bypasses found and fixed—package-manager spoofing, fork-per-file ransomware across directories, unprivileged auto-quarantine bypass, and overlong-filename quarantine bypass . **Honest limitation**: **no kernel self-protection or anti-tamper**—a privileged attacker can stop it . **Best for Linux workstations** wanting hardened, inspectable protection with real forensic value—not a replacement for commercial EDR on Windows/macOS.



- **[AegorX](https://github.com/jacobtblalock3-cmd/AegorX)**  

  Linux-focused **NGAV with signatures, YARA, ML, and real-time protection** (Python, Apache-2.0) . Features: **fanotify blocking mode** (root: denies file opens until scanned) ; inotify watch mode (unprivileged: scans and quarantines) ; **signed threat feeds** (Ed25519) with YARA rules embedded and hot-reloaded; **hash-chained audit log**; terminal dashboard; systemd unit for persistent monitoring . **Best for Linux servers and workstations** wanting a scriptable, signed-feed NGAV with real-time blocking—but it is Python-based and less hardened than Warden.



- **[OTX-Sec](https://github.com/AnorialTheReal/otx-sec)**  

  Linux antivirus and threat intelligence platform (AGPL-3.0, **early alpha v0.1.1**) . Features: file/process/network monitoring; **threat intelligence lookups** (AlienVault OTX, VirusTotal, MalwareBazaar, URLHaus) ; YARA rules; hash reputation; static analysis with entropy and suspicious string detection; quarantine support; GUI event review . **Critical caveat**: "should not be used as the only antivirus solution protecting production systems" . **Best for threat intelligence enrichment** on Linux—but not production-ready for primary protection.



### Windows-Focused NGAV



- **[Amaru](https://github.com/CripterHack/Amaru)**  

  Open-source **antivirus for Windows 11** (Rust, Tauri UI) . Features: **real-time file monitoring** via `notify-rs` + ClamAV; **YARA rule engine** (custom and signed rules) ; **Radare2 static analysis** for PE headers and suspicious strings; **Windows Filtering Platform (WFP)** kernel-level file filtering; modern Tauri/Svelte UI . **Critical caveat**: "experimental, in-progress version… should not be used in production environments" . **Best for Windows 11 users** wanting a modern, Rust-powered ClamAV frontend with YARA and static analysis—but not ready for production reliance .



- **[Sentinel Antivirus](https://github.com/mukti-sys/sentinel-antivirus)**  

  Cross-platform **antivirus engine** (Python, Windows/Linux/macOS) with **YARA scanning, PE ML classifier, and kernel minifilter driver** . Features: **in-memory emulation sandbox** (<100ms, zero host risk) ; **Job Object detonation sandbox** with CPU/RAM caps; hybrid analysis (emulation first, fallback to detonation) ; interactive GUI dashboard; headless CLI; 342-test unit suite . **Best for security researchers** wanting a sandbox analysis toolkit alongside scanning—but it is a Python application, not a hardened kernel-level NGAV.



### Additional Strong Open-Source Options



- **Fibratus** — Windows-only behavioral detection engine on ETW kernel telemetry; combines behavioral rules with YARA memory scanning and Python "filaments" for custom detections . **Needs admin/SYSTEM rights**; best treated as detection engineering and forensics tooling, not a hardened production sensor .

- **Rustinel** — Cross-platform (Windows/Linux/macOS) endpoint detection agent that normalizes ETW/eBPF/Endpoint Security telemetry and evaluates Sigma rules, YARA signatures, and IOC lists; alerts written to local ECS NDJSON files (no vendor cloud) . Apache 2.0 . **Explicitly lacks kernel self-protection and anti-tamper**—a privileged attacker can stop it .

- **owLSM** — Cybereason's public research project running Sigma-like rules **inside the Linux kernel** via eBPF LSM hooks to block malicious activity in real-time . **Most production-advanced** of the three EDR projects, but prevention rules require per-environment tuning and Sigma rules do not port automatically .

- **ClamAV** — The long-standing open-source antivirus toolkit (GPL) designed primarily for **email gateway scanning**; provides a multi-threaded daemon and command-line scanner . **Not an NGAV**—it is signature-based and does not provide behavioral detection or real-time endpoint protection. The foundation from which ClamWin and Amaru build.



**Frameworks for building custom systems**: For **hardened Linux workstation protection**, Warden provides the most security-conscious open-source NGAV/EDR with real-time blocking and documented adversarial testing . For **Linux servers with signed feeds**, AegorX . For **Windows 11 with ClamAV/YARA/Radare2**, Amaru (experimental) . For **cross-platform scanning with sandbox analysis**, Sentinel Antivirus . **None of these replace CrowdStrike Falcon Prevent or SentinelOne Singularity** for enterprise endpoint protection—they are detection engineering tools and second-opinion scanners, not hardened commercial NGAV suites .



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
