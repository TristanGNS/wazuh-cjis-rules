# Wazuh CJIS Ruleset (wazuh-cjis-rules)

A modular, version-controlled ruleset for aligning Wazuh with the **FBI CJIS Security Policy**. This repository enables security analysts and compliance engineers to implement, track, and maintain custom Wazuh rules directly mapped to CJIS controls and their NIST 800-53 equivalents.

## 🎯 Purpose

This project bridges the gap between Wazuh’s core monitoring capabilities and the control requirements laid out in the **CJIS Security Policy v6.0**. While Wazuh does not provide native CJIS mappings, it offers powerful primitives—log analysis, file integrity monitoring, SCA, and alerting—that can be used to support technical enforcement and audit readiness.

---

## 📂 Repo Structure

```

wazuh-cjis-rules/
├── metadata/
│   └── cjis-control-map.json      # Rule-to-control mapping reference
├── rules/
│   ├── rule_100001_failed_login.xml
│   ├── rule_100002_audit_log_mod.xml
│   └── ...
├── include_rules.xml              # Main include list for ossec.conf
└── README.md

```

---

## 🧩 Features

- 📦 Modular XML rules, one per file
- 🔐 Explicit mappings to CJIS and NIST 800-53 controls
- 🛠️ Designed for external management (not bound to `local_rules.xml`)
- 🔍 Ready for Git-based change tracking and audits
- 📊 Easy to extend with tooling or dashboards

---

## 🛣️ Roadmap

| Milestone | Description | Status |
|----------|-------------|--------|
| ✅ Stage 1 | Repository scaffolding, structure design, README setup | Complete |
| 🔧 Stage 2.1 | Rule Creation – Area 1: Information Exchange | Complete |
| 🔧 Stage 2.2 | Rule Creation – Area 2: Security Awareness Training | Complete |
| 🔧 Stage 2.3 | Rule Creation – Area 3: Incident Response | In Progress |
| 🔜 Stage 3 | Build compliance dashboards and rule validation tools | Planned |
| 🧪 Stage 4 | Deploy in Wazuh test environment, validate triggers | Planned |
| 📤 Stage 5 | Develop SCA policies and reporting scripts | Planned |
| 📚 Stage 6 | Documentation & CJIS compliance mapping exports | Planned |


---

## 📌 Current Control Coverage Plan

The following CJIS requirements and NIST controls are being addressed in the initial implementation phase:

| CJIS Requirement | Control Name                                         | NIST Control | Policy Area                         |
|------------------|------------------------------------------------------|--------------|--------------------------------------|
| 5.1.1            | Information Exchange                                 | AC-21        | Area 1 – Information Exchange Ag     |
| 5.1.1            | Information Exchange                                 | SA-4         | Area 1 – Information Exchange Ag     |
| 5.1.1.1          | Information Handling                                 | PM-1         | Area 1 – Information Exchange Ag     |
| 5.1.1.1          | Incident Response Plan                               | IR-8         | Area 1 – Information Exchange Ag     |
| 5.1.1.7          | Access Agreements                                    | PS-6         | Area 1 – Information Exchange Ag     |
| 5.1.1.7          | Personnel Screening                                  | PS-3         | Area 1 – Information Exchange Ag     |
| 5.1.1.7          | Physical Access Control                              | PE-3         | Area 1 – Information Exchange Ag     |
| 5.1.2            | Risk Assessment                                      | RA-3         | Area 1 – Information Exchange Ag     |
| 5.1.2            | Continuous Monitoring                                | CA-7         | Area 1 – Information Exchange Ag     |

Each of these will be implemented with a dedicated `.xml` rule file that:
- Uses Wazuh log fields or decoders
- Emits structured alerts
- Annotates the CJIS and NIST control reference

---

## 🛠 Usage

### 1. Clone or add this as a submodule:
```bash
git clone https://github.com/YOUR_ORG/wazuh-cjis-rules.git /var/ossec/etc/cjis-rules
```

### 2. Modify `ossec.conf`:

```xml
<rules>
  <include>etc/cjis-rules/include_rules.xml</include>
</rules>
```

### 3. Restart Wazuh manager:

```bash
systemctl restart wazuh-manager
```

---

## 📜 License

MIT License — open source and contribution-friendly. Please fork and contribute!

---

## ✉️ Feedback

For questions, feature requests, or rule submissions, open an issue or pull request.

---
