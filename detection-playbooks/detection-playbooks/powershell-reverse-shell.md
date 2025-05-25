# PowerShell Reverse Shell Detection Playbook

## Objective
Detect and respond to PowerShell-based reverse shell attempts.

## Log Sources
- Sysmon (Event ID 1, 3)
- EDR (CrowdStrike, Defender ATP)
- Windows Event Logs (4688)

## IOC Types
- Outbound PowerShell to IP
- Base64 encoded commands
- `Invoke-Expression`, `Net.WebClient`, etc.

## Steps
1. Alert triggered: Suspicious PowerShell with network connection
2. Review parent/child process tree (e.g., cmd → powershell)
3. Decode any base64 string in command line
4. Check external IP reputation (VirusTotal/GreyNoise)
5. Check for persistence (Registry, Scheduled Task)
6. Scan host for further payloads or lateral movement

## Response Actions
- Contain host immediately
- Kill suspicious process
- Remove persistence mechanisms
- Hunt across fleet for similar behavior

## Related MITRE TTPs
- T1059.001 – PowerShell
- T1047 – Windows Management Instrumentation
