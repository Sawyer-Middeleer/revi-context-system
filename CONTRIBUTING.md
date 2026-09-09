# Contributing

Contributions should make Revi's system easier to understand or make the guided
setup easier for a strategic operator to use.

## Writing

- Write for someone who understands business, technology, and AI but does not
  build software.
- Explain a term the first time it appears. Prefer ordinary business language.
- Introduce a file or concept through the decision it helps someone make.
- Keep the visible setup simple. The agent should manage the sequence.
- Prefer "business area," "source of truth," and "working copy" over more
  technical alternatives.

## Revi documentation

Preserve the real architecture and operating decisions, but never add:

- customer or prospect records;
- private messages or meeting transcripts;
- credentials, internal endpoints, or hostnames;
- confidential metrics or contract terms;
- details that would make an internal system easier to attack.

Describe vendor-specific tools alongside the business job they perform so
another team can map the design to its own stack.

## Guided setup

- Keep one main starting prompt.
- Ask the user one question at a time.
- Use real examples before general questions.
- Show proposed changes before writing them.
- Leave consequential actions and permission changes to the user.
- Store sensitive business context only in a private location the user approves.

Before submitting a change, check every relative link and confirm the public
Revi documentation still contains no private payloads.
