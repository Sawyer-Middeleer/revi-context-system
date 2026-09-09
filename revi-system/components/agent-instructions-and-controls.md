# Agent instructions and controls

Revi keeps the rules for using and maintaining context beside the context they
govern. This lets AI load the right guidance for a repository, folder, and task
while leaving unrelated material outside the session.

This component covers six things:

| Part | Role |
| --- | --- |
| Instruction files | Explain what a repository contains, which source owns each answer, and how changes should be reviewed |
| Skills | Provide the process and quality standard for a repeatable task |
| Hooks | Load useful session context or block an action before it reaches a sensitive path |
| Settings | Define approved tools, folders, and access boundaries |
| Schedules | Start recurring context work at the agreed time or event |
| Dispatch | Starts approved board work in the repository that owns the context |

Its scope is context governance: how AI receives, uses, and changes context.

## File structure

```text
sawyerm/
├── AGENTS.md                         vault-wide context and operating rules
├── CLAUDE.md                         equivalent rules for Claude
├── revi-systems/
│   ├── AGENTS.md                     rules for Revi company and client context
│   └── CLAUDE.md                     equivalent rules for Claude
├── .factory/
│   ├── hooks.json                    automatic context loading and path guards
│   ├── settings.json                 approved folders, tools, and access limits
│   └── skills/
│       └── <task>/SKILL.md            task process and quality standard
└── <other repository>/
    ├── AGENTS.md                     rules for that repository
    ├── CLAUDE.md                     equivalent rules for Claude
    └── .factory/skills/              task instructions specific to its context
```

Equivalent files support the AI tools Revi uses. The substance stays aligned so
the same source ownership, process, and access rules apply across them.

## How guidance reaches a task

1. The instruction file for the current repository or folder loads the standing
   context rules.
2. A relevant skill adds the process and quality bar for the task.
3. Settings expose the approved repositories and connected tools.
4. Hooks add timely context or stop access to protected paths.
5. A schedule or Ready board item starts the work in the repository that owns
   the context.
6. The proposed change returns to the correct source and review path.

Progressive loading keeps the initial guidance small. AI receives broad
orientation first, then loads detailed task instructions and business context
when the work calls for them.

## What Revi uses each part for

- Vault instruction files define filing rules, source ownership, privacy
  boundaries, and pull-request review.
- GTM instruction files explain how declarations, working copies, and live
  records relate.
- Skills cover repeatable work such as adding knowledge, structuring meeting
  notes, maintaining the vault, or operating a GTM loop.
- Hooks load active work at session start and enforce protected path rules
  before a tool runs.
- Settings grant cross-repository context deliberately and keep sensitive paths
  outside approved access.
- Revi Ops schedules recurring context work and dispatches Ready maintenance
  tasks from the shared board.

Instruction files hold standing rules. Skills hold task methods. Hooks and
settings control when context appears and where AI may act. Keeping these roles
separate makes each kind of guidance easier to update and review.

## Where to go next

- [Map of Revi's context system](../system-map.md)
- [The knowledge vault](knowledge-vault.md)
- [The GTM component](go-to-market.md)
- [Revi Ops](revi-ops.md)
- [Context operations workflow](../workflows/context-operations.md)
