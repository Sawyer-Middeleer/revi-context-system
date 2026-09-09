# Revi Ops

Within the context system, Revi Ops defines recurring context workflows, runs
shared maintenance routines, and manages related work around a shared GitHub
task board. This gives context work a common path from definition through
execution and human review.

Component-specific runners, such as GTM cycles, stay in their home repository.
This keeps the procedure close to the files it acts on while Revi Ops provides
one view of ownership and work in progress.

The shared board also carries broader Revi work. This page covers the part that
adds, refreshes, governs, or reviews context.

## Recurring workflows

`rhythm.yaml` lists every standing workflow across Revi. Each entry names the
owner, timing, trigger, runner, inputs, outputs, instructions, and destination.

Revi Ops stores the prompt or program for shared context routines it owns.
Examples include adding selected research to the vault, maintaining vault
structure, and turning Granola meetings into proposed notes. A
component-specific workflow points to the runner in its home repository.

Keeping these definitions in reviewed files makes recurring work inspectable.
A person can see what will run, what information it will use, and where its
result will go before the next scheduled execution.

## The shared task board

The GitHub task board is the common work queue for people and AI across all Revi
repositories. Context work on the board includes updates to knowledge,
instructions, source definitions, access rules, and maintenance workflows. A
person can see work move through:

```text
Backlog -> Ready -> In progress -> In review -> Done
                         |
                         └-------------> Blocked
```

Work reaches the board as a scoped issue or draft. When a person marks it Ready
and selects an AI executor, Revi Ops claims the task and starts the AI in the
correct repository. The AI leaves its work in a branch and pull request. Revi
Ops moves the item to In review or Blocked, and a person retains review and
merge authority.

The shared board gives people and AI the same view of priorities, ownership,
progress, and review state. It also gives work raised by a recurring workflow a
clear destination. For example, a failed check can become a visible task with
an owner and next action.

## Supporting history and health

Each recurring workflow writes a short result to shared run history. Revi Ops
uses that record to spot a failed run, a workflow that has gone quiet, or a
schedule that differs from `rhythm.yaml`.

The history supports the workflow and task-board model. It confirms whether
work ran and creates a trace for follow-up, while the workflow result or board
item remains the main operating surface.

## File structure

```text
revi-ops/
├── rhythm.yaml               list of recurring workflows across Revi
├── prompts/                  definitions for shared AI-assisted workflows
├── revi_ops/
│   ├── run_routine.py        runs a shared recurring workflow
│   ├── dispatch.py           runs Ready work from the shared task board
│   ├── sweep_prs.py          puts open pull requests into review
│   ├── drift_check.py        compares expected and observed automations
│   ├── health.py             prepares the operating health digest
│   └── lib/                  shared schedule, run-history, and health logic
└── docs/
    └── run-log.md            contract for recording every run
```

## What operational context lives here

Revi Ops gives AI and people the context needed to operate the whole:

- How a recurring context workflow runs and which component owns it
- Which tasks are in Backlog, Ready, In progress, In review, Done, or Blocked
- Which person or AI executor owns the next action
- Where each result should go
- When a recurring workflow last ran and whether it needs attention

Business knowledge stays in the [vault](knowledge-vault.md). GTM rules and GTM
run state stay in the [GTM component](go-to-market.md). Revi Ops coordinates
work across them. These boundaries let each component own its business context
while the task board gives the whole context system one operating queue.

## Where to go next

- [Map of Revi's context system](../system-map.md)
- [Context operations workflow](../workflows/context-operations.md)
- [Keeping context current](../workflows/keeping-context-current.md)
- [Agent instructions and controls](agent-instructions-and-controls.md)
- [Connected tools](connected-tools.md)
