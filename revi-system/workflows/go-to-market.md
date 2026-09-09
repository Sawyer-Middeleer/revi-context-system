# Go-to-market

> **What this page is:** One workflow across the knowledge vault, GTM
> workspace, GTM engine, live sales tools, and Revi Ops.

Revi's go-to-market workflow is a closed loop: decide what to test, find the right
companies and people, send a controlled campaign, then use the results to decide
what to test next.

The loop crosses several components. Company strategy starts in the knowledge
vault, sales rules live in the GTM workspace, current relationships live in
Attio, and campaign delivery lives in Instantly.

Revi Ops keeps the recurring GTM cycles visible and runs approved GTM tasks from
the shared board. The board gives changes and repairs a clear owner, status, and
route to human review.

## The operating loop

### 1. Decide what to test

- **Starts with:** Revi's positioning, services, prior campaign results, and
  current sales priorities.
- **AI helps by:** researching the market, summarizing past results, and
  comparing possible audiences and messages.
- **A person decides:** the audience, the problem to lead with, what result
  would count as promising, and when to stop.
- **The result:** an approved campaign plan in the GTM workspace. It names the
  audience, target roles, message, campaign, and decision rules.

The stable description of Revi still comes from the company knowledge vault.
The GTM workspace labels a more specific sales test as an active experiment.
Company strategy stays in the vault until Revi approves a durable change.

### 2. Build the account pool

- **Starts with:** the approved audience and sourcing rules in the GTM
  workspace.
- **AI and automation:** search approved public and paid data sources for
  matching companies, check for companies already in Attio, and record where
  each new company came from.
- **A person decides:** cases outside the rules, such as whether an unusual
  company really belongs in the audience.
- **The result:** possible accounts in Attio with their source and known
  qualification evidence.

For Revi's services campaigns, this means finding growing B2B services companies
that match the active audience definition. The GTM engine adds a company after its
evidence meets the declared rules.

### 3. Qualify the accounts

- **Starts with:** the account record, outside evidence, Revi's qualification
  rules, and any existing hold or exclusion.
- **AI and automation:** apply clear exclusions, calculate the declared score,
  and prepare a short explanation of the result.
- **A person decides:** unclear cases and any exception to the existing rules.
- **The result:** an account that is ready for contact research, disqualified,
  held, or waiting for a named judgment.

The explanation matters as much as the score. It lets a person inspect the
evidence and reasoning behind the number.

### 4. Find the right person

- **Starts with:** a qualified account and the target roles defined for that
  audience.
- **AI and automation:** search for people matching those roles, check the
  returned title against the actual title rules, and find approved contact
  information.
- **A person decides:** ambiguous titles, unclear responsibility, or whether to
  research the account another way.
- **The result:** a contact who fits the intended role, or an honest record of
  a failed search, zero qualified matches, or a case needing help.

A failed data-provider call is recorded as a provider failure. A completed
search records the number of qualified matches. Those outcomes lead to
different next steps.

Prospeo supplies Revi's company and person research. FullEnrich is the first
source for contact information, with Prospeo filling remaining gaps.

### 5. Prepare the campaign

- **Starts with:** the qualified account and contact, current Attio history,
  approved message, campaign routing, prior attempts, and active holds.
- **AI and automation:** check every contact against the send rules, prepare the
  campaign fields, and show a preview of who would be included or excluded and
  why.
- **A person reviews:** whether the audience, message, exclusions, and campaign
  state are ready for a send decision.
- **The result:** a send-ready preview or a set of corrections. Nothing has
  been authorized or sent yet.

Send authorization follows the valid-list preview.

### 6. Send and record what happened

- **Starts with:** the send-ready preview and explicit authorization for that
  audience, message, and campaign.
- **Automation:** loads only those contacts into Instantly, records successful
  submissions in the GTM operating history, and updates the relevant campaign
  state in Attio.
- **A person decides:** whether to authorize the external action. When the
  outreach platform reaches capacity or reports an unsafe state, the process
  waits for a safe state.
- **The result:** a reviewable record of who entered which campaign and when.

### 7. Capture delivery and replies

- **Starts with:** delivery and reply events from Instantly.
- **Automation:** matches each event to the person and company in Attio, updates
  the relationship history, and flags replies that need a person.
- **A person decides:** how to respond and what should happen next with an
  interested, unclear, negative, or opted-out contact.
- **The result:** a current relationship record, any required follow-up, and
  campaign results ready for analysis.

Instantly remains the answer to "was it delivered or answered?" Attio remains
the answer to "what is our current relationship with this person or company?"

### 8. Decide the next test

- **Starts with:** the captured results, campaign history, and the success or
  stopping rules chosen in step 1.
- **AI helps by:** comparing the current results with those rules and preparing
  a recommendation to continue, stop, or change the test.
- **A person decides:** what the evidence means for the next campaign.
- **The result:** a recorded decision that becomes the input to step 1.

## Rules that apply across the loop

- Credentials stay outside the context files.
- Every company and contact retains the source it came from.
- Clear holds and exclusions stop unnecessary research and contact.
- Source failures retain their failure status, preserving the difference
  between missing evidence and negative evidence.
- The same role and qualification rules apply during research and immediately
  before sending.
- External action always follows a preview and the agreed human check.
- Campaign activity and human judgment leave a record for the next cycle.

## What still needs work

- Company knowledge is copied into the GTM workspace by hand, so the two can
  temporarily disagree after Revi changes its positioning.
- Unclear qualification still depends heavily on the founder.
- Data and outreach providers can make the loop temporarily unavailable while
  Revi's own components are operating correctly.
- More campaign history is needed before every next-step decision has strong
  evidence behind it.

## Related component pages

- [Map of Revi's context system](../system-map.md)
- [The go-to-market component](../components/go-to-market.md)
- [Agent instructions and controls](../components/agent-instructions-and-controls.md)
- [Revi Ops](../components/revi-ops.md)
