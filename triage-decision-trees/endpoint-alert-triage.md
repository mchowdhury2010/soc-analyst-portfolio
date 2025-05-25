```markdown
# Endpoint Alert Triage Decision Tree

## Use Case
Responding to suspicious endpoint behavior (EDR alerts).

## Questions to Ask:
1. Is this process spawned by a known/legit parent (e.g., explorer.exe)?
2. Does it match any known malicious behaviors (LOLbins, encoded commands)?
3. Is the hash known (VirusTotal, internal intel)?
4. Is it persistent (scheduled task, registry run key)?
5. Has the user executed similar actions before?

## Decision Tree:
- 🔍 Suspicious process? →
  - ✔ Legit parent? → Investigate further
  - ❌ Unknown parent? → Isolate host + escalate

- 🧬 Encoded command? → Decode + reverse engineer intent
- 🔁 Repeated across fleet? → IOC sweep + threat hunt

## Response
- Quarantine endpoint
- Collect memory dump (if required)
- Kill process and delete file
- Check user behavior
```
