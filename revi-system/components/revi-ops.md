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

Revi Ops stores the instructions or program for shared context routines it
owns. Examples include adding selected research to the vault, turning Granola
meetings into proposed notes, preparing pages for the people in the day's
meetings, and proposing vault updates from recent work sessions. A
component-specific workflow points to the runner in its home repository.

Keeping these definitions in reviewed files makes recurring work inspectable.
A person can see what will run, what information it will use, and where its
result will go before the next scheduled execution.

## Routine instructions and skills

Each shared routine keeps its instructions in one folder named after its entry
in `rhythm.yaml`. The folder holds the main instructions for the AI, any smaller
instructions used at specific steps, and, when the routine uses one, the typed
questions it asks a decision model. Contracts for how a routine behaves, such as
what every run must record, live in the code that enforces them rather than in
separate documents that can drift.

A **skill** is a reviewed, reusable method for a task, such as filing a note or
linking to existing pages. A routine may rely only on skills stored in the
repository it runs in, never on one person's machine. Its `rhythm.yaml` entry
lists those skills. An automated check keeps that list equal to the skills the
routine's instructions name, and the run history records which skills each run
actually loaded. The health check flags a listed skill that runs have stopped
loading, and an inventory shows which routines depend on each skill.

This makes "which process does this automation follow?" something Revi can
check, not assume.

## Typed judgment

Some routines need a judgment call before any AI writes anything, such as which
work sessions contain a decision worth keeping. For these, Revi asks a decision
model (TypeSafe's Jev) narrow questions about data that has already been
reduced and stripped of credentials. Each question has a yes/no or pick-one
answer, and the model returns a probability rather than prose.

The program owns every threshold and every action. It decides what counts as
a strong enough answer, what the AI may see, and what happens next. After the
AI proposes a change, a final check returns anything outside the routine's
limits to draft before a person reviews it.

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

Each recurring workflow writes a short result to shared run history, including
runs that had nothing to do. The outcome separates an idle run, work that did
not land, a run that was stopped partway, and a crash. When AI did the work, the
record points to the AI session and the skills it loaded. Revi Ops uses that
record to spot a failed run, a workflow that has gone quiet, a missing or unused
skill, or a schedule that differs from `rhythm.yaml`.

The history supports the workflow and task-board model. It confirms whether
work ran and creates a trace for follow-up, while the workflow result or board
item remains the main operating surface.

## File structure

```text
revi-ops/
├── rhythm.yaml               list of recurring workflows across Revi
├── instructions/
│   └── <workflow>/           one folder per workflow in rhythm.yaml
│       ├── prompt.md         main instructions for the AI
│       ├── <step>.md         smaller instructions used at specific steps
│       └── jev.json          typed questions for the decision model, when used
├── ops/
│   ├── core/
│   │   ├── run_routine.py    runs a shared recurring workflow
│   │   ├── dispatch.py       runs Ready work from the shared task board
│   │   ├── sweep_prs.py      puts open pull requests into review
│   │   ├── drift_check.py    compares expected and observed automations
│   │   ├── health.py         prepares the operating health digest
│   │   └── skills.py         shows which routines depend on each skill
│   ├── routines/             code for workflows that need more than instructions
│   └── lib/                  shared schedule, run-history, skill, and decision logic
└── logs/runs/                append-only run history
```

## What operational context lives here

Revi Ops gives AI and people the context needed to operate the whole:

- How a recurring context workflow runs and which component owns it
- Which instructions and skills each recurring workflow relies on
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
