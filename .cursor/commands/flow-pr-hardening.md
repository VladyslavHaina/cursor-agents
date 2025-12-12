# Flow: PR Hardening (Make It Safe to Merge)

## Goal
Increase merge confidence by tightening tests, verifying behavior, and producing a clear PR description with rollback.

## Inputs to confirm (ask only if missing)
- What changed (scope)
- Risk level (low/medium/high) and blast radius
- How it will be verified (local/stg/prod)

## Checklist
1) **Diff review**
   - No unrelated refactors
   - Smallest change that works

2) **Quality gates**
   - Lint/format
   - Unit/integration tests
   - Add/adjust tests if behavior changed

3) **Security sanity**
   - Secrets not introduced
   - Redaction intact
   - Authz checks present (if relevant)

4) **Operational readiness**
   - Logs/metrics updated if needed
   - Runbook snippet for risky changes

5) **PR description**
   - Provide a copy/paste summary including verification + rollback

## Output format
### Findings
### Recommended hardening
### Verification
### Rollback
### PR Summary (copy/paste)
- **What**:
- **Why**:
- **How to verify**:
- **Risk**:
- **Rollback**:
