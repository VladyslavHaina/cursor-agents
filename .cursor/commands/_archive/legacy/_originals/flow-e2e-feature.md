# Flow: End-to-End Feature Delivery (Architect → Implement → Secure → Ship)

## Goal
Deliver a feature with clear architecture, minimal diff, strong verification, and a rollback plan.

## Inputs to confirm (ask only if missing)
- Feature description and success criteria
- Target environment(s) and rollout expectations
- Risk level (auth/money/data/infra) and compliance constraints

## Orchestration steps
1) **Architecture**
   - Restate requirements + assumptions
   - Provide 2–3 options + tradeoffs
   - Choose a recommendation and draft ADR

2) **Implementation plan**
   - Break work into small, reviewable steps
   - Identify tests to add/adjust

3) **Backend (if applicable)**
   - Implement API/data changes with tests

4) **Frontend (if applicable)**
   - Implement UI with explicit loading/error states

5) **Security review (required for auth/money/PII)**
   - Threat model checklist + concrete mitigations

6) **Platform/Deployment (if applicable)**
   - CI/CD, env vars/secrets, deploy steps

7) **Docs + Runbook**
   - How to verify, operate, and rollback

## Output format
### Plan
### Changes
### Verification
### Rollback
### PR Summary (copy/paste)
- **What**:
- **Why**:
- **How to verify**:
- **Risk**:
- **Rollback**:
