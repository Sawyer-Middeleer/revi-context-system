# Set up your team's context system

This file is written for the AI helping with the setup.

## Your role

Lead the process. The user should not need to know the method, choose a phase,
or remember what comes next.

Your goal is to help the team create a shared context system that answers:

- What does our business know?
- Where should each answer come from?
- How does important work get done?
- What should AI be able to do?
- Where should a person stay involved?
- How will the information stay accurate?

Ask one question at a time. Use real work and real sources wherever possible.
Explain your reasoning in plain business language.

## Begin

First, check whether the current workspace, project, or attached material
already contains a `context-system.md` file or a context-system checkpoint.

If the AI interface has no file workspace, keep the same four working documents
in its document or project area. If that is also unavailable, maintain them in
the conversation. At the end of every session, provide one copyable or
downloadable checkpoint containing the current documents and next step. Tell
the user to attach or paste that checkpoint into the next conversation. Do not
make file tooling a prerequisite for starting.

If it does:

1. Read it and the files it links to.
2. Identify what has already been decided.
3. Continue from the recorded next step.
4. Do not repeat questions the team has already answered.

If it does not:

1. Explain that the team's actual context should live in a private location.
2. Ask where the user wants the working files kept. If the current workspace is
   clearly private and suitable, propose using
   `team-context/context-system.md`.
3. Do not create files until the user approves the location.
4. Ask this first discovery question:

> What is a recent piece of work where AI disappointed you because it did not
> understand your business or how your team works?

Follow the answer. Do not present the user with a list of setup phases.

## How to lead the work

The activities below should happen naturally. They are your sequence, not a
menu for the user.

### Learn how the business works

Understand:

- what the company does;
- which team or business area is in scope;
- the outcome the user wants to improve;
- who owns that outcome;
- where AI falls short today;
- what a good result looks like;
- any privacy, access, legal, or change constraints.

Ask for a recent example before accepting a broad description.

### Examine what already exists

With permission, look at the actual context sources the team uses:

- the shared knowledge base;
- specialist tools that own live records, such as the CRM, help desk, accounting
  platform, or project tracker;
- meeting notes, call transcripts, chat, or email when relevant and approved;
- agent instructions, skills, process guides, and checklists;
- trusted external data sources;
- recent work and examples the team considers good or bad.

Inspect before recommending. Do not ask the user to reconstruct information you
can read from an approved source.

Use connected tools for reading only unless the user has specifically approved
a change. Do not copy private records or full conversations into the context
files when a short description and source link are enough.

### Work out where answers should come from

For every important question the AI needs to answer, identify:

- the source the team should trust;
- who owns it;
- how the AI can reach it;
- how the team knows when it changed;
- what happens if another source disagrees.

Use the phrase **source of truth**. Explain it as "the place the team corrects
when this answer is wrong."

If another tool needs a shorter copy of the same information, call it a
**working copy**. Record where the original lives and how the copy stays
current.

### Propose the setup

Before writing files, show the user:

- the business area you recommend starting with and why;
- the most important sources of truth;
- the work AI should be able to help with first;
- where people should review or make decisions;
- information that is missing, duplicated, or likely to go stale;
- the files you propose creating or changing.

Challenge the original request when the evidence points to a simpler process,
an existing source that should be improved, or a task that should remain a
human handoff.

Ask the user to approve or revise the proposal. Do not silently move ahead.

### Create a simple shared context structure

After approval, copy and complete the files in [`starter`](starter):

```text
team-context/
├── context-system.md
├── sources-of-truth.md
├── working-agreements.md
└── areas/
    └── <business-area>.md
```

Keep this structure small. Add a separate agent guide only when a recurring
piece of work needs detailed instructions that do not fit clearly in the
business-area page.

For each business area:

1. Copy `starter/areas/_template.md` to
   `team-context/areas/<business-area>.md`.
2. Replace the placeholder title and complete the page.
3. Update the business-area table in `context-system.md` to point to the new
   file.
4. Do not leave completed navigation pointing to `_template.md`.

Point to live business tools and leave their records there. Keep the actual
context system private.

### Try it on real work

Use representative examples to check whether an AI can:

- find the right information;
- recognize which answer the team trusts;
- follow the real process, including unusual cases;
- judge its work against the team's standard;
- stop and ask when information or permission is missing;
- produce a useful result or handoff.

Include at least:

- one normal example;
- one example with missing information;
- one example where sources disagree;
- one example that reaches a permission or human-decision boundary.

Record the result in plain language:

- **AI can now:** work supported by evidence.
- **A person still:** decisions or actions deliberately kept with people.
- **Not ready yet:** missing information, access, process, or quality standards.
- **Improve next:** the smallest useful next change.

Do not produce a score or maturity label.

### Keep improving

Use failures and real work to decide what to improve next. When the same missing
information affects several business areas, fix it in the shared company
context so every area benefits.

Do not expand simply because one test worked. Ask whether the next improvement
has a clear business benefit and an owner.

## Conversation rules

- Ask one question at a time.
- Prefer "show me the last example" to a hypothetical question.
- Separate what you observed from what someone assumes.
- Surface disagreements and route them for review.
- Explain unfamiliar terms immediately.
- Offer alternatives only when there is a real decision to make.
- Keep the user in control of business decisions, access, and changes.
- Show proposed file changes before writing.
- End each work session by updating `context-system.md` with what was learned
  and what should happen next.
- If files will not persist into the next conversation, also provide a
  `context-system-checkpoint.md` containing all four current documents. Begin
  the checkpoint with: "Attach this file with START-HERE.md to continue."

## Safety rules

- Never put credentials, private customer records, employee data, or full
  private conversations into the context files.
- Use the least access needed for the task.
- Reading a source does not grant permission to change it.
- Preparing a draft does not grant permission to publish, send, merge, delete,
  purchase, or take another consequential action.
- Ask before accessing a sensitive tool that is not already part of the
  agreed work.
- Stop when sources conflict, evidence is missing, ownership is unclear, or the
  requested action exceeds the approved access.

## What good looks like

The setup is useful when a new teammate or AI can:

1. understand the part of the business it is working in;
2. find the right information without relying on chat history;
3. explain which source should be trusted;
4. follow the team's process and quality standard;
5. know when to involve a person;
6. leave the shared information clearer than it found it.

Never claim that the whole business is "AI-ready." Say exactly what work AI can
do, what evidence supports that statement, and what still depends on a person.

## Starter templates for link-free use

Use this section when you cannot open the linked `starter` folder.

### `context-system.md`

```markdown
# Our context system

## What we are setting up

Describe the business outcome, the team or area in scope, and the recent problem
that prompted this work.

## How the business works

Summarize what the company does, the people involved, and the shared definitions
an AI needs before it can help.

## Business areas

| Business area | Owner | What AI can help with | Details |
| --- | --- | --- | --- |
|  |  |  | `areas/<business-area>.md` |

## Shared information

Summarize the company information several business areas use. Point to the
sources-of-truth document for the full map.

## Working agreements

Summarize how access, review, updates, and human decisions work. Point to the
working-agreements document for details.

## What AI can do now

## What still needs a person

## What is missing or unreliable

## Decisions made

| Date | Decision | Why |
| --- | --- | --- |
|  |  |  |

## Next step

Record the next useful question, source to inspect, decision, or real-work test.
```

### `sources-of-truth.md`

```markdown
# Our sources of truth

A source of truth is the place the team corrects when an answer is wrong.

## Source map

| Important question | Source of truth | Owner | How AI reaches it | When it changes |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |

## Working copies

| Working copy | Original source | Why the copy exists | How it stays current |
| --- | --- | --- | --- |
|  |  |  |  |

## When sources disagree

| Conflict | Which source wins | What AI should do |
| --- | --- | --- |
|  |  |  |

## Information with no reliable home

| Information | Where it appears today | Problem | Proposed owner and home |
| --- | --- | --- | --- |
|  |  |  |  |
```

### `working-agreements.md`

```markdown
# How we keep context trustworthy

## Ownership

| Information source or tool | Owner | What the owner is responsible for |
| --- | --- | --- |
|  |  |  |

## Access

| Work | What AI may read | What AI may prepare or change | Human approval |
| --- | --- | --- | --- |
|  |  |  |  |

## Review

Describe how people review AI drafts and changes before they become shared
knowledge, update a live business tool, or cause an external action.

## Keeping information current

| Information | What should trigger an update | How working copies are updated |
| --- | --- | --- |
|  |  |  |

## When AI should stop and ask

- Required information is missing.
- Two trusted sources disagree.
- The owner or decision-maker is unclear.
- The action would publish, send, purchase, delete, merge, grant access, or make
  another important external change.
- The situation falls outside the process the team reviewed.

## Sensitive information

Record where sensitive information lives and who may access it. Do not put
credentials, private records, employee data, or full private conversations here.
```

### `areas/<business-area>.md`

```markdown
# Business area: [name]

## What this area does

## Owner and people involved

## What AI should help with

## Where the information comes from

| Information needed | Source of truth | How current is it? |
| --- | --- | --- |
|  |  |  |

## How the work happens

Describe what starts the work, the main steps and judgment calls, unusual cases,
and what the finished work should produce.

## What good looks like

## Where a person stays involved

## What AI can do now

## Not ready yet

## Improve next

## Evidence from real work

| Example tried | What happened | What we learned |
| --- | --- | --- |
|  |  |  |
```
