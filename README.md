# OpenCode Setup

A reusable OpenCode configuration base for structured software engineering workflows.

## Goals

- Route different engineering activities to models based on capability and cost.
- Turn recurring engineering practices into reusable agents and commands.
- Keep reusable workflow policy separate from project-specific `AGENTS.md` rules.
- Make the setup portable across machines and projects.

## Workflow

```text
Goal
  -> Structure Problem
  -> Feasibility Research
  -> Roadmap
  -> Milestones
  -> Build / Scaffold
  -> Code Review
  -> Rework or Ship
```

## Agents

| Agent | Responsibility | Default model |
|---|---|---|
| `engineering-manager` | Orchestrate the workflow and delegate work | `opencode/qwen3.7-max` |
| `problem-structurer` | Turn ambiguity into a precise engineering problem | `opencode/glm-5.2` |
| `feasibility-researcher` | Evaluate approaches, constraints, dependencies and risks | `opencode/qwen3.7-max` |
| `roadmap-planner` | Convert a validated goal into an implementation roadmap | `opencode/qwen3.7-max` |
| `milestone-planner` | Break roadmap phases into executable milestones/tasks | `opencode/glm-5.2` |
| `builder` | Implement planned work and scaffolding | `opencode/deepseek-v4-flash` |
| `code-reviewer` | Independently inspect correctness, security and maintainability | `opencode/kimi-k2.7-code` |

> Model identifiers are intentionally centralized in `opencode.jsonc`. If your provider exposes a different provider/model prefix, change them there.

## Commands

- `/structure` — structure the current problem
- `/feasibility` — research technical feasibility
- `/roadmap` — create an implementation roadmap
- `/milestones` — decompose the roadmap into milestones
- `/scaffold` — implement a scaffold or planned task
- `/review` — perform a read-only code review

## Installation

This repository is intended to be used as a reusable OpenCode configuration directory. OpenCode can load global configuration from the user configuration directory, while project-specific configuration belongs in the project repository.

For a portable setup, clone this repository and point `OPENCODE_CONFIG_DIR` at it.

Example on PowerShell:

```powershell
$env:OPENCODE_CONFIG_DIR = 'D:\dev\opencode-setup'
opencode
```

## Project-specific rules

Do not put application-specific architecture, commands, or conventions in this repository. Put those in the target project's `AGENTS.md`. OpenCode loads `AGENTS.md` as project-specific instructions.

## Design principles

1. **Separate thinking from execution.** Planning agents should not edit code.
2. **Spend intelligence where it matters.** Expensive models are reserved for high-leverage reasoning.
3. **Keep implementation economical.** Routine scaffolding should use the low-cost builder.
4. **Review independently.** The reviewer should be a separate agent with no edit permission.
5. **Prefer explicit artifacts.** Each planning stage should produce a reusable, inspectable result.
6. **Keep the configuration provider-portable.** Model assignments are policy, not business logic.

## Repository status

This is the initial v1 workflow. Model assignments, prompts, permissions and output contracts should be treated as experimental until tested against real projects.
