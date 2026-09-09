# How Revi keeps context current

> **What this page is:** A cross-component maintenance workflow. It routes each
> change back to the vault, GTM component, Revi Ops, or live business tool that
> owns it.

Revi's information changes in three different ways:

| What changed | Example | Where the update belongs |
| --- | --- | --- |
| A live business record | A prospect replied or a deal moved forward | The CRM or other tool that runs that work |
| Company knowledge | Revi changed its positioning or made a policy decision | The company knowledge vault |
| A process | The team changed how it qualifies accounts or reviews agent work | The relevant instruction, skill, or operating configuration |

These paths are separate, but they follow the same update loop.

Revi Ops runs recurring checks and sends updates that need judgment to the
shared task board. This gives each proposed correction a visible owner and
review state.

## The update loop

### 1. Notice a possible change

- **Starts with:** a business event, meeting, message, accepted decision, human
  correction, or failed piece of work.
- **AI and automation:** watch approved sources for events that may make current
  information incomplete or wrong.
- **A person decides:** which sources an agent is allowed to watch.
- **The result:** a specific change candidate with its original evidence.

For example, the meeting-note routine checks recent Granola meetings. The GTM
reply routine checks Instantly for new campaign activity. Neither treats the raw
event as settled company knowledge.

### 2. Compare it with the current answer

- **Starts with:** the new evidence and the source the team currently trusts.
- **AI:** finds the existing record, decision, or instruction and explains what
  appears to differ.
- **A person decides:** only when the owner or meaning of the difference is
  unclear.
- **The result:** confirmation of the current answer, a clear correction, or a
  conflict that needs review.

This comparison stops the workflow from creating a second answer simply because a
meeting or message used different words.

### 3. Decide what actually changed

- **Starts with:** the comparison and relevant business context.
- **AI helps by:** separating explicit decisions from suggestions, discussion,
  and assumptions, then routing the proposed change to the likely owner.
- **A person decides:** the destination only when the rules or ownership are
  unclear.
- **The result:** a proposed update for one named source and owner, or
  confirmation that the current source remains accurate.

A Slack message can justify correcting the CRM, which remains the account
record. A discussion about new positioning enters the company description after
the founder accepts it.

### 4. Approve and update the source of truth

- **Starts with:** the proposed update.
- **AI or automation:** shows the exact change, then applies it through the
  controls of that component or tool after the required approval.
- **A person decides:** whether to accept shared knowledge, process changes, and
  important business actions. Routine live-record updates may proceed
  automatically only when an existing reviewed rule already authorizes them.
- **The result:** the corrected CRM record, vault note, or operating
  instruction.

Shared knowledge and instruction changes go through pull requests, so the
reviewer can see exactly what changed. Live GTM records use the rules and
history built into the GTM component.

### 5. Refresh the working copies

- **Starts with:** the accepted update and a list of other places that use a
  shorter copy.
- **AI or automation:** identifies the affected copies and updates or flags
  them.
- **A person decides:** whether an apparent difference is intentional, such as
  an active sales experiment.
- **The result:** aligned working copies or a clearly recorded exception.

Revi's main weak point is here. Company positioning is copied into the GTM
workspace by hand, so the sales version can lag behind the vault after a change.

### 6. Verify and record the outcome

- **Starts with:** the updated source and any refreshed copies.
- **AI or automation:** checks that the change landed, keeps a reviewable
  history, and reports any failed update.
- **A person decides:** how to resolve remaining conflicts or failures.
- **The result:** current information, visible exceptions, and evidence future
  agents can trust.

## Two concrete examples

### A meeting changes shared knowledge

1. The daily meeting-note routine finds a recent work meeting in Granola.
2. It checks the relevant vault folder and recent pull requests for an existing
   copy.
3. It drafts the decisions, action items, evidence, and open questions in the
   right company or client area.
4. A person checks the meaning, privacy, and attribution.
5. The accepted pull request becomes the shared note.
6. Any affected process or working copy is updated separately.

### A prospect reply changes a live record

1. The reply-check routine reads a new campaign event from Instantly.
2. It matches the event to the current person and company in Attio.
3. The GTM rules determine the internal update.
4. Attio is updated, and the GTM history records what happened.
5. Later campaign analysis uses that current relationship and reply history.

## Rules that apply across the loop

- Every important source has an owner.
- Raw conversations and agent drafts are evidence until someone accepts the
  change.
- The source the team trusts is updated before its working copies.
- A working copy identifies the original and how it stays current.
- A quiet automation still records that it checked and found nothing.
- Agents receive only the information and actions needed for the update.
- Credentials remain in the executing tool. Context files and instructions stay
  credential-free.

## What still needs work

- Some working copies are updated by hand.
- A person still needs to notice some decisions that should enter shared
  knowledge.
- Several ownership and review responsibilities sit with the founder.
- Meeting, chat, and email evidence follows the retention rules of those tools,
  so accepted conclusions need to move into a durable source promptly.

## Related component pages

- [Map of Revi's context system](../system-map.md)
- [The knowledge vault](../components/knowledge-vault.md)
- [The go-to-market component](../components/go-to-market.md)
- [Agent instructions and controls](../components/agent-instructions-and-controls.md)
- [Revi Ops](../components/revi-ops.md)
