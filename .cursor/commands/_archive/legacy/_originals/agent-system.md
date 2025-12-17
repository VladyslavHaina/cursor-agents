# Agent System Index (AWS/EKS Platform)

## Goal
Provide a cohesive, low-noise set of agents with clear separation of duties, consistent safety gates, and predictable verification/rollback.

## How to use
- Default entrypoint: start with `agent-orchestrator.md` for routing + end-to-end execution.
- Security overlay: treat `agent-security.md` and `agent-agent-security.md` as always-in-scope when risk involves **auth, money, PII, secrets, or production**.

## Global guardrails
- Workspace-wide rules in `.cursor/rules/*.mdc` always apply (Plan → Execute → Verify → Summarize, smallest safe diff, secrets hygiene).

## Core agents (keep)
These match what is actually present in this repo (AWS/EKS/Terraform/K8s/GitOps):
- `agent-orchestrator.md`: routes requests to the right specialists; owns end-to-end delivery.
- `agent-security.md`: security baseline assistant (threat model, approvals, least privilege).
- `agent-agent-security.md`: AI agent security guardrails (prompt injection, exfiltration, tool/RBAC).
- `agent-aws.md`: AWS infrastructure delivery (EKS-focused; Terraform-as-source-of-truth).
- `agent-terraform.md`: plan-first Terraform workflows; state safety + break-glass rules.
- `agent-networking.md`: connectivity auditor (VPC + EKS, SG/NACL/routes/NetworkPolicy).
- `agent-k8s.md`: Kubernetes SRE SafeOps (kubectl + multi-tenant safety).
- `agent-helm.md`: Helm safe upgrades (dry-run/diff/--wait/--atomic + rollback).
- `agent-gitops.md`: Git-as-source-of-truth workflows and environment promotion.
- `agent-argocd.md`: Argo CD app/project/sync/prune guardrails; rollback-by-git-revert.
- `agent-observability.md`: logs/metrics/traces/alerts + runbooks.
- `agent-platform.md`: CI/CD, environments, reproducible builds, secrets wiring.
- `agent-repo-structure.md`: safe moves/renames and repo layout discipline.
- `agent-docs.md`: runbooks/ADRs with verify/rollback snippets.
- `agent-linux.md`: host-level debugging and safe changes.
- `agent-wireguard.md`: WireGuard topology/routing/firewall safe rollouts (repo has a WireGuard Terraform module).
- `agent-finops.md`: cost controls (optional but generally useful).
- `agent-mcp.md`: MCP/toolserver/agent template design (repo has kagent/tooling).

## MLOps suite (keep if you are actively running ML lifecycle work)
- `agent-mlops.md`: MLOps supervisor (routes to the below; enforces gates).
- `agent-data.md`: data pipelines/schemas/privacy (no training/deploy).
- `agent-experimentation.md`: training/tuning + MLflow logging (no deploy).
- `agent-evaluation.md`: evaluation/fairness reporting (no promotion/deploy).
- `agent-model-registry.md`: versioning/model cards/promotion gates (no deploy).
- `agent-deployment.md`: deploy approved models to Kubernetes with canary/rollback.
- `agent-ml-observability.md`: read-only drift/latency/error monitoring for model services.

## App engineering suite (optional)
Keep if you regularly change application code in this repo:
- `agent-architect.md`, `agent-backend.md`, `agent-frontend.md`, `agent-qa.md`, `agent-auth.md`

## Archived (not referenced in this repo today)
Based on a workspace scan, these domains had **no footprint** in the current code/infra, so they were moved to:

` .cursor/commands/_archive/ `

- `agent-kafka.md`
- `agent-msk.md`
- `agent-flink.md`
- `agent-kafbat-ui.md`
- `agent-mongodb.md`
- `agent-docdb.md`
- `agent-bitbucket-pipelines.md` (no `bitbucket-pipelines.yml` found)

## Restore policy (safe)
If any of these become relevant later, move them back from `.cursor/commands/_archive/` into `.cursor/commands/` and re-add them to the appropriate tier above.
