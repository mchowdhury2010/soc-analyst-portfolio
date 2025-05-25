phishing-alert-triage.md
```markdown
# Phishing Alert Triage Decision Tree

## Use Case
Handling alerts for suspicious emails reported by users or filtered by gateway.

## Questions to Ask:
1. Does the email contain a link or attachment?
2. Is the sender spoofed or suspicious?
3. Are others reporting the same email?
4. Is the link active/malicious (URLScan.io, VT)?
5. Did the user click or enter credentials?

## Decision Tree:
- 📧 Phishing alert received →
  - 🔍 Suspicious link/attachment? → Analyze IOC
  - 🧑‍🤝‍🧑 Multiple recipients? → Tenant-wide sweep

- 🔗 User clicked? → Check DNS, proxy, and login activity
- 💥 Credentials used? → Reset + monitor for abuse

## Response
- Quarantine message
- Notify affected users
- Block domains/IPs/attachments
- Add rules to spam filter
```
