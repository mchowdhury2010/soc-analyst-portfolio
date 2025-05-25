# Phishing Detection Playbook

## Objective
Identify and triage potential phishing emails targeting end-users.

## Log Sources
- Email Gateway (Proofpoint, O365, etc.)
- DNS Logs
- Endpoint logs (EDR)

## IOC Types
- Malicious URLs
- Spoofed email domains
- Suspicious attachments (e.g., .html, .hta)

## Steps
1. Alert received: Suspicious email detected
2. Extract indicators (sender, subject, URLs)
3. Use VirusTotal, URLScan.io, AnyRun to analyze links
4. Check if other users received same email
5. Query for clicked links in proxy/DNS logs
6. Pull email headers, analyze SPF/DKIM
7. Search for credential use in logs

## Response Actions
- Block sender/IP/URL
- Reset credentials if login observed
- Remove email from inboxes
- Update blocklists

## Related MITRE TTPs
- T1566.001 – Spearphishing Attachment
- T1566.002 – Spearphishing Link
