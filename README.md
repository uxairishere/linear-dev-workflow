# linear-dev-workflow

A Claude Code plugin that drives a Linear ticket end-to-end — from reading the ticket to raising a PR — with human approval gates at each stage.

## What it does

Given a Linear ticket URL, the agent:

1. **Ingests** the ticket (title, description, comments, labels)
2. **Picks a skill** (debugging, brainstorming, TDD, etc.) based on ticket labels
3. **Plans** the implementation with YAGNI enforcement
4. **Implements** on an isolated branch
5. **Reviews** code against requirements, quality, and OWASP security checks
6. **Raises a PR** with a structured description linking back to the ticket

You approve or redirect at every gate. The agent never auto-advances.

## Requirements

1. **Linear MCP** — configure the [Linear MCP server](https://linear.app/settings/api) with access to your workspace
2. **Superpowers plugin** — install via:
   ```
   /plugin install superpowers@claude-plugins-official
   ```
3. **GitHub CLI** — authenticated (`gh auth login`)

## Installation

**Step 1 — Register this repo as a marketplace** (one-time, tells Claude Code where to find the plugin):

```
/plugin add marketplace linear-dev-workflow github:uxairishere/linear-dev-workflow
```

**Step 2 — Install the plugin from that marketplace:**

```
/plugin install linear-dev-workflow@linear-dev-workflow
```

## Usage

```
/linear-ticket https://linear.app/team/issue/TEAM-123/ticket-title
```
