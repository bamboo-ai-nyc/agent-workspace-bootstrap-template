---
type: org_instructions
---

# Bamboo Agent Workspace

This is the root of your organization's Bamboo marketing agent workspace.

This file mirrors `CLAUDE.md` for agents and editors that read the `AGENTS.md` convention. Keep both files aligned when making manual edits.

## Org-wide Rules

Replace this placeholder with rules that apply across every brand and agent, such as:

- naming conventions for campaigns, audiences, and assets
- default reporting windows
- escalation paths
- pricing, discount, and promotion policy
- definitions that should be consistent across brands

If a rule only matters for one brand, keep it in that brand's folder. If it only matters for one agent, keep it in that agent's folder.

## Workspace Layout

- `org/knowledge/` — durable org-level facts and policies
- `org/memory/` — agent-written working memory at org scope
- `brands/` — brand and agent folders added by Bamboo

## Secrets

Do not store secrets in this repo. API keys, OAuth tokens, and connector credentials live in Bamboo's managed credential store.

