# Flow: End-to-End Delivery (Plan → Implement → Secure → Ship)

## Goal
Deliver a feature with clear architecture, minimal diff, strong verification, and a rollback plan.

## Inputs to confirm (ask only if missing)
- Feature description and success criteria
- Target environment(s) and rollout expectations
- Risk level (auth/money/data/infra) and compliance constraints

## Orchestration steps
1) **Scope + minimal plan**
   - Restate requirements + assumptions
   - Call out risk + blast radius (infra/auth/data/money)
   - Choose the smallest design that satisfies requirements (ADR if it’s a real decision)

2) **Implementation**
   - Break work into small, reviewable steps
   - Prefer plan/diff-first changes (Terraform plan, `kubectl diff`, Helm dry-run, Argo CD diff)

3) **Domain delivery (pick what applies)**
   - Infra: AWS/Terraform/networking changes
   - Delivery: Kubernetes/Helm/GitOps/Argo CD changes
   - Platform: CI/CD + environments wiring (if needed)

4) **Security overlay (required for auth/money/PII/public exposure/production)**
   - Lightweight threat model + concrete mitigations

5) **Docs + Runbook**
   - How to verify, mitigate, and rollback

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
