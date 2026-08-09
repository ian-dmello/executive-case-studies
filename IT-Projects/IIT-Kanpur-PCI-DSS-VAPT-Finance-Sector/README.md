# IIT Kanpur Capstone – PCI DSS & VAPT of Finance Sector Endpoint

## Overview

This project was completed as part of the **PS1 – IIT Kanpur Capstone Project on Finance Sector** through **Simplilearn**.

The project applied concepts from the cybersecurity modules to a finance-sector scenario involving a Windows 10 virtual machine that processes and stores cardholder information.

The objective was to assess the environment against relevant **PCI DSS requirements**, perform a **Vulnerability Assessment and Penetration Testing (VAPT)** exercise, identify vulnerabilities and misconfigurations, and prepare a management-oriented report containing observations, risk implications and recommendations.

The project report identifies the engagement as an assessment of a Windows 10 virtual machine within the **Cardholder Data Environment (CDE)** and directly subject to PCI DSS v4.0 requirements.

---

## Project Details

| Item | Details |
|---|---|
| **Project** | PS1 – IIT Kanpur Capstone Project on Finance Sector |
| **Platform** | Simplilearn |
| **Author** | Ian Dmello |
| **Project focus** | PCI DSS compliance, vulnerability assessment and penetration testing |
| **Environment** | Windows 10 VM + Kali Linux VM |
| **Primary security tool** | Nessus |
| **Penetration-testing framework** | Metasploit |
| **Discovery tool** | Nmap |
| **Assessment type** | VAPT / security-control assessment |
| **Report** | Detailed assessment with screenshots, observations and recommendations |

The project brief required identification of applicable PCI DSS requirements, vulnerability identification and classification, and a controlled penetration-testing exercise using Kali Linux. fileciteturn5file8L501-L516

---

# 1. Business Context

The project was framed around a finance-sector organization whose Windows 10 endpoint handled cardholder information.

Because the system was considered part of the Cardholder Data Environment, the security of the endpoint was assessed in the context of PCI DSS requirements.

The assessment therefore considered not only technical vulnerabilities but also:

- System hardening
- Secure communication
- Access and authentication controls
- Vulnerability management
- Patch management
- Attack-surface reduction
- Information disclosure
- Ongoing security testing

The final report states that the assessment focused on identifying technical vulnerabilities and misconfigurations, evaluating PCI DSS control effectiveness, and documenting observations, impact analysis and remediation recommendations. fileciteturn5file1L125-L130

---

# 2. Objectives

The project had three principal objectives:

1. **Identify the relevant PCI DSS requirements** applicable to the endpoint.
2. **Perform vulnerability assessment and classification** of the Windows 10 environment.
3. **Conduct a controlled penetration-testing exercise** and prepare a professional report documenting the work performed, observations and recommendations.

The original project brief explicitly describes these activities, including the use of Kali Linux and the preparation of a report expected from an ethical-hacking engagement. fileciteturn5file8L501-L516

---

# 3. PCI DSS Scope

The assessment considered the following PCI DSS requirements:

- **Requirement 1** – Install and maintain network security controls
- **Requirement 2** – Apply secure configurations to all system components
- **Requirement 3** – Protect stored account data
- **Requirement 5** – Protect systems and networks from malicious software
- **Requirement 6** – Develop and maintain secure systems and software
- **Requirement 11** – Regularly test security of systems and networks
- **Requirement 12** – Support information security with organizational policies and programs

The project report links these requirements to firewall and network controls, system hardening, protection of stored data, malware protection, patching, vulnerability testing and information-security governance. fileciteturn5file7L433-L466

---

# 4. Environment & Tools

The project environment included:

### Target Environment

- Windows 10 Virtual Machine
- Services and applications running on the Windows endpoint
- Network communication paths

### Security Assessment Environment

- Kali Linux Virtual Machine
- Nessus Vulnerability Scanner
- Metasploit Framework
- Nmap

The report identifies these assets and tools as being within the assessment environment. fileciteturn5file4L239-L250

---

# 5. Methodology

The work followed a structured security-assessment process.

### Phase 1 – Understand the PCI DSS requirements

The first stage involved identifying the PCI DSS requirements applicable to a system handling cardholder data.

### Phase 2 – Establish the assessment environment

The Windows 10 and Kali Linux virtual machines were prepared for the exercise.

Nessus and Metasploit were installed/configured on Kali Linux, with Nmap available for discovery where required.

### Phase 3 – Network / Host Discovery

The Windows 10 target was identified within the controlled lab environment.

### Phase 4 – Vulnerability Assessment

A Nessus vulnerability scan was performed against the Windows 10 endpoint.

The scan generated findings covering:

- SSL/TLS configuration
- SMB configuration
- ICMP behaviour
- Service detection
- OS identification
- Information disclosure
- Protocol support
- SMB versions
- TLS versions
- Other configuration and enumeration information

### Phase 5 – Vulnerability Review

The findings were reviewed in terms of:

- Severity
- Security impact
- Relevant PCI DSS control objective
- Potential attack implications
- Recommended remediation

### Phase 6 – Controlled Penetration Testing

The project brief included an exploitation exercise using Metasploit. However, the completed assessment found that the Windows 10 machine passed the **MS17-010 / EternalBlue** check.

Consequently, the final report states that **no successful exploitation was performed**, because no exploitable critical vulnerability was identified. fileciteturn5file1L89-L103

This distinction is important: the project included penetration-testing methodology and tooling, but the final result was not a successful compromise.

### Phase 7 – Reporting

The final deliverable documented:

- Scope
- Control objectives
- Findings
- Severity
- Impact
- Recommendations
- Methodology
- Screenshot evidence
- Nessus reports

---

# 6. Key Assessment Results

The executive summary reported:

> **No high or critical vulnerabilities were detected by the Nessus assessment.**

The machine also passed the **MS17-010 (EternalBlue)** check.

However, the assessment identified several medium, low and informational findings that could weaken the security posture or provide useful information to an attacker. fileciteturn5file1L89-L103

The Nessus appendix recorded **36 findings in total**, comprising:

- 0 Critical
- 0 High
- 2 Medium
- 1 Low
- 33 Informational

The two medium findings were:

1. **SSL Certificate Cannot Be Trusted**
2. **SMB Signing Not Required**

The low finding was:

3. **ICMP Timestamp Request Remote Date Disclosure** fileciteturn5file5L320-L358

---

# 7. Significant Findings

## Finding 1 – SSL Certificate Cannot Be Trusted

### Observation

The assessment identified an SSL certificate that was not issued by a trusted certificate authority.

### Risk

An untrusted certificate can weaken confidence in secure communications and potentially increase exposure to man-in-the-middle scenarios.

### Recommendation

The report recommended:

- Replacing the untrusted/self-signed certificate with a certificate issued by a recognized CA
- Ensuring the certificate chain is correctly configured
- Maintaining certificate renewal processes
- Enforcing secure HTTPS configuration

The Nessus report classified this as a **Medium** finding. fileciteturn5file0L11-L22

---

## Finding 2 – SMB Signing Not Required

### Observation

SMB signing was not required on the remote SMB server.

### Risk

The assessment noted that this configuration could allow an unauthenticated remote attacker to conduct man-in-the-middle attacks against the SMB server.

### Recommendation

The report recommended:

- Enforcing SMB signing
- Restricting SMB access
- Disabling SMBv1
- Monitoring SMB traffic for anomalies

The Nessus finding was classified as **Medium**, with a CVSS v3.0 base score of **5.3**. fileciteturn5file0L23-L50

---

## Finding 3 – ICMP Timestamp Disclosure

### Observation

The Windows host responded to ICMP timestamp requests.

### Risk

This can disclose information about the system's configured time and potentially assist reconnaissance activities.

### Recommendation

The report recommended:

- Filtering ICMP timestamp requests and replies
- Limiting ICMP responses to necessary diagnostic purposes
- Periodically reviewing firewall configuration

The Nessus finding was classified as **Low**. fileciteturn5file0L54-L63

---

## Finding 4 – SMBv1 Enabled

The assessment detected support for the deprecated **SMBv1** protocol.

The report highlighted SMBv1 as an insecure legacy protocol and recommended disabling it across the environment and reviewing systems for unsupported protocol dependencies. fileciteturn5file4L300-L309

Importantly, the assessment did **not** establish that EternalBlue was exploitable on the tested endpoint. The report explicitly records that the MS17-010 check was passed. fileciteturn5file1L89-L103

---

# 8. Information Disclosure

A significant portion of the Nessus output consisted of informational findings.

These included information relating to:

- HTTP server type and version
- Operating-system fingerprinting
- SMB/NetBIOS information
- MAC-address information
- SMB versions
- TLS versions
- Service detection
- Device type
- Protocol support

The report considered this information relevant because excessive technical disclosure can help attackers with reconnaissance and attack planning. fileciteturn5file1L97-L103

The recommendation was therefore to reduce unnecessary service banners, protocol disclosures and externally accessible enumeration information.

---

# 9. Penetration-Testing Outcome

The original project brief required identification of vulnerabilities and a controlled exploitation exercise using Kali Linux and Metasploit. fileciteturn5file2L142-L153

The completed assessment produced a more important real-world outcome:

**The anticipated critical EternalBlue vulnerability was not exploitable on the tested endpoint.**

The final report therefore did not claim a successful compromise.

Instead, it identified configuration weaknesses that could become useful enablers in a broader attack scenario, particularly:

- SMB signing not being enforced
- SMBv1 being enabled
- Untrusted SSL configuration
- Excessive information disclosure

This is an important aspect of the project because a VAPT exercise should not be presented as successful exploitation when the evidence does not support that conclusion.

---

# 10. Recommendations

The final report recommended the following remediation actions:

### Network & Protocol Security

- Enforce SMB signing
- Disable SMBv1
- Restrict unnecessary SMB access
- Review firewall and network segmentation controls
- Filter unnecessary ICMP timestamp traffic

### Secure Communication

- Replace untrusted SSL certificates
- Maintain the certificate chain of trust
- Enforce secure HTTPS configuration

### Attack-Surface Reduction

- Suppress unnecessary service banners
- Reduce protocol and version disclosure
- Limit NetBIOS and other unnecessary enumeration

### Vulnerability Management

- Establish formal patch-management processes
- Conduct regular vulnerability assessments
- Perform credentialed scans in future assessments
- Integrate remediation into vulnerability-management workflows

These recommendations were explicitly documented in the assessment report. fileciteturn5file1L107-L121

---

# 11. Skills Demonstrated

This project provided practical exposure to:

### Cybersecurity & VAPT

- Vulnerability assessment
- Penetration-testing methodology
- Security-control assessment
- Vulnerability classification
- Risk interpretation
- Remediation planning

### Compliance

- PCI DSS requirements
- Mapping technical findings to control objectives
- Cardholder Data Environment considerations
- Security governance
- Compliance-oriented reporting

### Security Tools

- Nessus
- Metasploit
- Nmap
- Kali Linux

### Operating Systems / Infrastructure

- Windows 10
- Linux
- Virtual machines
- Network discovery
- Services and protocols

### Reporting

- Executive summary preparation
- Finding documentation
- Risk/impact analysis
- Management recommendations
- Evidence and screenshot documentation
- Security assessment reporting

---

# 12. Professional Relevance

The project is particularly relevant to a professional background in **audit, risk, governance and internal controls**.

Rather than treating cybersecurity purely as a technical exercise, the project required connecting:

**Technology → Vulnerability → Risk → Compliance Requirement → Business Impact → Remediation**

That is the aspect of the project I consider most relevant to my broader professional profile.

The original project material itself emphasises that the methodology, steps followed and reporting skills are key takeaways of the exercise. fileciteturn5file1L53-L64

---

# 13. Key Learning

The most important learning from this project was that a cybersecurity assessment is not simply about finding vulnerabilities.

A useful VAPT engagement requires:

1. Understanding the business and regulatory context
2. Defining the scope
3. Identifying applicable controls
4. Assessing the technology environment
5. Validating vulnerabilities
6. Assessing potential impact
7. Distinguishing exploitable vulnerabilities from configuration weaknesses
8. Recommending practical remediation
9. Communicating the results clearly to management

This project therefore strengthened my understanding of how **cybersecurity, compliance, risk management and internal controls intersect**.

---

# 14. Project Deliverable

The completed project report contains:

- Executive Summary
- Audit Scope
- Findings and Vulnerabilities
- Work Done and Methodology
- Screenshot Evidence
- Nessus Vulnerability Reports

The report was prepared as a management-oriented assessment rather than simply a collection of technical scan outputs. fileciteturn4file0L17-L25

---

# 15. Important Scope & Evidence Note

This is a **training/capstone project conducted in a controlled virtual-machine environment**.

The assessment should therefore be understood as evidence of **hands-on learning and practical exposure**, not as a claim of production penetration-testing experience.

The project brief required the use of ethical-hacking techniques in a controlled environment, while the completed report records the actual assessment outcome. fileciteturn5file8L501-L516

I have deliberately described the result as a **VAPT and PCI DSS assessment exercise** and have not represented the exercise as a successful real-world system compromise.

---

# Summary

### Project
**IIT Kanpur Capstone – PCI DSS & VAPT of Finance Sector Endpoint**

### Focus
**PCI DSS + Vulnerability Assessment + Penetration Testing + Security Reporting**

### Environment
**Windows 10 VM + Kali Linux VM**

### Tools
**Nessus · Metasploit · Nmap**

### Key result
**No critical/high vulnerabilities identified; 36 Nessus findings, primarily configuration and information-disclosure issues.**

### Key findings
**Untrusted SSL certificate · SMB signing not required · ICMP timestamp disclosure · SMBv1 enabled · Information disclosure**

### Key professional capability
**Connecting technical cybersecurity findings to compliance requirements, risk implications and management remediation.**

---

## Learning Progression

This project forms part of my broader technology and professional-development journey:

**Internal Audit & Risk**

↓

**Data Analytics & Fraud Analytics**

↓

**Cybersecurity & PCI DSS**

↓

**Machine Learning & AI**

↓

**Applied AI / NLP**

The common thread is the ability to understand technology sufficiently to evaluate **risk, controls, governance and business impact**.


