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
| ✅ Stage 1   | Repository scaffolding, structure design, README setup                 | Complete |
| ✅ Stage 2.01 | Rule Creation – Area 1: Information Exchange                          | Complete |
| ✅ Stage 2.02 | Rule Creation – Area 2: Security Awareness Training                   | Complete |
| ✅ Stage 2.03 | Rule Creation – Area 3: Incident Response                             | Complete |
| ✅ Stage 2.04 | Rule Creation – Area 4: Auditing and Accountability                   | Complete |
| ✅ Stage 2.05 | Rule Creation – Area 5 Access Control                                 | Complete |
| 🔜 Stage 2.06 | Rule Creation – Area 6 Identification and Auth                        | In Progress |
| 🔜 Stage 2.07 | Rule Creation – Area 7 Configruation Management                       | Planned |
| 🔜 Stage 2.08 | Rule Creation – Area 8 Media Protection                               | Planned |
| 🔜 Stage 2.09 | Rule Creation – Area 9 Physical Protection                            | Planned |
| 🔜 Stage 2.10 | Rule Creation – Area 10 Systems and Communication                     | Planned |
| 🔜 Stage 2.11 | Rule Creation – Area 11 Formal Audits                                 | Planned |
| 🔜 Stage 2.12 | Rule Creation – Area 12 Personnel Security                            | Planned |
| 🔜 Stage 2.13 | Rule Creation – Area 13 Mobile Devices                                | Planned |
| 🔜 Stage 3   | Build compliance dashboards and rule validation tools                  | Planned |
| 🧪 Stage 4   | Deploy in Wazuh test environment, validate triggers                    | Planned |
| 📤 Stage 5   | Develop SCA policies and reporting scripts                             | Planned |
| 📚 Stage 6   | Documentation & CJIS compliance mapping exports                        | Planned |



---

## 📌 Current Control Coverage Plan

The following CJIS requirements and NIST controls are currently addressed in the initial implementation phase:

| CJIS Requirement | Control Name                                         | NIST Control     | Policy Area                        | Rule ID  |
|------------------|------------------------------------------------------|------------------|-------------------------------------|----------|
| 5.1.1            | Information Exchange                                 | AC-21            | Information Exchange                | 100003   |
| 5.1.1            | Information Exchange                                 | SA-4             | Information Exchange                | 100004   |
| 5.1.1.1          | Information Handling                                 | PM-1             | Information Exchange                | 100005   |
| 5.1.1.1          | Incident Response Plan                               | IR-8             | Information Exchange                | 100006   |
| 5.1.1.7          | Access Agreements                                    | PS-6             | Information Exchange                | 100007   |
| 5.1.1.7          | Personnel Screening                                  | PS-3             | Information Exchange                | 100008   |
| 5.1.1.7          | Physical Access Control                              | PE-3             | Information Exchange                | 100009   |
| 5.1.2            | Risk Assessment                                      | RA-3             | Information Exchange                | 100010   |
| 5.1.2            | Continuous Monitoring                                | CA-7             | Information Exchange                | 100011   |
| 5.2.1            | Rules of Behavior                                    | PL-4             | Security Awareness Training         | 100012   |
| 5.2.1            | Social Media & External Usage Restrictions           | PL-4(1)          | Security Awareness Training         | 100013   |
| 5.2.1.1          | Literacy Training and Awareness                      | AT-2             | Security Awareness Training         | 100014   |
| 5.2.1.1          | Incident Response Training                           | IR-2             | Security Awareness Training         | 100015   |
| 5.2.1.1          | Role-Based Training                                  | AT-3             | Security Awareness Training         | 100016   |
| 5.2.1.2          | Insider Threat Literacy Training                     | AT-2(2)          | Security Awareness Training         | 100017   |
| 5.2.1.3          | Identification & Authentication Policies             | IA-1             | Security Awareness Training         | 100018   |
| 5.3.1            | Incident Reporting                                   | IR-6             | Incident Response                   | 100019   |
| 5.3.1            | Automated Incident Reporting                         | IR-6(1)          | Incident Response                   | 100020   |
| 5.3.1            | Vulnerabilities Related to Incidents                 | IR-6(2)          | Incident Response                   | 100021   |
| 5.3.1.1.1        | Incident Response Assistance                         | IR-7             | Incident Response                   | 100022   |
| 5.3.1.1.1        | Automation Support for IR Availability               | IR-7(1)          | Incident Response                   | 100023   |
| 5.3.1.1.2        | Coordination with External Providers                 | IR-7(2)          | Incident Response                   | 100024   |
| 5.3.2            | Policy and Procedures for Incident Management        | IR-1             | Incident Response                   | 100025   |
| 5.3.2            | Incident Response Plan                               | IR-8             | Incident Response                   | 100026   |
| 5.3.2.1          | Automated Incident Handling                          | IR-4(1)          | Incident Response                   | 100027   |
| 5.3.2.1          | Incident Handling Lifecycle & Lessons Learned        | IR-4             | Incident Response                   | 100028   |
| 5.3.2.1          | Automated Tracking & Incident Analytics              | IR-5(1)          | Incident Response                   | 100029   |
| 5.3.2.1          | Continuity of Operations                             | IR-4(3)          | Incident Response                   | 100030   |
| 5.3.2.1          | Information Correlation                              | IR-4(4)          | Incident Response                   | 100031   |
| 5.3.2.1          | Dynamic Reconfiguration                              | IR-4(2)          | Incident Response                   | 100032   |
| 5.3.2.1          | Incident Monitoring                                  | IR-5             | Incident Response                   | 100033   |
| 5.3.2.2          | Audit Record Review & Reporting                      | AU-6             | Incident Response                   | 100034   |
| 5.3.3            | Incident Response Training                           | IR-2             | Incident Response                   | 100035   |
| 5.3.3            | Incident Response Testing                            | IR-3             | Incident Response                   | 100036   |
| 5.3.4            | Audit Record Retention                               | AU-11            | Incident Response                   | 100037   |
| 5.4.1            | Time Stamps in Audit Logs                            | AU-8             | Auditing and Accountability         | 100038   |
| 5.4.1            | Audit Log Storage Capacity                           | AU-4             | Auditing and Accountability         | 100039   |
| 5.4.1            | Protection of Audit Information                      | AU-9             | Auditing and Accountability         | 100040   |
| 5.4.1            | Separate Audit Log Storage                           | AU-9(2)          | Auditing and Accountability         | 100041   |
| 5.4.1            | Audit Logging Process Failure Response               | AU-5             | Auditing and Accountability         | 100042   |
| 5.4.1            | Audit Review and Alerting                            | AU-6             | Auditing and Accountability         | 100043   |
| 5.4.1            | Audit Storage Capacity Warning                       | AU-5(1)          | Auditing and Accountability         | 100044   |
| 5.4.1            | Audit Access by Subset of Privileged Users           | AU-9(4)          | Auditing and Accountability         | 100045   |
| 5.4.1            | Additional Audit Information                         | AU-3(1)          | Auditing and Accountability         | 100046   |
| 5.4.1            | Real-time Alerts on Logging Failure                  | AU-5(2)          | Auditing and Accountability         | 100047   |
| 5.4.1            | Complete Audit Log Entry Structure                   | AU-3             | Auditing and Accountability         | 100048   |
| 5.4.1            | Previous Logon Notification                          | AC-9             | Auditing and Accountability         | 100049   |
| 5.4.1            | Audit Record Generation                              | AU-12            | Auditing and Accountability         | 100050   |
| 5.4.1            | Correlation Across Audit Repositories                | AU-6(3)          | Auditing and Accountability         | 100051   |
| 5.4.1.1          | Remote Access Monitoring                             | AC-17(1)         | Auditing and Accountability         | 100052   |
| 5.4.1.1          | System Monitoring for Threats                        | SI-4             | Auditing and Accountability         | 100053   |
| 5.4.3            | Continuous Monitoring Strategy                       | CA-7             | Auditing and Accountability         | 100054   |
| 5.4.3            | Event Logging Content & Frequency                    | AU-2             | Auditing and Accountability         | 100055   |
| 5.4.1.1          | Automated Audit of Account Lifecycle Events          | AC-2(4)          | Auditing and Accountability         | 100056   |
| 5.4.3            | Automated Audit Review Integration                   | AU-6(1)          | Auditing and Accountability         | 100057   |
| 5.4.3            | Audit Reduction & Report Generation                  | AU-7             | Auditing and Accountability         | 100058   |
| 5.4.3            | Audit Record Retention Policy Enforcement            | AU-11            | Auditing and Accountability         | 100059   |
| 5.5.1            | Account Lifecycle Monitoring                         | AC-2(4)          | Access Control                     | 100060   |
| 5.5.1            | Auto-disable Expired or Inactive Accounts           | AC-2(3)          | Access Control                     | 100061   |
| 5.5.1            | Full Account Lifecycle Enforcement                   | AC-2             | Access Control                     | 100062   |
| 5.5.1            | Automated Account Management Enforcement             | AC-2(1)          | Access Control                     | 100063   |
| 5.5.1            | Temporary/Emergency Account Expiration               | AC-2(2)          | Access Control                     | 100064   |
| 5.5.1            | Termination & Offboarding Enforcement                | PS-4             | Access Control                     | 100065   |
| 5.5.2            | Logical Access Control Enforcement                   | AC-3             | Access Control                     | 100066   |
| 5.5.2            | Least Privilege Violation Detection                  | AC-6             | Access Control                     | 100067   |
| 5.5.2            | User Logout Capability Enforcement                   | AC-12(1)         | Access Control                     | 100068   |
| 5.5.2            | Discretionary Access Control Change Monitoring       | AC-3(4)          | Access Control                     | 100069   |
| 5.5.2            | Mandatory Access Control Enforcement                 | AC-3(3)          | Access Control                     | 100070   |
| 5.5.2            | Privileged Account Usage for Non-Security Functions  | AC-6(2)          | Access Control                     | 100071   |
| 5.5.2.1          | Privileged Account Lifecycle Monitoring              | AC-2(7)          | Access Control                     | 100072   |
| 5.5.2.1          | Security Function Access Monitoring                  | AC-6(1)          | Access Control                     | 100073   |
| 5.5.2.1          | Concurrent Session Limit Enforcement                 | AC-10            | Access Control                     | 100074   |
| 5.5.2.1          | Unauthorized Privileged Account Use Detection        | AC-6(5)          | Access Control                     | 100075   |
| 5.5.2.1          | Privileged Account Use in Vulnerability Scanning     | RA-5(5)          | Access Control                     | 100076   |
| 5.5.2.1          | Separation of Duties Violation Detection             | AC-5             | Access Control                     | 100077   |
| 5.5.3            | Insecure Password Practice Detection                 | IA-5(1)          | Access Control                     | 100078   |
| 5.5.4            | Login Banner Compliance Enforcement                  | AC-8             | Access Control                     | 100079   |
| 5.5.4            | Public Content Publishing Control                    | AC-22            | Access Control                     | 100080   |
| 5.5.5            | Session Lock & Inactivity Enforcement                | AC-11            | Access Control                     | 100081   |
| 5.5.6            | Remote Access Activity Monitoring                    | AC-17            | Access Control                     | 100082   |
| 5.5.6            | Central Control Point Enforcement for Remote Access | AC-17(3)         | Access Control                     | 100083   |
| 5.5.6            | Remote Privileged Command Restrictions               | AC-17(4)         | Access Control                     | 100084   |
| 5.5.6            | Automated Remote Access Monitoring                   | AC-17(1)         | Access Control                     | 100085   |
| 5.5.6            | Real-time Threat Monitoring for Remote Sessions      | SI-4             | Access Control                     | 100086   |
| 5.5.6            | Confidentiality of Remote Access Configuration       | AC-17(6)         | Access Control                     | 100087   |
| 5.5.6            | Encrypted Remote Access Enforcement                  | AC-17(2)         | Access Control                     | 100088   |
| 5.5.6.1          | External System Access Control                       | AC-20            | Access Control                     | 100089   |


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
