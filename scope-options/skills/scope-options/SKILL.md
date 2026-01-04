---
name: scope-options
description: Plan mode on steroids. Push engineers to think with a product mindset before building. Structured intake, then concrete options.
---

# Scope & Options

Plan mode on steroids. Help engineers think like product people before writing code.

## When to Use

When the user wants to scope a feature before building it. Triggered by `/scope-options` or when the user asks to think through, scope, or explore options for a feature.

## Process

### 1. Quick Scan (Fast)

Do a quick, lightweight scan to get the lay of the land:
- Project structure (main directories, tech stack)
- Read key docs (README, CLAUDE.md) if they exist
- Note high-level patterns

This should be fast - don't go deep yet. Just enough to have context.

### 2. Ask What They're Building

Use `AskUserQuestion` to get the basic idea:
- **What do you want to build?** (free text)
- **Who is this for?** (Internal team, End users, Developers/API consumers, Multiple audiences)

Just these two questions first. Get the core idea before going deeper.

### 3. Targeted Deep Dive

Now that you know what they want to build, explore the relevant parts of the codebase:
- Look for similar features that could be extended or reused
- Understand patterns in the areas you'll likely touch
- Note relevant dependencies and integrations
- Find code they mentioned or that's clearly related

Skip parts of the codebase that aren't relevant to what they're building.

### 4. Product & Technical Questions

Use `AskUserQuestion` for remaining questions. Ask in batches of 2-4.

**Product questions:**

- **What problem does it solve?**
  - Free text - what pain point or need does this address?

- **How will we know it's successful?**
  - Options: User engagement metrics, Revenue/conversion, Time saved, Error reduction, User feedback, Not sure yet

- **What's the smallest version that delivers value?**
  - Free text - push them to think MVP

**Technical questions:**

- **Any initial ideas on approach?**
  - Free text - what have they already considered?
  - Mention similar features you found as options

- **What are the constraints?**
  - Multi-select: Tight timeline, Must use existing tech stack, Needs to integrate with X, Performance critical, Security sensitive, None

- **What's the risk if we don't build this?**
  - Options: Users churn, Revenue loss, Technical debt grows, Team productivity suffers, Low risk - it's a nice-to-have

- **What are we explicitly NOT building?**
  - Free text - force them to set boundaries

### Ongoing Exploration

Return to the codebase as needed throughout the conversation:
- When user mentions specific features or systems, go look at them
- To answer questions about how a specific option would work
- To validate assumptions before presenting options

Don't hesitate to explore multiple times. It's better to look things up than to guess.

### 5. Present Options (2-5 options)

Present concrete options as soon as you have enough context. Each option should address BOTH product and technical dimensions:

```
## Option A: [Name]

**What it is:** [1-2 sentence description]

**Product lens:**
- Delivers value to: [who]
- Time to value: [fast/medium/slow]
- Supports future iteration: [yes/no/partially]

**Technical lens:**
- Approach: [brief technical approach]
- Builds on: [existing code/patterns it leverages]
- Effort: [low/medium/high]

**Tradeoffs:**
- Pros: ...
- Cons: ...

---

## Option B: [Name]
...
```

Always include:
- At least one "lean/MVP" option
- At least one "more complete" option
- Note which option you'd recommend and why (if you have a view)

**ASCII UI mockups** - When the feature involves UI, include simple ASCII mockups to illustrate options:

```
Option A: Modal approach        Option B: Inline approach

┌─────────────────────┐        ┌─────────────────────┐
│  Page content       │        │  Page content       │
│                     │        │  ┌───────────────┐  │
│   ┌───────────┐     │        │  │ Form inline   │  │
│   │   Modal   │     │        │  │ here          │  │
│   │   Form    │     │        │  └───────────────┘  │
│   └───────────┘     │        │                     │
└─────────────────────┘        └─────────────────────┘
```

This helps visualize different approaches quickly without building anything.

### 6. Discuss and Refine

After presenting options, use `AskUserQuestion` to:
- Get their initial reaction (which options resonate?)
- Dig deeper into options they're interested in
- Surface edge cases and hidden complexity
- Help narrow down or combine approaches

### 7. Summarize

If conversation gets long, provide a summary:
- Which option(s) they're leaning toward
- Key decisions made
- Open questions remaining
- What's explicitly out of scope

### 8. Transition to Plan Mode

Once an option is chosen, use `AskUserQuestion` to ask if they're ready to plan implementation.

If yes, use the `EnterPlanMode` tool and provide context for the planning phase:

```
## Planning Context

**Chosen approach:** [Option name and brief description]

**Who it's for:** [from intake]

**Success looks like:** [from intake]

**MVP scope:** [what's in v1]

**Out of scope:** [what we're NOT building]

**Constraints:** [timeline, tech, etc.]

**Relevant existing code:** [what to build on from codebase exploration]
```

This hands off everything learned during scoping so plan mode can focus on implementation details.

## Key Principles

- **Product before technical** - Ask about who/why/success before how
- **Force boundaries** - Make them say what they're NOT building
- **MVP mindset** - Always surface the smallest valuable version
- **Use the question UI** - Never ask questions in plain text, always use `AskUserQuestion`
- **Get to options fast** - Don't over-discuss, present concrete choices
- **Effort not time** - Use low/medium/high, never give time estimates

## What This Skill Does NOT Do

- Write code
- Produce formal specs or documentation
- Make decisions for the user
- Give time estimates
- Let engineers skip the product questions
