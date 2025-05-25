# Brute Force Attack Detection Playbook

## Objective
Detect brute-force login attempts across network systems.

## Log Sources
- Windows Security Logs (4625, 4624)
- VPN logs
- Linux auth logs

## IOC Types
- Repeated login failures from single IP
- Abnormal geolocation login attempts

## Steps
1. Alert received: Multiple failed login attempts
2. Extract username, source IP, and timestamps
3. Correlate successful logins following failed ones
4. GeoIP lookup for source IP
5. Check login pattern across other users/systems
6. Review VPN/firewall logs for source activity

## Response Actions
- Block offending IP
- Reset credentials
- Notify affected users
- Enable MFA if not already in use

## Related MITRE TTPs
- T1110 – Brute Force
- T1078 – Valid Accounts
