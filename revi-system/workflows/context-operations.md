# Context operations

> **What this page is:** The workflow for scheduling or dispatching work that
> adds, refreshes, governs, or reviews context.

Context work spans several repositories and tools. Revi Ops coordinates the
schedule or board item, while instruction files, skills, hooks, and settings
govern how AI performs the work.

Revi Ops handles two paths:

- Recurring context workflows are defined in reviewed files and run on a
  schedule or event.
- One-off context work enters the shared GitHub task board, where people and AI
  share the same queue.

When a recurring workflow creates work that needs attention, it sends that work
to the board. The board tracks Backlog, Ready, In progress, In review, Done, and
Blocked. This gives every task an owner and a visible route to review.

Run history and health checks support both paths by showing whether recurring
work completed and whether a follow-up task is needed.

## The operating loop

### 1. Define the work

- **Starts with:** context that needs to be added, refreshed, reorganized,
  governed, or reviewed.
- **AI helps by:** documenting the trigger, information required, steps,
  expected output, unusual cases, and review point.
- **A person decides:** whether the work should recur, which source owns the
  result, what AI may read or change, and where review happens.
- **The result:** a reviewed recurring-workflow definition or a scoped task for
  the shared board.

The automation register describes the work. The vault workflow executes
meeting-note sync, and the GTM component executes GTM cycles.

### 2. Register or queue it

- **Starts with:** the reviewed definition.
- **The owner:** adds recurring work to `rhythm.yaml` and its scheduler, or adds
  a one-off task to the shared board.
- **Automation:** checks the live schedule for recurring work and the required
  owner, repository, and executor fields for board work.
- **A person decides:** the final schedule, any deliberate pause, or when a
  board task is Ready.
- **The result:** a registered recurring workflow or a Ready task with a named
  owner and execution path.

A pause requires two matching facts: the scheduler is disabled, and the
register says why it is paused and what would start it again. A mismatch becomes
a specific task on the board.

### 3. Run the work

- **Starts with:** a scheduled time, an event, or a Ready board task.
- **AI or automation:** loads the applicable instruction file and skill,
  follows hook and setting boundaries, and prepares the assigned context
  change.
- **A person decides:** only when the process reaches a judgment or permission
  boundary.
- **The result:** a proposed source update, a clear "nothing to do," a blocked
  handoff, or a failure ready to record.

The issue dispatcher is a concrete example. It reads work marked ready on the
board, claims one item, starts AI in the appropriate repository, and
returns the resulting branch or pull request to Revi Ops.

### 4. Record and route the result

- **Starts with:** the completed or failed run.
- **Automation:** appends one short outcome to the shared run log. It includes
  when the run started and ended, the outcome, what it produced, and where more
  detail can be found. It then routes a proposed change to review, a blocked or
  failed run to its owner, and updates the board where a task exists.
- **A person decides:** only where the result needs judgment or follow-up.
- **The result:** durable evidence plus one clear destination: review,
  investigation, human judgment, or completion.

### 5. Review the individual result

- **Starts with:** a proposed change, blocked handoff, judgment request, or
  failure routed in step 4.
- **AI helps by:** presenting the output, evidence, and relevant run detail in
  one place.
- **A person decides:** whether to merge, request changes, resolve the judgment,
  restart the work, or leave it blocked.
- **The result:** accepted work, a specific revision, or a recoverable next
  action.

### 6. Check supporting health

- **Starts with:** the intended schedule in `rhythm.yaml`, the real scheduler,
  and the pattern of recent run outcomes.
- **Automation:** looks for schedule disagreements, missing runs, repeated
  failures, unusually long work, and declared pauses. A daily health routine
  posts the summary to the operations channel.
- **A person decides:** whether a failure needs investigation, a routine should
  stay paused, or the process itself should change.
- **The result:** a concise health view or a work item that feeds the
  improvement step.

### 7. Improve the routine

- **Starts with:** health findings, repeated human corrections, wasted work, or
  a better way to produce the outcome.
- **AI helps by:** tracing the pattern across the register, run log, and review
  history.
- **A person decides:** whether to change the instructions, access, schedule, or
  ownership.
- **The result:** a reviewed change to the owning repository and, when needed, the
  automation register. That change returns to step 1.

## Rules that apply across the loop

- Every recurring routine has an owner and one entry in the register.
- Every run records an outcome, including "nothing to do."
- Deliberate pauses remain visible and name the condition for restarting.
- Failure and missing execution are different problems.
- Durable run history remains primary, with detailed logs supplying explanation.
- Agents can prepare changes, but people merge them.

## What still needs work

- The shared board depends on clear task briefs and accurate Ready states.
- Ownership can still become unclear when a recurring workflow creates a task
  in another repository.
- The founder still reviews work that should eventually have separate owners.

## Related component pages

- [Map of Revi's context system](../system-map.md)
- [Revi Ops](../components/revi-ops.md)
- [Agent instructions and controls](../components/agent-instructions-and-controls.md)
- [The knowledge vault](../components/knowledge-vault.md)
- [The go-to-market component](../components/go-to-market.md)
