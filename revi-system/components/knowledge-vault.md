# Revi's knowledge vault

Revi uses an Obsidian vault as its main home for durable knowledge and business
reasoning. Obsidian is the reading and linking interface. Underneath it, the
vault is a version-controlled collection of Markdown files. Plain text makes
the knowledge easy for AI to read, while version history makes every accepted
change reviewable.

The vault is broader than Revi. It also holds Sawyer's research, notes, and
personal knowledge. Revi's company material has a defined area inside it. This
keeps company context navigable while still connecting it to useful research
and entity pages elsewhere in the vault.

## File structure

`revi-systems/` is Revi's working context. The research, hub, article, and daily
note areas serve the wider vault. `__inbox/` is temporary intake. Personal
folders sit outside this public view.

```text
sawyerm/
├── AGENTS.md                 instructions for AI working in the vault
├── revi-systems/             REVI WORKING CONTEXT
│   ├── _index.md             human-facing entry point
│   ├── company/
│   │   ├── about.md
│   │   ├── positioning.md
│   │   ├── services.md
│   │   ├── pricing-and-engagements.md
│   │   └── sales-process.md
│   ├── case-studies/
│   ├── clients/
│   ├── ecosystem/
│   ├── founder/
│   ├── marketing-content/
│   ├── sales/
│   ├── workshops-courses/
│   └── admin/
├── library/                  VAULT-WIDE RESEARCH
├── _hubs/                    VAULT-WIDE ENTITY AND CONCEPT INDEX
│   ├── people/
│   ├── customers-clients/
│   ├── partners/
│   ├── competitors/
│   ├── employers/
│   ├── products/
│   ├── tools/
│   ├── repos/
│   ├── events/
│   ├── concepts/
│   └── frameworks/
├── _articles/                VAULT-WIDE WRITING
├── _daily-notes/             VAULT-WIDE WORKING NOTES
├── __inbox/                  TEMPORARY INTAKE
└── z_templates/              note templates and vault conventions
```

Private client folders and sensitive operating material are omitted from this public view.

## What each area does

| Area | Role |
| --- | --- |
| `revi-systems/company/` | Stable facts about Revi: positioning, services, pricing, and company background |
| `revi-systems/case-studies/` | Evidence Revi can use when making claims |
| `revi-systems/clients/` | Context, decisions, and deliverables for each engagement |
| `revi-systems/marketing-content/` and `_articles/` | Content plans, drafts, and published work |
| `library/` | Research that may support Revi, a client, or future work |
| `_hubs/` | Entry points for recurring people, organizations, tools, repositories, events, concepts, and frameworks |
| `_daily-notes/` and `__inbox/` | Temporary intake surfaces before durable material is filed |
| `AGENTS.md` and skills | Instructions for how AI should navigate, judge, and change the vault; see [Agent instructions and controls](agent-instructions-and-controls.md) |

## How the vault is organized

The vault favors one durable home for each idea. A company fact belongs in the
company folder. A reusable research finding belongs in the library. A
client-specific decision belongs with that client. Links connect those files
while each explanation stays in one home.

Each note carries simple information about what it is and when it changed. Index pages and hubs make the file structure easier for people and AI to navigate.

## How the hubs work

A hub gives a recurring entity or concept one stable page in the vault. Other
notes link to that page, so its backlinks collect every place where the person,
company, tool, event, or idea appears.

The folders add useful meaning. A customer and a competitor may both be
companies, but their relationship to Revi changes how an AI should interpret
them. The same applies to a former employer, a current partner, and a tool used
inside a client project.

Hubs carry durable narrative and relationships. Specialist tools still own
their live records. For example, a company hub can connect research and project
notes across the vault, while Attio owns its current sales record.

## How AI uses it

An AI session starts with the vault instructions, follows links to the relevant company or client material, and reads only the context needed for the task. It can draft changes, but a reviewed repository change is the approval point for durable knowledge.

Obsidian is the local reading and linking interface. GitHub holds the shared
repository and pull-request history. Granola supplies meeting evidence that can
become a reviewed vault note.

The vault focuses on durable knowledge and business reasoning:

- Current contacts and deals stay in the CRM.
- Active GTM rules stay in the [GTM workspace](go-to-market.md#the-workspace).
- Automation schedules and health stay in [Revi Ops](revi-ops.md).
- Credentials stay outside the knowledge files.

This boundary keeps the vault useful for reasoning while specialist business
tools hold their own live records.

## Where to go next

- [Map of Revi's context system](../system-map.md)
- [Knowledge and content workflow](../workflows/knowledge-and-content.md)
- [Keeping context current](../workflows/keeping-context-current.md)
- [Agent instructions and controls](agent-instructions-and-controls.md)
- [Connected tools](connected-tools.md)
