# 🛡️ Incident-Response-Plan-and-Test
Create an Incident Response Plan and Test It

> A complete, production-grade Incident Response Plan (IRP) aligned to **NIST SP 800-61 Rev. 2**, including a full tabletop simulation of a phishing-to-data-leak incident, scored simulation results, and a completed incident report template.

---

## 📋 Overview

This repository contains the full **Information Security Incident Response framework** for **NovaStar Tech, Inc.**, a fictional 30-employee tech startup. It was built to simulate the work of a CISO and IR team responding to a real-world P1 incident — a spear-phishing attack that led to credential theft and exfiltration of 8,500 customer PII records.

---

## 📁 Repository Contents

| File | Description |
|------|-------------|
| [novastar_ir_plan.docx](https://github.com/user-attachments/files/26393503/novastar_ir_plan.docx) | Full Incident Response Plan — 10 sections including tabletop simulation and completed incident report |
| [novastar_ir_workbook.xlsx](https://github.com/user-attachments/files/26393509/novastar_ir_workbook.xlsx) | IR workbook — Tabletop Simulation scorecard + Incident Report with timeline and remediation tracking |

---

## 📄 IR Plan Document — Section Breakdown

| Section | Contents |
|---------|----------|
| 1. Purpose & Scope | Objectives, scope, severity classification (P1–P4) |
| 2. Roles & Responsibilities | IRT team structure, RACI matrix |
| 3. Detection & Analysis | Detection sources, triage checklist (7 steps) |
| 4. Containment | Short-term actions by scenario, evidence preservation requirements |
| 5. Eradication | Step-by-step process, full credential rotation checklist |
| 6. Recovery | Recovery steps, RPO/RTO targets, post-recovery monitoring |
| 7. Communications | Notification requirements with deadlines, internal/external templates |
| 8. Lessons Learned | Post-incident review process, improvement tracking table |
| 9. Tabletop Simulation | Full phishing → data leak scenario with 18-step timeline |
| 10. Incident Report Template | Completed example report for IR-2025-001 |

---

## 📊 Excel Workbook — Tab Breakdown

### 1. Tabletop Simulation
18 simulation steps across 6 phases, each scored 1–5:

| Phase | Steps | Focus |
|-------|-------|-------|
| Detection | 1–4 | SIEM alert, triage, scope, escalation |
| Containment | 5–8 | Account suspension, OAuth revocation, IP blocking, evidence |
| Eradication | 9–11 | Credential rotation, forwarding rules, AWS lateral movement check |
| Recovery | 12–13 | Account re-enable, enhanced monitoring |
| Communication | 14–15 | Exec notification, all-staff alert |
| Legal | 16–18 | Legal engagement, ICO notification, customer notification |

**Total Score: 70/90 (78%) — Needs Improvement**

### 2. Incident Report Template
Fully completed for IR-2025-001 with:
- **Section A**: Incident overview and key dates
- **Section B**: Impact assessment (data, systems, customer, regulatory, financial)
- **Section C**: Full technical timeline with IOCs and evidence references
- **Section D**: Root cause analysis using 5-Whys methodology
- **Section E**: 8 prioritised remediation actions with owners and due dates
- **Section F**: Key metrics (MTTD, MTTC, MTTR, GDPR notification timelines)

---

## 🎭 Tabletop Scenario Summary

**Incident:** Phishing → Credential Theft → Data Exfiltration  
**Severity:** P1 Critical  
**Company:** NovaStar Tech, Inc.

**Attack Chain:**
```
08:14  Spear-phishing email delivered (fake Google Security alert)
08:22  Employee enters credentials on lookalike domain
08:23  Attacker adds OAuth app; disables login notifications
08:30  Attacker locates customer_export_Q1_2025.csv (8,500 PII records)
08:45  Data exfiltrated to Tor exit node (185.220.101.47)
10:15  SIEM alert fires (1h 53m after initial access)
10:30  P1 incident declared; IRT activated
10:43  Account contained; attacker access revoked
51h    ICO breach notification filed (within 72h GDPR deadline)
```

---

## 📈 Key Metrics — IR-2025-001

| Metric | Actual | Target | Status |
|--------|--------|--------|--------|
| Mean Time to Detect (MTTD) | 1h 53m | < 30 min | ⚠️ Needs improvement |
| Mean Time to Contain (MTTC) | 13 min | < 30 min | ✅ Met |
| Mean Time to Recover (MTTR) | 3h 30m | < 8 hours | ✅ Met |
| GDPR Notification (ICO) | 51 hours | < 72 hours | ✅ Met |
| Customer Notification | 48 hours | < 72 hours | ✅ Met |
| Tabletop Score | 70/90 (78%) | ≥ 80% | ⚠️ Needs improvement |

---

## 🚨 Top Gaps Identified

| Priority | Gap | Remediation |
|----------|-----|-------------|
| CRITICAL | No hardware MFA enforced — password alone sufficient | Mandate YubiKey for all staff; stock spare keys |
| CRITICAL | 2-hour SIEM detection gap — Workspace logs pulled not pushed | Integrate via push API; target ≤5 min MTTD |
| HIGH | No DLP blocking bulk Drive exports | Deploy Workspace DLP; alert on exports > 1,000 rows |
| HIGH | No OAuth app inventory or alerting | Monthly audit; alert on new OAuth app authorisations |
| HIGH | Tor exit node blocklist not maintained | Subscribe to Tor IP feed; auto-update WAF nightly |

---

## 🗺️ IR Lifecycle (NIST SP 800-61)

```
Preparation
    └── IRP written, IRT trained, tools deployed, tabletop complete

Detection & Analysis
    └── SIEM alert → Triage → Scope → Severity rating → IC notification

Containment
    ├── Short-term: Isolate / suspend / block
    └── Long-term: Stable environment; evidence preserved

Eradication
    └── Root cause removed; credentials rotated; persistence cleared

Recovery
    └── Clean restore; enhanced monitoring; gradual service re-enable

Post-Incident Activity
    └── Lessons learned → Improvement actions → IRP updated
```

---

## 🧰 How to Use This Template

1. **Customise** the IR Plan Word doc with your company name, team names, and tool stack
2. **Update** the RACI matrix with your actual org structure
3. **Replace** the simulation scenario with one relevant to your environment
4. **Run** the tabletop with your team — score each step honestly
5. **Complete** the Incident Report template for every P1/P2 incident
6. **Track** improvement actions in Section E until closed
7. **Repeat** the tabletop every 6 months

---

## 📚 References

- [NIST SP 800-61 Rev. 2 — Computer Security Incident Handling Guide](https://csrc.nist.gov/publications/detail/sp/800-61/rev-2/final)
- [NIST SP 800-83 — Malware Incident Prevention and Handling](https://csrc.nist.gov/publications/detail/sp/800-83/rev-1/final)
- [CISA Incident Response Guidance](https://www.cisa.gov/topics/cybersecurity-best-practices/organizations-and-cyber-safety/incident-response)
- [GDPR Article 33 — Breach Notification to Supervisory Authority](https://gdpr-info.eu/art-33-gdpr/)
- [MITRE ATT&CK — Phishing Technique T1566](https://attack.mitre.org/techniques/T1566/)
- [Google Workspace Admin Audit Logs](https://support.google.com/a/answer/4579579)
- [AWS GuardDuty Findings Reference](https://docs.aws.amazon.com/guardduty/latest/ug/guardduty_findings.html)

---

## ⚠️ Disclaimer

This project is a **lab exercise** using a fictional company. It is intended for educational and training purposes. Always consult a qualified security professional when implementing a real Incident Response Plan.

---

*Built by Godwin Iduye  |  © 2025*
