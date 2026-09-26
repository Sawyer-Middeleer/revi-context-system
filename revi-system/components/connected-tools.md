# Connected tools

Revi's repositories hold durable knowledge, operating choices, and instructions.
Connected vendor tools supply the live records, raw evidence, and outside data
that AI needs during work. Keeping those records in the tools built to manage
them preserves current state and avoids stale copies in the knowledge vault.

The categories below come from Revi's organizational context system guide. One
tool can play more than one role.

## Categories

| Category | Revi's tools | What they contribute |
| --- | --- | --- |
| Knowledge base | Obsidian vault stored in GitHub | Shared company knowledge, client context, research, and decisions |
| Specialist business tools | Attio, Instantly, QuickBooks Online, Mercury | Current sales, outreach, accounting, and banking records |
| Unstructured streams | Granola, Google Calendar, AI work sessions, Slack | Meeting evidence, the day's schedule, decisions made during AI work, and operating updates |
| Instructions and controls | GitHub repositories, Factory | Reviewed instruction files, skills, hooks, settings, prompts, and declarations, plus the AI runtime that loads them |
| Decision models | TypeSafe | Typed answers to narrow judgment questions inside scheduled routines |
| External data sources | Prospeo, FullEnrich | Company, person, and contact data retrieved when needed |

## What each tool owns

| Tool | Role in Revi's context system | How it connects |
| --- | --- | --- |
| **GitHub** | Holds the shared versions and change history of the vault, GTM, and Revi Ops repositories. The shared task board, issues, and pull requests carry work and review. | People and AI work through local checkouts, then use pull requests as the review gate. |
| **Attio CRM** | Owns current people, company, deal, and relationship records. | The GTM engine reads and updates Attio. Campaign results from Instantly return here as relationship history. |
| **Instantly** | Owns outreach campaign membership, delivery activity, and reply events. | The GTM engine loads approved contacts and syncs results back to Attio. |
| **QuickBooks Online** | Owns Revi's accounting books and customer invoices. | Approved finance routines read or update the books. Mercury supplies the bank feed. |
| **Mercury** | Owns bank balances and transaction activity. | Its bank feed enters QuickBooks for bookkeeping and reconciliation. |
| **Granola** | Holds meeting recordings, transcripts, and generated meeting notes. | A scheduled routine turns useful meeting evidence into a proposed vault change for review. |
| **Google Calendar** | Owns the schedule of upcoming meetings and their attendees. | The meeting-preparation routine reads the day's events to find people who need a vault page. |
| **Factory** | Runs AI sessions and keeps the record of each one. | People and scheduled routines work through it. Recent sessions feed the routine that proposes vault updates from work. |
| **TypeSafe** | Supplies Jev, a decision model that returns a probability for a narrow typed question. | Routines send it reduced, credential-free data. The routine's program applies the thresholds and chooses the action. |
| **Slack** | Carries short operating updates for people. | Routines post summaries and the daily health digest to the operations channel. Durable context still lands in its owning repository. |
| **Prospeo** | Supplies outside company and person data for sourcing and enrichment. | The GTM engine calls it under workspace rules, then records accepted results and their source in Attio. |
| **FullEnrich** | Supplies verified contact information for selected people. | The GTM engine uses it in the contact-enrichment sequence and records accepted results in Attio. |

## The main connection paths

```text
Granola -> meeting-note routine -> vault change -> GitHub review

Factory sessions -> TypeSafe triage -> vault change -> GitHub review

Google Calendar -> meeting-prep routine -> new vault pages -> GitHub review
                                        \-> summary in Slack

Prospeo -> company and person evidence \
                                      -> GTM engine -> Attio -> Instantly
FullEnrich -> contact evidence       /                  |
                                                       v
                                                delivery and replies

Mercury -> bank feed -> QuickBooks Online
```

## Where to go next

- [Map of Revi's context system](../system-map.md)
- [The knowledge vault](knowledge-vault.md)
- [The go-to-market component](go-to-market.md)
- [Revi Ops](revi-ops.md)
- [Agent instructions and controls](agent-instructions-and-controls.md)
