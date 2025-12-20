# GitHub Copilot Instructions

## Introduction

This file contains multiple specialized system prompts that guide GitHub Copilot's behavior in different contexts within this repository. Each prompt is designed to activate automatically based on specific conditions, ensuring consistent and context-appropriate assistance throughout your development workflow.

The prompts are organized by category and can be easily extended to accommodate new specialized behaviors as the project evolves.

## Activation Rules

| Prompt ID | Category | Activates When | Status |
|-----------|----------|----------------|--------|
| [CONVENTIONAL-COMMIT-v2.1](#-prompt-conventional-commit-v21) | Commit Messages | Writing commit messages | Active |

## Table of Contents

- [🔖 PROMPT: CONVENTIONAL-COMMIT-v2.1](#-prompt-conventional-commit-v21)

---

## 🔖 PROMPT: CONVENTIONAL-COMMIT-v2.1

**Metadata:**
- **Category:** Commit Messages
- **Activate When:** User is writing commit messages
- **Status:** Active
- **Last Updated:** 2025-12-20

### Instructions

When crafting commit messages, follow the Conventional Commits specification to ensure clear, consistent, and semantic version-friendly commit history.

#### Commit Message Format

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

#### Types

- **feat:** A new feature
- **fix:** A bug fix
- **docs:** Documentation only changes
- **style:** Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
- **refactor:** A code change that neither fixes a bug nor adds a feature
- **perf:** A code change that improves performance
- **test:** Adding missing tests or correcting existing tests
- **build:** Changes that affect the build system or external dependencies
- **ci:** Changes to CI configuration files and scripts
- **chore:** Other changes that don't modify src or test files
- **revert:** Reverts a previous commit

#### Guidelines

1. **Type:** Use lowercase for the type
2. **Scope:** Optional, use lowercase, represents the section of the codebase
3. **Description:**
   - Use imperative, present tense: "change" not "changed" nor "changes"
   - Don't capitalize the first letter
   - No period (.) at the end
   - Keep it concise (50 characters or less recommended)

4. **Body:**
   - Optional, use when description alone is insufficient
   - Separate from description with a blank line
   - Explain *what* and *why* vs. *how*
   - Wrap at 72 characters

5. **Footer:**
   - Optional, used for breaking changes and issue references
   - Breaking changes should start with `BREAKING CHANGE:` followed by a description
   - Reference issues with `Fixes #123` or `Closes #456`

#### Examples

**Simple feature:**
```
feat: add user authentication
```

**Feature with scope:**
```
feat(auth): implement JWT token validation
```

**Bug fix with issue reference:**
```
fix(api): resolve null pointer exception in user endpoint

Fixes #234
```

**Breaking change:**
```
feat(api): redesign authentication flow

BREAKING CHANGE: The authentication endpoint now requires OAuth 2.0 tokens instead of API keys. All clients must update their authentication mechanism.
```

**Commit with body:**
```
refactor(database): optimize query performance

Restructured the database queries to use indexed lookups instead of full table scans. This change reduces query time from ~500ms to ~50ms for user search operations.
```

#### Best Practices

- Keep commits atomic (one logical change per commit)
- Write commit messages that explain why, not just what
- Use the body to provide context when the description isn't self-explanatory
- Reference relevant issues and pull requests
- Ensure the description is meaningful and descriptive

---

