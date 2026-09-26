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
├── revi-systems/
│   └── AGENTS.md                     rules for Revi company and client context
├── .factory/
│   ├── hooks.json                    automatic context loading and path guards
│   ├── settings.json                 approved folders, tools, and access limits
│   ├── droids/                       specialist AI helpers, such as researchers
│   └── skills/
│       └── <task>/SKILL.md            task process and quality standard
└── <other repository>/
    ├── AGENTS.md                     rules for that repository
    └── .factory/skills/              task instructions specific to its context
```

Each folder has one instruction file, and each repository keeps its skills in
one place. A single copy means there is no second version to fall out of step.
Instructions refer to files by paths relative to the repository or the home
folder, so the same guidance works on every operating system Revi uses.

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
- Specialist helpers take on bounded research inside a larger session, so the
  main session receives findings instead of raw search results.
- Revi Ops schedules recurring context work and dispatches Ready maintenance
  tasks from the shared board. Each scheduled routine lists the skills it relies
  on, and Revi Ops checks that those skills exist and that runs load them. See
  [Routine instructions and skills](revi-ops.md#routine-instructions-and-skills).

Instruction files hold standing rules. Skills hold task methods. Hooks and
settings control when context appears and where AI may act. Keeping these roles
separate makes each kind of guidance easier to update and review.

## Where to go next

- [Map of Revi's context system](../system-map.md)
- [The knowledge vault](knowledge-vault.md)
- [The GTM component](go-to-market.md)
- [Revi Ops](revi-ops.md)
- [Context operations workflow](../workflows/context-operations.md)
