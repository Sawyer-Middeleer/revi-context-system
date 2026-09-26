# Knowledge and content

> **What this page is:** A workflow centered on the knowledge vault. It can
> also use research tools, publishing tools, and Revi Ops when a step runs on a
> schedule.

Revi's knowledge workflow turns useful research, meetings, decisions, and
operating experience into information that people and agents can find and reuse.

The workflow preserves material with lasting value. Each item moves through one
clear path: select it, place it, structure it, review it, then use it.

Revi Ops runs scheduled knowledge workflows and routes their proposed changes
through the shared task board. This keeps recurring contributions visible until
a person accepts or rejects them.

## The operating loop

### 1. Select what is worth keeping

- **Starts with:** a meeting, external source, decision, client interaction, or
  useful lesson from active work.
- **AI helps by:** checking whether the material is work-relevant, durable, and
  already represented in the vault.
- **A person decides:** uncertain cases and anything sensitive.
- **The result:** material worth developing, a pointer to existing knowledge, or
  a deliberate decision to add nothing.

Adding nothing is a valid result. A knowledge base becomes less useful when
agents fill it with generic summaries and duplicates.

### 2. Find the right home

- **Starts with:** the selected material and Revi's existing vault structure.
- **AI:** identifies whether it belongs with company knowledge, a client,
  reusable research, a person or company page, or an active project.
- **A person decides:** cases where ownership or future use is unclear.
- **The result:** one intended home and a list of related knowledge the draft
  should consider.

Current CRM contacts and campaign events stay in the live tools built to
maintain them.

### 3. Turn the source into useful context

- **Starts with:** the original source and the related knowledge already in the
  vault.
- **AI:** extracts decisions, evidence, actions, relationships, and reusable
  insight. It drafts the content, metadata, and links together.
- **A person decides:** what the source meant when interpretation affects the
  business.
- **The result:** a focused draft that is shorter and more useful than the raw
  source.

For a meeting, the draft separates decisions and action items from discussion.
For outside research, it preserves the source and writes an original summary.

### 4. Review the proposed knowledge

- **Starts with:** the draft and its source.
- **AI:** opens a pull request showing exactly what would be added or changed.
- **Automation:** for scheduled contributions, checks the pull request against
  the routine's limits and returns anything outside them to draft with the
  reason.
- **A person checks:** accuracy, privacy, attribution, placement, and whether
  the material is useful enough to keep.
- **The result:** an accepted change, a revision request, or a rejected draft.

A person reviews and merges the agent's knowledge contribution.

### 5. Retrieve and use it

- **Starts with:** the accepted note.
- **AI:** finds it through the reviewed links, metadata, and folder location
  when later sales, content, client, or operating work needs it.
- **A person decides:** whether new use reveals an error or a reason to change
  company knowledge, a process, or a working copy.
- **The result:** better grounded work or a proposed update that returns to the
  review loop.

When later work reveals an error, the correction goes back through the same
review path. [The maintenance loop](keeping-context-current.md) handles updates
across the rest of Revi's components.

## A concrete example: daily reading

1. A scheduled agent finds one substantive, freely available source relevant to
   Revi's work.
2. It checks the vault for the title and author to prevent duplicate
   recommendations.
3. It chooses the subject area where the note belongs.
4. It writes a short summary in its own words, records the source, and links
   related knowledge.
5. When a daily note exists, it adds a link there. Daily notes remain
   user-created.
6. It opens a pull request.
7. A person reviews and merges the contribution.

## A concrete example: updates from recent work sessions

Decisions and corrections often surface during everyday AI work sessions
rather than in meetings. A daily routine collects them.

1. A program cuts the previous day's work sessions into short exchanges, drops
   tool output and AI reasoning, and removes anything that looks like a
   credential.
2. A decision model sorts each exchange by answering narrow yes-or-no and
   pick-one questions (see
   [Typed judgment](../components/revi-ops.md#typed-judgment)). Only a
   decision a person made, a correction to a fact the vault already records, or
   an insight about a named person, organization, project, or tool can go
   forward. General lessons and summaries of work are left out. If nothing
   qualifies, the AI never runs.
3. The AI receives only the selected exchanges, never the full sessions. It
   edits the note that holds the stale fact or the page for the entity involved.
4. It opens one pull request for the day.
5. A final check returns the pull request to draft if it strays outside the
   routine's limits, for example by creating a concept page or containing
   something that looks like a credential.
6. A person reviews and merges the contribution.

Corrections count for more than additions. A run that adds nothing is a correct
run.

## A concrete example: meeting preparation

1. Each morning, a routine reads the day's calendar and lists the outside people
   in each meeting.
2. It checks the vault for an existing page for each person and, where the
   company is the reason for the meeting, for that company.
3. For anyone missing, it researches public sources and keeps a finding only
   when both the name and the company match the invitation. A sparse page is
   acceptable; a guessed one is not.
4. It creates the missing pages, links existing mentions to them, and opens one
   pull request.
5. It posts a short summary to the operations channel with the meetings, new
   pages, and the pull request.
6. A person reviews and merges the contribution.

## Rules that apply across the loop

- Keep only material likely to matter later.
- Put each item where someone will look for it in six months.
- Link existing knowledge while keeping each fact in its established home.
- Keep private client material inside the client's area.
- Preserve the source and distinguish evidence from interpretation.
- Leave live records in their specialist tools.
- Agent drafts remain proposals until a person accepts them.

## What still needs work

- Review quality depends on someone understanding both the source and the
  business context.
- A person still needs to notice some decisions that should update company
  knowledge.
- Meeting and communication tools keep evidence on their own retention
  schedules.
- Ownership must move from one central reviewer to the people closest to each
  subject as Revi grows.

## Related component pages

- [Map of Revi's context system](../system-map.md)
- [The knowledge vault](../components/knowledge-vault.md)
- [Agent instructions and controls](../components/agent-instructions-and-controls.md)
- [Revi Ops](../components/revi-ops.md)
