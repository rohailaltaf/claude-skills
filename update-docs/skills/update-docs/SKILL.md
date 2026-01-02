---
name: update-docs
description: Updates documentation in the repository after completing work. Use when the user explicitly asks to update docs, refresh documentation, or sync docs with code changes.
---

# Update Documentation

Update human-edited markdown documentation files after completing a piece of work.

## When to Use

Only when the user explicitly requests documentation updates (e.g., "update the docs", "sync documentation", "refresh the readme").

## Process

1. **Ask what to review** - Before analyzing code, ask the user:
   - Uncommitted changes only (staged + unstaged)
   - Committed changes (all commits on current branch)
   - Both uncommitted and committed changes
   - Whole repo (review entire codebase, not just recent changes)

   **For uncommitted/committed/both:**
   - Use `git diff` for uncommitted changes
   - For committed changes, review all commits unique to the current branch (use `git log main..HEAD` or similar)
   - Focus documentation updates on what changed

   **For "Whole repo" option:**
   - Explore the codebase structure (key directories, main files, entry points)
   - Identify features, APIs, and components
   - Compare existing documentation against actual code
   - Look for undocumented features, outdated information, or missing sections
   - This is useful for documentation audits or when docs have drifted significantly from code

2. **Identify documentation files** - Search for:
   - README.md files (root and nested)
   - docs/ or documentation/ folders
   - agents.md, claude.md, or similar project-specific docs
   - Any other .md files that appear to be human-edited

3. **Filter out auto-generated and special files** - Skip:
   - Auto-generated documentation (look for generation comments/headers)
   - LICENSE, LICENSE.md
   - CONTRIBUTING.md
   - CHANGELOG.md, HISTORY.md
   - CODE_OF_CONDUCT.md
   - Files with "auto-generated" or "do not edit" markers

   If the user wants these files updated, ask for explicit confirmation first.

4. **Review existing conventions** - Before making changes:
   - Read the existing documentation style and formatting
   - Match the tone (formal vs casual)
   - Follow existing heading structures
   - Preserve any existing patterns for code examples, links, etc.

5. **If no documentation exists** - Work with the user to initialize:
   - Ask what documentation they want to create
   - Suggest a basic structure based on the project type
   - Start minimal and expand based on feedback

6. **Make targeted updates**:
   - For change-based reviews: only update sections relevant to the changes
   - For whole repo reviews: address gaps, outdated info, and missing documentation
   - Don't rewrite entire documents unnecessarily
   - Add new sections for undocumented features
   - Update existing sections if behavior differs from docs
   - Remove outdated information

## What to Document

Based on the work completed, consider updating:

- **Features/Usage**: New functionality, how to use it, examples
- **Installation/Setup**: New dependencies, configuration options
- **API Reference**: New endpoints, functions, parameters
- **Architecture**: Structural changes, new components
- **Examples**: Working code snippets demonstrating changes

## Guidelines

- Keep documentation concise and scannable
- Use code blocks with appropriate language tags
- Prefer examples over lengthy explanations
- Link to related documentation rather than duplicating
- Maintain consistent formatting with existing docs
