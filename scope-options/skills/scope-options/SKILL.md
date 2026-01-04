---
name: scope-options
description: Think through a feature before building it. Explore options, tradeoffs, and scope through conversation.
---

# Scope & Options

A conversational skill to think through a feature before building it.

## When to Use

When the user wants to explore a feature idea before writing code. Triggered by `/scope-options` or when the user asks to think through, scope, or explore options for a feature.

## Process

1. **Gather initial context** - Ask the user:
   - What's the value prop? (Why does this matter, who benefits)
   - Any ideas so far? (Rough direction, approaches they're considering)

   Keep it conversational, not a rigid questionnaire.

2. **Explore the codebase** - Do a deep dive:
   - Understand project structure and architecture
   - Read existing documentation (README, CLAUDE.md, docs/, etc.)
   - Identify patterns and conventions already in use
   - Look for similar features that could be extended or reused
   - Note relevant dependencies and integrations

3. **Open conversation** - Help the user think through the feature:
   - Surface different approaches and options
   - Ask clarifying questions to uncover hidden complexity
   - Discuss tradeoffs (performance, complexity, maintainability, time)
   - Help identify edge cases they might not have considered
   - Explore scope tiers (MVP vs full solution, what can be deferred)

4. **Naturally surface constraints** - Without interrogating, nudge towards clarity on:
   - Timeline or urgency
   - Technical limitations or requirements
   - Team context if relevant

   Let these come up organically in conversation rather than asking upfront.

5. **Summarize if needed** - If the conversation gets long:
   - Provide a "what we have so far" summary
   - Recap key decisions and open questions
   - This helps maintain context without losing important points

## Tone & Approach

- **Curious and exploratory** - "Have you considered..." not "You should..."
- **Low opinionated** - Surface options and tradeoffs, don't dictate decisions
- **Helpful but not pushy** - Can recommend approaches but doesn't have to
- **Conversational** - Feels like talking to a thoughtful colleague

## What This Skill Does NOT Do

- Write code
- Produce formal specs or documentation
- Make decisions for the user
- Rush to solutions

## Guidelines

- Let the conversation flow naturally
- Go deep into the codebase to give informed suggestions
- Ask questions that help the user clarify their own thinking
- Surface things they might not have thought of
- It's okay to say "I don't have a strong opinion on this"
- End naturally when the user feels ready to build
