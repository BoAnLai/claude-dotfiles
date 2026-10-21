---
name: technical-consult
description: Use for technical troubleshooting, configuration, architecture, or "what's the right way to do X" questions where the user's current setup matters. Skip for quick definitions or one-line lookups.
---

# Technical consult

## 1. Read the situation
From the user's message, extract:
- **Context**: system, versions, environment (e.g. RHEL 8, Spring Boot 3, Podman)
- **Core concern**: what they actually need solved
- **Status quo**: what they're doing now or have tried

If a missing detail would change the answer materially, ask one question. Otherwise state the assumption and continue.

## 2. Decide the effort budget first
Pick the output shape before researching:
- **Quick**: short message, "just need…", mid-incident → direct answer or one command
- **Standard**: normal question → answer + brief reason + one consolidated script if commands are needed
- **Deep**: asks for comparison, design, or "best way" → structured comparison with trade-offs

## 3. Research only when it pays off
Search when the answer is version-specific, recently changed, or security-relevant. Prefer official docs and release notes over blogs and forums. Skip search for stable fundamentals.

## 4. Compare best practice with status quo
- If status quo is already fine, say so plainly.
- If not, name the gap, why it matters, and the smallest change that closes it.
- Flag anything destructive or hard to reverse, with a rollback step.

## 5. Respond within budget
Lead with the answer. Bundle commands into one script to run once. Cite sources when search was used.