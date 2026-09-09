# Revi Systems context system

Useful AI work depends on context. The AI needs the right information, a clear
picture of how your team works, and a reliable way to judge its output.

This repository has two parts:

1. **[See how Revi's context system works](revi-system/README.md)**
2. **[Set up a context system for your team](set-up-your-system/START-HERE.md)**

## How Revi's context system works

Revi's context system connects company knowledge, live business records, team
activity, instructions, review, and the tools that support them.

```text
Company knowledge    Live records    Team activity    Instructions
       \                  |                |                /
        \_________________|________________|_______________/
                          v
                   AI and team work
                          |
                          v
                 Review and monitoring
                          |
                          v
                Update the right source
```

The most important rule is simple: for every important question, the team knows
where the answer should come from.

- Company positioning and services come from the knowledge vault.
- Current people, companies, and deals come from the CRM.
- Campaign activity and replies come from the outreach platform.
- Agent instructions come from reviewed skills and operating files.
- Meetings, Slack, and email provide evidence. Reviewed conclusions move into
  the source that owns the answer.
- Every recurring automation is listed, monitored, and owned.

Explore the context system:

- [Map of Revi's context system](revi-system/system-map.md)
- [The knowledge vault](revi-system/components/knowledge-vault.md)
- [The go-to-market component](revi-system/components/go-to-market.md)
- [Agent instructions and controls](revi-system/components/agent-instructions-and-controls.md)
- [Revi Ops](revi-system/components/revi-ops.md)
- [Connected tools](revi-system/components/connected-tools.md)
- [The operating workflows](revi-system/README.md#workflows)

This is a real, sanitized account of Revi's context system. It keeps the
architecture and operating decisions intact while leaving out customer records,
private conversations, credentials, and sensitive implementation details.

## Set up your team's context system

Paste this into the AI tool you already use:

> Help me set up my team's context system. Read and follow <https://github.com/Sawyer-Middeleer/revi-context-system/blob/main/set-up-your-system/START-HERE.md>. Lead the process for me, ask one question at a time, and manage the steps and choices for me.

That is the entry point. The AI should:

1. Learn what your team does and where AI is falling short.
2. Look at the information, tools, and processes you already have.
3. Show you where information should live and which source should win when
   answers conflict.
4. Create a simple set of shared context files in a private location.
5. Test them against real work and tell you what AI can do reliably.

The AI manages the method, template, sequence, and resumption from completed
work.

For an AI that works from attachments, download
[`set-up-your-system/START-HERE.md`](set-up-your-system/START-HERE.md) and attach
it to the conversation. It includes the full process and starter templates.

In a chat interface with temporary sessions, the AI will give you a checkpoint
at the end of the session. Attach that checkpoint when you start a new
conversation, and it will continue where you left off.

## Optional reusable skill

Teams that want the setup process available as a reusable agent skill can use
the adapters for:

- [Factory Droid](set-up-your-system/adapters/factory-droid/INSTALL.md)
- [Claude Code](set-up-your-system/adapters/claude-code/INSTALL.md)
- [OpenAI Codex](set-up-your-system/adapters/openai-codex/INSTALL.md)

The guided process also works in a normal chat.

## License

[MIT](LICENSE)
