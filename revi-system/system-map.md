# Map of Revi's context system

Revi's context system is distributed by design. Each kind of context has one
sensible home. The components connect through reviewed updates, working copies,
live records, and run history. Clear ownership keeps copies from drifting and
gives AI a reliable answer when sources disagree.

## The context system at a glance

| Component | What it holds or controls | The question it answers |
| --- | --- | --- |
| [Knowledge vault](components/knowledge-vault.md) | Company facts, services, case studies, research, client work, decisions, and reusable reasoning | What does Revi know, believe, and promise? |
| [GTM component](components/go-to-market.md) | A workspace for current choices and an engine that applies them | What go-to-market choices are active, and how do they become action? |
| [Agent instructions and controls](components/agent-instructions-and-controls.md) | Instruction files, skills, hooks, and settings | Which context and process should AI use, and what may it access? |
| [Revi Ops](components/revi-ops.md) | Recurring context workflows, schedules, dispatch, and the shared task board | What context work should run, and what needs review? |
| [Connected tools](components/connected-tools.md) | Shared repositories, live business records, meeting evidence, and outside data | What can AI retrieve from the tools where work happens? |

## Where each part lives

| Part | Location | Access |
| --- | --- | --- |
| This documentation | The public `revi-context-system` repository | Public, with private details removed |
| Knowledge vault | Revi's private Obsidian and Git repository | Revi and approved AI sessions |
| GTM component | Two private Revi repositories: workspace and engine | Revi and approved GTM routines |
| Agent instructions and controls | Files beside the context they govern | Loaded according to repository, folder, and task |
| Revi Ops | A private Revi repository | Revi and approved operating routines |
| Connected tools | Restricted repositories and vendor services | Limited by each person's or routine's role |

## Four distinct parts

The context system contains different kinds of files and records:

1. **Working context files** hold knowledge or current choices. These include
   vault notes, GTM declarations, message templates, skills, prompts, and
   `rhythm.yaml`.
2. **Implementation code** reads or acts on that context. The GTM engine and
   Revi Ops programs are the machinery around the business knowledge and
   choices.
3. **Live business records** hold current activity in the CRM, outreach
   platform, and publishing tools.
4. **This public documentation** explains the structure while Revi's private
   repositories and tools hold the working context.

## How the parts connect

```text
Evidence sources
       |
       v
Knowledge vault ----> GTM workspace ----> GTM engine ----> Live tools
 stable knowledge       active choices      controlled work    current activity
       ^                                      |                    |
       └──────────── reviewed learning and results ────────────────┘

Agent instructions and controls guide how AI uses each component.
Revi Ops schedules context workflows and dispatches related board work.
```

The vault provides stable business context. The GTM workspace turns part of
that context into a current operating plan. The engine checks and applies that
plan to live tools. Results come back as records, replies, run logs, and
proposed updates. Revi Ops defines shared workflows and manages work across the
shared task board. Run history and health checks support that work.

The named tool connections are:

```text
Granola -----------------> reviewed note -----------------> Knowledge vault
Prospeo + FullEnrich ----> GTM engine ----> Attio <------> Instantly
Mercury -----------------------------------------> QuickBooks Online

GitHub holds the shared repositories, change history, issues, and reviews.
```

See [Connected tools](components/connected-tools.md) for what each tool owns.

## Five types of context

Revi uses the five context types from the organizational context system guide.

| Type | Revi example | Main home |
| --- | --- | --- |
| Declarative | Company facts, CRM records, campaign state, and financial records | Vault and specialist business tools |
| Procedural | Skills, GTM rules, routine instructions, and review steps | Agent instructions and owning repository |
| Historical | Campaign events, meetings, financial activity, decisions, and run history | Connected tools, vault, and Revi Ops |
| Relational | Links among people, companies, deals, clients, and concepts | Attio and vault hubs |
| Evaluative | Qualification rules, approved examples, policies, and definitions of done | GTM workspace, skills, and vault |

Most work uses several types. An outbound message needs company facts,
prospecting steps, prior activity, account relationships, and a quality bar.

## Source ownership

Revi chooses a source based on the question being answered.

| Question | Source |
| --- | --- |
| What does Revi do and how does it describe its work? | `revi-systems/company/` in the vault |
| Which case studies support a claim? | `revi-systems/case-studies/` in the vault |
| Which market segments and buyer roles does the GTM component use? | `declarations/icp/` in the GTM workspace |
| Which campaign, score, or outreach rule is active? | `declarations/` in the GTM workspace |
| How does the GTM component execute those rules? | The GTM engine |
| Which standing instructions apply to an AI session? | The nearest `AGENTS.md` or `CLAUDE.md` file |
| How should AI perform a repeatable task? | The relevant skill |
| Which context may AI access automatically? | Repository settings and hooks |
| What recurring workflows should exist? | `rhythm.yaml` in Revi Ops |
| What work is Ready, In progress, In review, or Blocked? | The shared GitHub task board |
| What did an automation do? | The shared run history and the home component's state |
| What is the current relationship with a company or person? | The CRM |
| What was delivered or answered in an outreach campaign? | Instantly |
| What is in Revi's accounting books? | QuickBooks Online |
| What cleared through Revi's bank accounts? | Mercury |
| What was said in a meeting? | Granola |

When another component needs the same information in a different form, it
receives a **working copy**. For example, stable positioning and case-study
material from the vault also appears in the GTM workspace so AI can use it while
preparing outreach. The original source still owns the fact.

## The rule for moving context

A useful update has to land in the source that owns it.

- A reply updates the live customer record first.
- A validated change to a target segment updates the GTM workspace.
- A durable lesson about Revi's positioning updates the vault after review.
- A change to what should run updates Revi Ops and the home component's
  schedule.
- A change to how AI performs a task updates the instruction file, skill, hook,
  or setting that governs the task.

This prevents chat transcripts, reports, and generated drafts from quietly becoming unofficial sources.

## How the workflows fit

The workflow pages provide views across the same components.

| Workflow | Components it crosses |
| --- | --- |
| [Go-to-market](workflows/go-to-market.md) | Vault, GTM workspace, GTM engine, Attio, Instantly, Prospeo, FullEnrich, and Revi Ops |
| [Knowledge and content](workflows/knowledge-and-content.md) | Vault, GitHub, Granola, research sources, AI instructions, review, and publishing tools |
| [Context operations](workflows/context-operations.md) | Agent instructions and controls, Revi Ops, the owning repository, the work board, and human review |
| [Keeping context current](workflows/keeping-context-current.md) | Every component, because it routes each change back to its owner |

Together, the workflows show how Revi turns context into work and work back into better context.
