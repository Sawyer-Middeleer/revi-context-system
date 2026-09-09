# How Revi's context system works

Revi's context system connects repositories and business tools that hold
knowledge, control recurring work, and record what happened.

The pages cover two kinds of information:

- **Components** are the places where context lives or recurring work is
  controlled.
- **Workflows** are the paths work takes through those components.

> **This folder is public documentation.** The private repositories and
> business tools described below contain Revi's working context.

Start with the [map of Revi's context system](system-map.md). It shows how the
parts fit together and which questions each component answers.

## What is in this section

```text
revi-system/
├── README.md
├── system-map.md
├── components/
│   ├── knowledge-vault.md
│   ├── go-to-market.md
│   ├── revi-ops.md
│   ├── agent-instructions-and-controls.md
│   └── connected-tools.md
└── workflows/
    ├── go-to-market.md
    ├── knowledge-and-content.md
    ├── context-operations.md
    └── keeping-context-current.md
```

### Components

- [The knowledge vault](components/knowledge-vault.md) holds durable business
  knowledge, research, decisions, and reusable reasoning.
- [The go-to-market component](components/go-to-market.md) turns Revi's market
  choices into testable rules and controlled action.
- [Revi Ops](components/revi-ops.md) defines recurring workflows, runs shared
  context routines, and manages related work around the shared task board.
- [Agent instructions and controls](components/agent-instructions-and-controls.md)
  define how AI finds context, follows a process, and stays within approved
  access.
- [Connected tools](components/connected-tools.md) hold live business records,
  meeting evidence, and outside data used by the other components.

### Workflows

- [Go-to-market](workflows/go-to-market.md) shows how Revi chooses a test, finds
  the right companies and people, sends with approval, and learns from replies.
- [Knowledge and content](workflows/knowledge-and-content.md) shows how an input
  becomes durable knowledge or published work.
- [Context operations](workflows/context-operations.md) shows how recurring and
  one-off context work is defined, run, reviewed, and improved.
- [Keeping context current](workflows/keeping-context-current.md) shows how
  changes move back into the right source.

## How to read this example

Read the context system map first. Open a component page to see what a repository
contains. Open a workflow page to see how the components produce an outcome.

The public example shows Revi's real structure with private client information, credentials, and sensitive records removed.
