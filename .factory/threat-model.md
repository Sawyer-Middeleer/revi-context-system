# Security threat model

## 1. System Overview

This repository is a public documentation project. It contains Markdown guides,
starter templates, and small instruction adapters for AI tools. It has no
application server, database, authentication layer, executable package, or
deployment configuration.

The repository has two user-facing parts:

1. `revi-system/` describes a sanitized example of Revi's organizational
   context system.
2. `set-up-your-system/` guides a person and an AI assistant through creating
   private context files from starter templates.

The primary security goal is to keep private business information and
credentials out of this public repository while preserving the integrity of
the guidance. The setup guide may lead an AI assistant to read connected
business tools or prepare changes, so its permission and review boundaries are
also security-relevant.

## 2. Trust Boundaries

### Public repository

All repository content is public and untrusted until a user verifies that it
comes from the official repository and a reviewed revision. Forks, copied
files, issue comments, and external links can differ from the maintained
version.

### Private working context

Teams following the guide create context in a private location they approve.
Private customer records, employee data, conversations, and credentials must
remain across this boundary and outside the public repository.

### Connected business tools

An AI assistant may receive approved read or write access to services such as a
CRM, meeting recorder, accounting platform, or repository. Each service keeps
its own authentication and authorization controls. Reading from a service does
not authorize an external action or a change to that service.

### Human review

The guide places people at decisions involving access, source ownership,
publication, sending, purchases, deletion, merges, and other consequential
actions. Drafts and proposed file changes cross this boundary only after review.

## 3. Critical Assets

| Asset | Sensitivity | Required protection |
| --- | --- | --- |
| Private business context | High | Store only in a user-approved private location and grant least access |
| Credentials and connector tokens | Critical | Keep outside all context files, examples, logs, and commits |
| Customer, prospect, and employee records | High | Leave in approved systems of record; use short descriptions or links when sufficient |
| External account state | High | Require explicit authorization before consequential changes |
| Public guidance and adapters | Medium | Review changes, preserve source history, and verify repository origin |
| Source-ownership decisions | Medium | Record an owner and review conflicting sources before accepting changes |

## 4. Attack Surface

The repository exposes no network service. Its attack surface consists of:

- Markdown instructions that an AI assistant or person may follow;
- copyable skill adapters that delegate to `START-HERE.md`;
- external documentation links;
- starter files that users fill with private business context;
- public contributions that could weaken safety rules or disclose private
  material.

Content copied into a private workspace inherits the permissions and security
controls of that workspace.

## 5. Threat Analysis

### Spoofing

**Threat:** A malicious fork or copied adapter presents itself as the official
guide and adds unsafe instructions.

**Mitigations:** The root README links to the canonical repository, adapters
point to one shared process file, and Git history supports source verification.
Users should verify the repository owner and revision before installing an
adapter.

**Residual risk:** Medium likelihood and medium impact when users install files
from an unverified source.

### Tampering

**Threat:** A contribution changes review, permission, or source-ownership rules
so an AI assistant can act beyond the user's intent.

**Mitigations:** Pull-request review, a concise central setup guide, explicit
human decision points, and automated link and structure checks make material
changes visible.

**Residual risk:** Low likelihood and high impact for a reviewed upstream
change; higher likelihood in an unreviewed fork.

### Repudiation

**Threat:** A consequential action or accepted context change has no durable
record of who approved it.

**Mitigations:** The guide uses pull requests and source-system history for
accepted changes and keeps external actions behind explicit authorization.

**Residual risk:** Medium when an adopting team uses tools without adequate
history or bypasses the proposed review path.

### Information Disclosure

**Threat:** A contributor or adopter commits credentials, private records, full
conversations, internal endpoints, or identifying business data.

**Mitigations:** The repository is sanitized, contributing guidance prohibits
private payloads, starter files exclude credentials, `.gitignore` patterns
cover common secret files, and pre-commit secret scanning checks the full tree.

**Residual risk:** Medium because filled starter files contain user-supplied
content and can be committed to the wrong repository.

### Denial of Service

**Threat:** Overly broad or recursive instructions cause excessive connected
tool reads or repeated setup work.

**Mitigations:** The guide starts with one business area, resumes from a
checkpoint, inspects only relevant approved sources, and asks for the smallest
useful next change.

**Residual risk:** Low. Connected services should retain their own quotas and
rate limits.

### Elevation of Privilege

**Threat:** An AI assistant treats access to a connected tool as permission to
write, publish, send, delete, merge, purchase, or grant access.

**Mitigations:** `START-HERE.md` separates reading from changing, requires user
approval for consequential actions, and directs the assistant to stop when a
request exceeds approved access.

**Residual risk:** Medium if a consuming AI tool ignores instructions or is
given unnecessarily broad credentials.

## 6. Vulnerability Pattern Library

This repository contains documentation and no application code. Security
reviews should look for these content patterns:

### Embedded secrets or private payloads

Unsafe patterns include API keys, tokens, passwords, private customer details,
full conversation transcripts, internal endpoints, and real filled-in starter
templates. Safe examples use generic placeholders and explain where the private
record belongs.

### Unbounded authority

Unsafe instructions tell an AI assistant to update connected tools or take
external actions solely because access exists. Safe instructions distinguish
reading, drafting, approval, and action.

### Instruction indirection

Unsafe adapters duplicate the full process and can drift from safety rules.
Safe adapters point to the reviewed `START-HERE.md` source.

### Unsafe source ingestion

Unsafe instructions treat chat, email, meetings, or external pages as settled
business truth. Safe instructions treat them as evidence, compare them with the
owned source, and route proposed changes through review.

### Sensitive output paths

Unsafe setup flows write private context into the public repository by default.
Safe flows ask the user to approve a private location before creating files.

Traditional SQL injection, cross-site scripting, command injection, path
traversal, authentication bypass, and IDOR patterns do not apply because the
repository has no executable application or request-handling surface.

## 7. Security Testing Strategy

Before committing:

1. Review every changed file for private or identifying payloads.
2. Run a secret scanner with redacted output.
3. Validate relative links, headings, fenced blocks, skill metadata, encoding,
   and whitespace.
4. Confirm setup instructions preserve least access, human approval, and
   private-storage boundaries.
5. Inspect the staged diff and file list before creating the commit.

## 8. Assumptions and Accepted Risks

- The official Git host and user-selected private workspace enforce their own
  authentication and authorization.
- Connected services protect credentials and apply their own rate limits.
- AI tools can fail to follow written instructions, so people retain authority
  over consequential actions.
- Public architecture descriptions reveal component names and relationships.
  Sensitive records, credentials, host details, and exploitable implementation
  details remain excluded.
- External documentation links can change after review. They are references,
  not executable dependencies.

## 9. Version Changelog

- **1.0.0, 2026-09-08:** Initial threat model for the public documentation,
  guided setup, starter templates, and skill adapters.
