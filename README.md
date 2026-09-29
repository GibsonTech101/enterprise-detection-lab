# 🛡️ enterprise-detection-lab

[![Security: SIEM / Telemetry](https://img.shields.io/badge/Domain-Defensive%20Security-red.svg)](#)
[![Stack: Splunk & Sysmon](https://img.shields.io/badge/Stack-Sysmon%20%7C%20Splunk%20%7C%20AD-000000.svg)](#)
[![Framework: MITRE ATT&CK](https://img.shields.io/badge/Framework-MITRE%20ATT%26CK-orange.svg)](#)

> Blueprint and configuration repository for an enterprise threat detection and audit lab. Implements host-level instrumentation (Sysmon), automated log ingestion (Universal Forwarder), and SIEM analytics (Splunk Enterprise) targeting common adversary tradecraft.

---

### 🏛️ Architecture Overview

```ascii
[ Workstation / Endpoint ]
   │  ├── Sysmon (v4.90 Schema)  --> Filters noisy events, hashes process executions
   │  └── Splunk Universal Fwd   --> Secure forwarding over TLS / Port 9997
   ▼
[ Network Perimeter / Router ]
   │
   ▼
[ Central SIEM Server ]
   ├── Splunk Enterprise Indexer (win_telemetry)
   └── Detection Analytics & Alert Engine (SPL correlation rules)
