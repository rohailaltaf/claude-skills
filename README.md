# Claude Skills

A collection of custom skills for Claude Code.

## Table of Contents

- [update-docs](#update-docs) - Update documentation after completing work
- [scope-options](#scope-options) - Plan mode on steroids

## update-docs

Updates markdown documentation files after completing work. Invoke with `/update-docs` or by asking Claude to update the docs.

The skill will:
- Ask what to review (uncommitted, committed, both, or whole repo)
- Find existing documentation files in your repository
- Update relevant sections based on changes or audit entire docs against codebase

### How it works

1. Invoke the skill with `/update-docs`

![Invoke the skill](docs/update-docs/1.png)

2. Select what changes to review

![Select changes](docs/update-docs/2.png)

3. Claude searches for documentation files and reviews recent changes

![Search and review](docs/update-docs/3.png)

4. Claude proposes updates to your documentation

![Propose updates](docs/update-docs/4.png)

### Installation

```
/plugin marketplace add rohailaltaf/claude-skills
/plugin install update-docs@rohailaltaf-skills
```

## scope-options

Plan mode on steroids. Invoke with `/scope-options` before building a feature.

The skill will:
- Ask structured questions (product first, then technical)
- Push you to define: who benefits, what success looks like, what's MVP, what you're NOT building
- Deep dive into your codebase to inform options
- Present 2-5 concrete options with product AND technical tradeoffs
- Help you narrow down to a direction

Forces engineers to think with a product mindset before writing code.

### How it works

1. Invoke with `/scope-options` and describe what you want to build

![Invoke the skill](docs/scope-options/1.png)

2. Select what you want the feature to do

![What to build](docs/scope-options/2.png)

3. Define what problem it solves

![Problem](docs/scope-options/3.png)

4. Define how you'll know it's successful

![Success metric](docs/scope-options/4.png)

5. Explicitly define what's out of scope

![Out of scope](docs/scope-options/5.png)

6. Answer technical constraint questions

![Constraints](docs/scope-options/6.png)

7. Review concrete options with product and technical tradeoffs

![Options](docs/scope-options/7.png)

8. Select which approach resonates

![Select approach](docs/scope-options/8.png)

9. Get ASCII UI mockups for your chosen approach

![UI mockups](docs/scope-options/9.png)

### Installation

```
/plugin marketplace add rohailaltaf/claude-skills
/plugin install scope-options@rohailaltaf-skills
```
