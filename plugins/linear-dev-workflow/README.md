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

## Installation

```
/plugin add marketplace linear-dev-workflow github:uxairishere/linear-dev-workflow
/plugin install linear-dev-workflow@linear-dev-workflow
```

## Usage

```
/linear-ticket https://linear.app/team/issue/TEAM-123/ticket-title
```

## Requirements

- [Linear MCP](https://github.com/anthropics/claude-plugins-official) configured with access to your workspace
- `gh` CLI authenticated (`gh auth login`)
- [Superpowers plugin](https://github.com/anthropics/claude-plugins-official) installed
