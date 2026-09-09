# Revi's go-to-market component

Revi keeps business knowledge, current GTM choices, software, and live customer
activity in separate places. Each changes on a different schedule and needs a
different owner: strategy should remain stable, experiments should change
quickly, software should stay reusable, and customer records should reflect
current activity.

This component uses two main repositories. The **GTM workspace** says what Revi
wants the component to do. The **GTM engine** checks and carries out those
instructions.

## The workspace

The workspace is Revi's current go-to-market plan. Changes to targeting,
scoring, campaigns, or outreach usually start here.

```text
revi-gtm-workspace/
├── context/                  working copies of positioning, voice, and case studies
├── declarations/             Revi's current GTM choices
│   ├── campaigns/
│   ├── crm/
│   ├── enrichment/
│   ├── icp/
│   ├── policies/
│   ├── prospecting/
│   ├── scoring/
│   ├── sequences/
│   ├── signals/
│   ├── sourcing/
│   ├── loader.yaml
│   └── providers.yaml
├── templates/
│   └── sequences/            message templates used by outreach sequences
├── ops/
│   ├── schedules.yaml        GTM-specific run schedule
│   ├── run_cycle.py          starts a complete scheduled cycle
│   └── tranche.yaml          current experiment limits and review rules
├── prompts/                  instructions for bounded AI judgment
├── .factory/skills/          interactive GTM task instructions
├── .gtm/                     run state, event history, pending work, and audit records
└── tests/                    checks for workspace-specific operating code
```

The `declarations/` folder is the core. Its files define the target segments,
buyer roles, qualification rules, data fields, campaigns, message sequences,
and safeguards. The same rules can work with different CRMs.

The `context/` folder holds working copies of stable material from the
[knowledge vault](knowledge-vault.md). AI uses these copies while preparing
work. The prose provides reference material. The declarations provide rules the
engine can run.

In this repository, `context/`, `declarations/`, `templates/`, prompts, skills,
and run state are context. The programs in `ops/` run GTM-specific routines.
The engine below is the reusable machinery that acts on those files.

The workspace instruction files explain how these parts relate. Its skills load
the process and review gates for interactive GTM work. See
[Agent instructions and controls](agent-instructions-and-controls.md).

## The engine

The engine is reusable software. It reads a workspace and checks that the files
agree. It previews changes and applies approved work to live services.

```text
revi-gtm/
├── orchestration/
│   ├── defaults/workspace/   starter structure for a new workspace
│   └── src/
│       ├── cli/              commands and output
│       ├── commands/         entry point for each GTM action
│       ├── engine/           loading, scoring, policies, plans, and run state
│       ├── providers/        connections to Attio, Instantly, Prospeo, and FullEnrich
│       └── workflows/        reusable execution sequences
└── docs/                     operating and feature documentation
```

The separation lets Revi change its target market or campaign rules while the
machinery stays stable. Provider connections contain service-specific details,
and the business rules stay portable.

## Connected GTM tools

| Tool | Role |
| --- | --- |
| Attio | Current company, person, deal, and relationship records |
| Instantly | Campaign delivery and reply activity |
| Prospeo | Company and person sourcing, plus company enrichment |
| FullEnrich | Contact information enrichment |

The workspace chooses when each provider applies. The engine performs the work
and keeps the source attached to accepted data. See
[Connected tools](connected-tools.md) for the wider context system.

## What each layer owns

| Layer | Owns |
| --- | --- |
| Knowledge vault | Stable positioning, services, voice, case studies, and the reasoning behind business decisions |
| GTM workspace | Active target market, buyer roles, scoring, campaigns, sequences, limits, and tests |
| GTM engine | Validation, previews, policy checks, execution, and audit records |
| CRM and outreach tools | Current companies, people, campaign activity, replies, and relationship state |
| Revi Ops | Recurring workflow definitions and the shared task board |

## How a change becomes action

1. A person changes a workspace declaration or template.
2. The engine checks that the workspace is internally consistent.
3. The engine produces a preview of the live changes.
4. A person reviews the decision when the action has external consequences.
5. A scheduled cycle or approved command carries out the work.
6. The engine records what it changed and routes uncertain cases for judgment.
7. Replies and results return to the CRM, experiment records, and any durable vault updates.

AI can prepare, compare, score, and recommend. A person controls major targeting
changes, sending, and durable changes to Revi's business position.

Revi Ops coordinates the GTM component in two ways. It includes recurring GTM
cycles in the workflow register, and its dispatcher runs approved GTM tasks
from the shared board. This gives operating changes and repairs a visible path
to a reviewed pull request.

## Where to go next

- [Map of Revi's context system](../system-map.md)
- [Go-to-market workflow](../workflows/go-to-market.md)
- [Revi Ops](revi-ops.md)
- [Agent instructions and controls](agent-instructions-and-controls.md)
- [Connected tools](connected-tools.md)
