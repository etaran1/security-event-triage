# Triage Flow (SOC Analyst)

## Severity Quick Rules
**Low**
- Single isolated event
- No privileged access
- No persistence indicators
- Likely misconfiguration or user error

**Medium**
- Repeated failures across accounts/IPs
- Suspicious but unconfirmed access
- Possible policy violation
- Needs containment steps or monitoring

**High**
- Confirmed unauthorized access
- Privileged account involvement
- Evidence of persistence, data access, or lateral movement
- Requires immediate escalation + containment

## Decision Steps
1. Identify event type (Auth, Endpoint, Network, Policy)
2. Validate context (time, user, asset, baseline behavior)
3. Determine indicators (frequency, geo/IP, process, parent process)
4. Assign severity (Low/Medium/High)
5. Action:
   - Low: document + close
   - Medium: document + contain + monitor + escalate if needed
   - High: escalate immediately + contain + preserve evidence

## Evidence Checklist
- Who/what asset?
- When did it start?
- Indicators (IOCs): IPs, users, hostnames, processes
- What changed?
- What action was taken?
- Recommended next steps
