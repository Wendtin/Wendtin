# Wend Tin Basile Sam

**Cloud Security Engineer** &nbsp;·&nbsp; New York, NY

I build AWS environments as code and then attack them to find out where they hold.
Terraform-defined infrastructure, CI/CD that reaches AWS without a stored credential,
and incident response that starts by preserving evidence instead of rebooting the box.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/wend-tin-basile-sam-35b70199/)
[![Email](https://img.shields.io/badge/Email-sw.basile14%40gmail.com-505050?style=flat-square&logo=maildotru&logoColor=white)](mailto:sw.basile14@gmail.com)
[![Portfolio](https://img.shields.io/badge/Lab%20Portfolio-24%2B%20writeups-238636?style=flat-square&logo=github&logoColor=white)](https://github.com/Wendtin/My-Portfolio)

**Currently** — TKH Innovation Fellowship 2026, Cloud Security track · CompTIA Security+ in progress
**Open to** — Cloud Security Engineer · DevSecOps Engineer · SOC Analyst

---

## Selected work

**[TLAB9-Breach](https://github.com/Wendtin/TLAB9-Breach) — cloud incident response, end to end**
An unauthorised EC2 instance appears in the account. I built the audit trail that could answer
who launched it (CloudTrail into S3, queried through Athena), contained it with a zero-rule
security group so the instance stayed intact for forensics, then revoked the principal. The
interesting failure mode: a fresh Glue table returns zero rows until `MSCK REPAIR TABLE`
registers the partitions — the difference between "no evidence" and a complete trail.
`CloudTrail` `Athena` `KMS` `EC2` `IAM`

**[TLAB7-Forge](https://github.com/Wendtin/TLAB7-Forge) — secretless CI/CD with a security gate**
GitHub Actions authenticates to AWS through OIDC federation, so there is no long-lived access
key anywhere in the repository. `tfsec` runs before Terraform and fails the job on findings
rather than reporting them afterwards — proven by committing a security group open to
`0.0.0.0/0` and confirming the deploy stopped.
`Terraform` `GitHub Actions` `OIDC` `tfsec` `IAM`

**[TLAB8-Fleet](https://github.com/Wendtin/TLAB8-Fleet) — container supply chain and least privilege**
A non-root Alpine image pushed to ECR with scan-on-push enabled, audited by a Lambda function
whose IAM policy I cut from `AdministratorAccess` down to `ecr:DescribeImages` on one repository
ARN plus its own log stream. Re-running the function afterwards confirmed the reduction did not
break the workload, which is the only way to know a least-privilege policy is correct rather
than merely small.
`Docker` `ECR` `Lambda` `Boto3` `IAM`

---

## Toolbox

| | |
|---|---|
| **AWS** | IAM · EC2 · VPC · S3 · Lambda · ECR · CloudTrail · CloudWatch · GuardDuty · Athena · Systems Manager · KMS · Config · Budgets |
| **IaC & CI/CD** | Terraform · CloudFormation · GitHub Actions · tfsec · OIDC federation |
| **Detection & SIEM** | ELK Stack · KQL · Suricata rule authoring · Sysmon · VPC Flow Logs |
| **DFIR** | Autopsy · The Sleuth Kit · Volatility · FTK Imager · Wireshark · tcpdump |
| **Offensive** | Metasploit · Burp Suite · sqlmap · nmap · LinPEAS · GTFOBins · SOCKS pivoting |
| **Frameworks** | NIST CSF 2.0 · CIS Benchmarks · MITRE ATT&CK |
| **Languages** | Python · Bash · HCL · SQL · PowerShell |

---

<details>
<summary><b>Full lab portfolio</b> — 24 labs across cloud, detection, forensics, and offensive security</summary>

<br>

Reports, scripts, and evidence live in **[My-Portfolio](https://github.com/Wendtin/My-Portfolio)**.

**Cloud security & DevSecOps**

| Lab | What I built |
|---|---|
| Budgeted Identity | AWS Budget alerts, S3, IAM role and EC2 defined entirely in Terraform |
| The Castle Walls | Two-tier VPC as code — public and private subnets with corrected routing |
| The Wiretap | VPC Flow Logs into CloudWatch, then a threat hunt across the captured traffic |
| Zero Trust Terminal | EC2 administration with no SSH and no open port 22, via Session Manager |
| Monitored Fortress | Terraform VPC + Flow Logs + zero-trust access combined |
| The Quality Inspector | SAST gate in GitHub Actions; a public-ACL S3 bucket fails `tfsec`, then is remediated with KMS encryption, versioning, public access block, and logging |
| The Traveler's Guide | Keyless OIDC federation from GitHub Actions to AWS |
| Executive Risk Translation | AWS service inventory mapped to NIST CSF 2.0 functions, written up for a non-technical board |

**Detection engineering & DFIR**

| Lab | What I built |
|---|---|
| The Central Nervous System | ELK SIEM deployment; host and network threat hunting with custom KQL |
| The Tripwire | Suricata signatures detecting reverse shells, scans, and SQLi patterns |
| Operation Fortress | Layered host defence — UFW, iptables, and Sysmon event triage |
| The Barricade | Stateful firewall rulesets with documented defence rationale |
| The Crime Scene | Disk forensics with Autopsy and Sleuth Kit; deleted-artifact recovery under chain of custody |
| The Digital Autopsy | Memory forensics with Volatility; malware artifact and volatile IOC extraction |
| Operation Phantom Pursuit | SIEM logs correlated with disk forensics to reconstruct and close an incident |

**Offensive security**

| Lab | What I built |
|---|---|
| TEPP — The Final Reckoning *(capstone)* | Four-phase pentest and incident response across segmented Docker networks |
| Operation Omni-Portal | Multi-vector web attack (SQLi + XSS + BOLA) with a CVSS-scored report |
| The Invisible Logic | BOLA/IDOR exploitation against a REST API to extract unauthorised records |
| The Poisoned Browser | Stored XSS and CSRF payload delivery; full attack chain documented |
| The Verification Protocol | RCE via the Samba username map script vulnerability (CVE-2007-2447) |
| Climbing the Ladder | Linux privilege escalation — SUID binaries, sudo misconfiguration, cron wildcard injection |
| The Deep Network | Metasploit SOCKS pivoting into an isolated internal Redis service |
| Operation Deep Pivot | Initial access → privilege escalation → persistence → pivoting |

**Networking**

Cisco Packet Tracer labs covering VLANs, routing, and access control lists.

</details>

---

## Background

| | |
|---|---|
| **B.S. Computer Science & Information Security** | John Jay College, CUNY — GPA 3.73, Dean's List |
| **A.S. Computer Science** | BMCC, CUNY |
| **TKH Innovation Fellowship 2026** | The Knowledge House, NYC — Cloud Security track |
| **Cybersecurity Tech Fellow** | CodePath (paid) — taught cybersecurity labs |
| **AWS Cloud Practitioner Essentials** | AWS Skill Builder — 13 modules, 9 SimuLearn labs |

Bilingual: English / French.
