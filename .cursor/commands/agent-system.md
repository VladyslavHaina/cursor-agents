# Agent System Index (AWS/EKS Platform)

## Goal
Keep a **small, low-noise** set of commands that cover the common work in this repo (AWS + Terraform + EKS/Kubernetes + GitOps), while keeping older/specialized agents archived and easy to restore.

## How to use
- Default entrypoint: start with `agent-orchestrator.md` for routing + end-to-end delivery.
- Security overlay: treat `agent-security.md` as always-in-scope when risk involves **auth, money, PII, secrets, public exposure, production**, or **agent/tooling**.

## Global guardrails
- Workspace-wide rules in `.cursor/rules/*.mdc` always apply (Plan → Execute → Verify → Summarize, smallest safe diff, secrets hygiene).

## Core agents (keep)
These are intentionally **broad**. The point is to avoid “agent sprawl”.
- `agent-orchestrator.md`: routes requests and owns end-to-end delivery.
- `agent-aws.md`: **Infra** (AWS + Terraform workflow + networking + cost/VPN guardrails).
- `agent-k8s.md`: **Delivery** (Kubernetes + Helm + GitOps/Argo CD safe operations).
- `agent-platform.md`: CI/CD + environments + secrets wiring (build/deploy).
- `agent-security.md`: security baseline + auth + secret manager integration + AI agent/tool security.
- `agent-observability.md`: **Ops** (incident triage + observability + Linux triage patterns).
- `agent-docs.md`: docs/runbooks + safe repo hygiene (moves/renames).
- `agent-mcp.md`: MCP/toolserver implementation details (optional; use when building tools, not for general security review).

## Archived (legacy / superseded by core agents)
Moved to `.cursor/commands/_archive/legacy/` to keep the command list small. Restore only when you need deep specialist guidance.
- Infra split: `agent-terraform.md`, `agent-networking.md`, `agent-finops.md`, `agent-wireguard.md`
- Delivery split: `agent-helm.md`, `agent-gitops.md`, `agent-argocd.md`
- Security split: `agent-auth.md`, `agent-agent-security.md`, `agent-cyberark-safe.md`
- Ops split: `agent-linux.md`
- Repo split: `agent-repo-structure.md`
- App/ML suites: `agent-architect.md`, `agent-backend.md`, `agent-frontend.md`, `agent-qa.md`, `agent-data.md`, `agent-mlops.md`, `agent-experimentation.md`, `agent-evaluation.md`, `agent-model-registry.md`, `agent-deployment.md`, `agent-ml-observability.md`
- Other optional: `agent-ansible.md`, `agent-postgresql.md`

## Archived (not referenced in this repo today)
Existing archive bucket: `.cursor/commands/_archive/`
- `agent-kafka.md`
- `agent-msk.md`
- `agent-flink.md`
- `agent-kafbat-ui.md`
- `agent-mongodb.md`
- `agent-docdb.md`
- `agent-bitbucket-pipelines.md` (no `bitbucket-pipelines.yml` found)

## Restore policy (safe)
- Move the file back from `_archive/...` into `.cursor/commands/`.
- Add it back to **Core agents** only if it earns its keep (used repeatedly).
