# Security log samples

Paired **malicious** and **benign** sample logs for 50 security log formats — 109 files
(57 malicious, 52 benign) — for testing log parsers, detection rules and
analytics. Each attack sample has a benign counterpart from the same source, so a rule can be
checked both ways: it must fire on the first and stay silent on the second.

These files are the parser test corpus of [LogTriage](https://logtriage.app). The same samples
validate every rule in the public
[LogTriage Sigma rule library](https://github.com/logtriage-cyber/logtriage-detection-rules).

## Layout

```
samples/<format>/malicious/<file>
samples/<format>/benign/<file>
manifest.json   # one entry per file: format, label, size, lines, sha256, Sigma rules that use it
manifest.csv    # the same, as CSV
```

## Formats

| Format | Category | Malicious | Benign | Field reference |
|---|---|---|---|---|
| AWS ALB / ELB | Cloud | 1 | 1 |  |
| AWS CloudTrail | Cloud | 1 | 1 | [reference](https://logtriage.app/reference/log-formats/cloudtrail/) |
| AWS Config | Cloud | 1 | 1 |  |
| AWS GuardDuty | Cloud Security | 1 | 1 |  |
| AWS Inspector v2 | Cloud Security | 1 | 1 |  |
| AWS S3 Server Access Logs | Cloud | 1 | 1 |  |
| AWS Security Hub | Cloud Security | 1 | 1 |  |
| AWS VPC Flow Logs | Cloud Network | 1 | 1 | [reference](https://logtriage.app/reference/log-formats/vpc-flow/) |
| AWS WAF | WAF | 1 | 1 | [reference](https://logtriage.app/reference/log-formats/aws-waf/) |
| Azure AD Sign-In Logs | Identity | 4 | 1 | [reference](https://logtriage.app/reference/log-formats/azure-ad-signin/) |
| Azure ARM Activity Log | Cloud | 1 | 1 |  |
| Azure NSG Flow Logs | Cloud Network | 1 | 1 |  |
| Carbon Black | EDR | 1 | 1 |  |
| CEF (Common Event Format) | Network & Firewall | 1 | 1 |  |
| Cisco ASA / FTD | Firewall | 1 | 1 |  |
| Cloudflare Logs | Network & CDN | 1 | 1 |  |
| CrowdStrike Falcon | EDR | 1 | 1 | [reference](https://logtriage.app/reference/log-formats/crowdstrike/) |
| Duo Security | Identity | 1 | 1 | [reference](https://logtriage.app/reference/log-formats/duo/) |
| Elastic Common Schema | SIEM | 1 | 1 |  |
| F5 BIG-IP ASM | WAF | 1 | 1 |  |
| FortiGate | Firewall | 1 | 1 |  |
| GCP Cloud Audit Log | Cloud | 1 | 1 |  |
| Generic CSV | Generic | 2 | 2 |  |
| GitHub Audit Log | SaaS | 1 | 1 |  |
| Google Workspace | SaaS | 1 | 1 |  |
| HAProxy | Network | 1 | 1 |  |
| IBM LEEF | SIEM | 1 | 1 |  |
| IIS W3C Extended | Web | 1 | 1 |  |
| JumpCloud Directory | Identity | 1 | 1 |  |
| Juniper SRX | Firewall | 1 | 1 |  |
| Kubernetes Audit Log | Cloud-Native | 1 | 1 | [reference](https://logtriage.app/reference/log-formats/k8s-audit/) |
| Linux audit log (auditd) | Endpoint | 1 | 1 |  |
| Linux auth.log / secure | Endpoint | 1 | 1 |  |
| Microsoft 365 Unified Audit Log | SaaS | 1 | 1 |  |
| Microsoft Defender for Endpoint | EDR | 1 | 1 |  |
| MySQL | Database | 1 | 1 |  |
| nginx / Apache Combined | Web | 4 | 2 |  |
| Okta System Log | Identity | 1 | 1 | [reference](https://logtriage.app/reference/log-formats/okta/) |
| PAN-OS Native CSV | Firewall | 1 | 1 |  |
| PostgreSQL | Database | 1 | 1 |  |
| SentinelOne | EDR | 1 | 1 |  |
| Slack Audit Log | SaaS | 1 | 1 |  |
| Snort | IDS/IPS | 1 | 1 |  |
| Suricata | IDS/IPS | 1 | 1 | [reference](https://logtriage.app/reference/log-formats/suricata/) |
| Syslog (RFC 5424 / 3164) | Network | 1 | 1 |  |
| Sysmon | Endpoint | 1 | 1 | [reference](https://logtriage.app/reference/log-formats/sysmon/) |
| Traefik | Network | 1 | 1 |  |
| Wazuh | HIDS | 1 | 1 |  |
| Windows Event Log | Endpoint | 1 | 1 | [reference](https://logtriage.app/reference/log-formats/evtx/) |
| Zeek | IDS/IPS | 1 | 1 | [reference](https://logtriage.app/reference/log-formats/zeek/) |

Field-by-field explanations of each format are at
[logtriage.app/reference/log-formats](https://logtriage.app/reference/log-formats/). To look at a
file without uploading it anywhere, drop it into the
[free in-browser analyzer](https://logtriage.app/tools/log-analyzer/).

## How the data was made

The samples are synthetic: they are written to reproduce the structure and field usage of real
exports and the shape of real attacks (password spraying, MFA bypass, privilege escalation, port
scans, web exploitation, credential dumping and more). Every public IP address has been replaced
with an address from the RFC 5737 documentation ranges (192.0.2.0/24, 198.51.100.0/24,
203.0.113.0/24), consistently across all files, so one attacker keeps one address everywhere.
Private addresses, user names and host names are fictitious.

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — use, share and adapt with attribution
to LogTriage (https://logtriage.app). See `CITATION.cff` for a citation entry.
