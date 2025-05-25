network-alert-triage.md
```markdown
# Network Alert Triage Decision Tree

## Use Case
Responding to alerts from IDS/IPS, firewall, or proxy.

## Questions to Ask:
1. What is the alert type (exploit, scan, malware C2)?
2. What was the destination? Internal host or external IP?
3. Is the domain/IP malicious (Reputation check)?
4. What protocol was used (HTTP, DNS, SMB)?
5. Was data exfiltration attempted?

## Decision Tree:
- 🚨 C2 beacon detected? →
  - 🔗 Known bad IP? → Block immediately
  - 🤔 Unknown? → Pivot to endpoint activity

- 🔄 Multiple internal hosts contacting same IP?
  - 📊 Lateral movement suspected → Investigate via logs

## Response
- Block external IP/domain
- Identify affected users/systems
- Capture packet data (if possible)
- Escalate to IR team
```
