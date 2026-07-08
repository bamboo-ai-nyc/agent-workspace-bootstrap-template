# Bamboo Agent Workspace Bootstrap

This is the private, dedicated GitHub repo Bamboo's marketing agents work in — the
"marketing agent's context." It holds the org knowledge, brand knowledge, and agent
setup Bamboo uses to manage, measure, and improve the performance of your marketing
agents in Claude. It does not touch your product code, your other repos, or your
broader GitHub org.

It is intentionally small and inspectable. It contains repo structure, placeholder
configuration, and baseline instructions only — no secrets, no customer data, no
Bamboo release internals.

## Why a separate repo

Marketing teams are increasingly becoming marketing engineers — using Claude and
Bamboo to run agents that need durable, versioned context (brand facts, goals,
playbooks, competitors) the same way engineering teams version code. GitHub is the
natural home for that: it's where changes get reviewed, where history lives, and
where your existing access-control model already works. This repo is that home for
your marketing agents' context specifically, kept separate from your engineering repos.

## Enterprise Install Model

Use this template to create a private repo in your own GitHub org, then install the
Bamboo GitHub App scoped only to that repo.

Recommended flow:

1. Create a private repo from this template, for example `marketing-agent-workspace`.
2. Review the contents of the repo before granting Bamboo access.
3. Install the Bamboo GitHub App with selected-repository access to only that repo.
   The app asks for permissions scoped to that one repo — to read and write it —
   which is what lets Bamboo manage, measure, and auto-improve your marketing
   agents' context.
4. Bamboo applies the current private release template into the repo by PR or
   direct merge, depending on your workspace policy.
5. Your team reviews future Bamboo changes as pull requests unless you explicitly
   enable optional branch-protection bypass.

This gives Bamboo access to the dedicated marketing workspace only. Bamboo does not
need access to product repos, engineering repos, or your full GitHub org.

## What Bamboo Adds Later

After the App is installed, Bamboo maintains this workspace from its private release channel:

- plugin marketplace files
- Bamboo MCP wiring
- skills and sub-agents
- template migrations
- dashboard/control artifacts
- guard scripts and workspace checks

Those operational assets are kept out of this public bootstrap repo so customers can inspect the trust boundary without exposing Bamboo internal release mechanics.

## Structure

```text
.
├── AGENTS.md
├── CLAUDE.md
├── bamboo-workspace.yml
├── org/
│   ├── knowledge/
│   └── memory/
└── brands/
```

`CLAUDE.md` and `AGENTS.md` are baseline org-level instructions. Bamboo will add brand and agent folders under `brands/` during setup.

## No Secrets

Do not commit API keys, OAuth tokens, credential files, or customer secrets. Bamboo stores connector credentials in the Bamboo platform, not in this repo.

