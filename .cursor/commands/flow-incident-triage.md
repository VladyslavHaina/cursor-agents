# Flow: Incident Triage (Mitigate First, Then Understand)

## Goal
Stabilize the system quickly, reduce blast radius, and capture the evidence needed for a solid postmortem.

## Inputs to confirm (ask only if missing)
- Service/component impacted
- Time window and symptoms
- Severity and user impact
- Recent changes/deploys

## Triage checklist
1) **Stabilize / mitigate**
   - Stop the bleeding (rollback, disable feature flag, scale, rate-limit)
   - Prefer reversible mitigations

2) **Establish impact**
   - What users are affected? What %? What regions?
   - SLA/SLO breach status

3) **Gather evidence**
   - Logs (with correlation IDs)
   - Metrics (latency/error/saturation)
   - Traces (hot paths)
   - Recent deploys/config changes

4) **Hypotheses → tests**
   - Form 2–3 plausible causes
   - Run minimal tests to confirm/deny

5) **Fix forward vs rollback**
   - If fix-forward is risky or slow, rollback
   - If rollback impossible, isolate and reduce blast radius

6) **Communication**
   - Short updates: what we know, what we’re doing, next update time

7) **Post-incident**
   - Write follow-ups: detection gaps, runbook gaps, permanent fixes

## Output format
### Situation
### Immediate mitigation
### Evidence
### Hypotheses
### Next actions
### Verification
### Rollback / backout
### Follow-ups
