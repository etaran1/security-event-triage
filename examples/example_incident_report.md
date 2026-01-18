# Incident Report

**Incident Title:** Brute-force login attempts + blocked RDP  
**Date/Time (local):** 2026-01-10 08:14–08:20  
**Reporter:** Emilio Tarango  
**Severity:** Medium  
**Status:** Escalated  

## Summary
Multiple failed login attempts were observed against a workstation including attempts targeting the local Administrator account. Firewall logs show repeated blocked inbound RDP attempts from the same external IP. This indicates likely credential stuffing or brute-force activity.

## Systems / Scope
- Host(s): WS-07, FW-01
- User(s): jdoe, Administrator (attempted)
- Business impact: None confirmed (blocked)

## Timeline
| Time | Event |
|------|------|
| 08:14 | Spike in 4625 failed logins for user jdoe |
| 08:16 | Failed logins targeting Administrator |
| 08:17 | Firewall blocks repeated inbound RDP attempts |

## Indicators / Evidence
- IP: 203.0.113.55
- Log sources: Windows Security (4625), Firewall blocks

## Triage Analysis
- Why suspicious: High volume, privileged account targeted, consistent source IP
- Ruled out: user typo (volume too high), internal scanner (external IP)

## Actions Taken
- Recommended block IP at perimeter
- Escalated to senior analyst for correlation across environment

## Recommendation / Next Steps
- Check if same IP hits other assets
- Review account lockout policies
- Monitor for successful auth attempts after failures
