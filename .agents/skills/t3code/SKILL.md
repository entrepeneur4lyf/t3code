---
name: t3code-conventions
description: Development conventions and patterns for t3code. TypeScript project with mixed commits.
---

# T3code Conventions

> Generated from [entrepeneur4lyf/t3code](https://github.com/entrepeneur4lyf/t3code) on 2026-03-24

## Overview

This skill teaches Claude the development patterns and conventions used in t3code.

## Tech Stack

- **Primary Language**: TypeScript
- **Architecture**: type-based module organization
- **Test Location**: mixed
- **Test Framework**: vitest

## When to Use This Skill

Activate this skill when:
- Making changes to this repository
- Adding new features following established patterns
- Writing tests that match project conventions
- Creating commits with proper message format

## Commit Conventions

Follow these commit message conventions based on 200 analyzed commits.

### Commit Style: Mixed Style

### Prefixes Used

- `fix`
- `feat`
- `chore`

### Message Guidelines

- Average message length: ~55 characters
- Keep first line concise and descriptive
- Use imperative mood ("Add feature" not "Added feature")


*Commit message example*

```text
fix(provider,claude): handle prompt stream interrupt on session stop (#1365)
```

*Commit message example*

```text
feat: add word wrapping setting and in-panel button (#1326)
```

*Commit message example*

```text
refactor(settings): simplify settings layout and controls (#1288)
```

*Commit message example*

```text
ci(github): exclude test files from mixed PR size calculation (#1105)
```

*Commit message example*

```text
chore(release): prepare v0.0.13
```

*Commit message example*

```text
Sort sidebar projects and threads by recency (#1372)
```

*Commit message example*

```text
Surface context window usage in the UI (#1351)
```

*Commit message example*

```text
Preserve terminal history across ANSI control sequences (#1367)
```

## Architecture

### Project Structure: Turborepo

This project uses **type-based** module organization.

### Configuration Files

- `.github/workflows/ci.yml`
- `.github/workflows/issue-labels.yml`
- `.github/workflows/pr-size.yml`
- `.github/workflows/pr-vouch.yml`
- `.github/workflows/release.yml`
- `apps/desktop/package.json`
- `apps/desktop/tsconfig.json`
- `apps/marketing/package.json`
- `apps/marketing/tsconfig.json`
- `apps/server/package.json`
- `apps/server/tsconfig.json`
- `apps/server/vitest.config.ts`
- `apps/web/package.json`
- `apps/web/tsconfig.json`
- `apps/web/vite.config.ts`
- `package.json`
- `packages/contracts/package.json`
- `packages/contracts/tsconfig.json`
- `packages/shared/package.json`
- `packages/shared/tsconfig.json`
- `scripts/package.json`
- `scripts/tsconfig.json`
- `vitest.config.ts`

### Guidelines

- Group code by type (components, services, utils)
- Keep related functionality in the same type folder
- Avoid circular dependencies between type folders

## Code Style

### Language: TypeScript

### Naming Conventions

| Element | Convention |
|---------|------------|
| Files | camelCase |
| Functions | camelCase |
| Classes | PascalCase |
| Constants | SCREAMING_SNAKE_CASE |

### Import Style: Relative Imports

### Export Style: Named Exports


*Preferred import style*

```typescript
// Use relative imports
import { Button } from '../components/Button'
import { useAuth } from './hooks/useAuth'
```

*Preferred export style*

```typescript
// Use named exports
export function calculateTotal() { ... }
export const TAX_RATE = 0.1
export interface Order { ... }
```

## Testing

### Test Framework: vitest

### File Pattern: `*.test.ts`

### Test Types

- **Unit tests**: Test individual functions and components in isolation
- **Integration tests**: Test interactions between multiple components/services

### Mocking: msw


*Test file structure*

```typescript
import { describe, it, expect } from 'vitest'

describe('MyFunction', () => {
  it('should return expected result', () => {
    const result = myFunction(input)
    expect(result).toBe(expected)
  })
})
```

## Error Handling

### Error Handling Style: Try-Catch Blocks


*Standard error handling pattern*

```typescript
try {
  const result = await riskyOperation()
  return result
} catch (error) {
  console.error('Operation failed:', error)
  throw new Error('User-friendly message')
}
```

## Common Workflows

These workflows were detected from analyzing commit patterns.

### Feature Development

Standard feature implementation workflow

**Frequency**: ~9 times per month

**Steps**:
1. Add feature implementation
2. Add tests for feature
3. Update documentation

**Files typically involved**:
- `apps/web/src/*`
- `apps/web/src/components/*`
- `apps/web/src/components/ui/*`
- `**/*.test.*`
- `**/api/**`

**Example commit sequence**:
```
fix(web): add default thread env mode setting (#892)
fix(web): defer diff worker startup until diff opens (#934)
Extract reusable clipboard hook and standardize media queries (#1006)
```

### Test Driven Development

Test-first development workflow (TDD)

**Frequency**: ~4 times per month

**Steps**:
1. Write failing test
2. Implement code to pass test
3. Refactor if needed

**Files typically involved**:
- `**/*.test.*`
- `**/*.spec.*`
- `src/**/*`

**Example commit sequence**:
```
test: add tests for user validation
feat: implement user validation
```

### Feature Or Settings Development With Tests And Docs

Implements a new feature or settings option, updating implementation, tests, and related documentation/UI files.

**Frequency**: ~4 times per month

**Steps**:
1. Implement feature logic in main code file(s)
2. Update or add corresponding test files
3. Update UI components as needed
4. Update documentation or settings files if applicable

**Files typically involved**:
- `apps/web/src/appSettings.ts`
- `apps/web/src/appSettings.test.ts`
- `apps/web/src/components/ChatView.tsx`
- `apps/web/src/routes/_chat.settings.tsx`

**Example commit sequence**:
```
Implement feature logic in main code file(s)
Update or add corresponding test files
Update UI components as needed
Update documentation or settings files if applicable
```

### Backend Adapter Or Provider Enhancement With Tests

Adds or modifies a backend provider/adapter (e.g., Claude, Codex), updating both implementation and test files.

**Frequency**: ~3 times per month

**Steps**:
1. Edit provider/adapter implementation file
2. Edit or add corresponding test file
3. Update related orchestration or service files if needed

**Files typically involved**:
- `apps/server/src/provider/Layers/ClaudeAdapter.ts`
- `apps/server/src/provider/Layers/ClaudeAdapter.test.ts`
- `apps/server/src/provider/Layers/CodexAdapter.ts`
- `apps/server/src/provider/Layers/CodexAdapter.test.ts`

**Example commit sequence**:
```
Edit provider/adapter implementation file
Edit or add corresponding test file
Update related orchestration or service files if needed
```

### Sidebar Or Ui Component Enhancement

Makes improvements or fixes to sidebar or other UI components, often in response to UX/UI feedback.

**Frequency**: ~5 times per month

**Steps**:
1. Edit main component file (e.g., Sidebar.tsx)
2. Edit or add logic/test files for the component
3. Update supporting utility or style files as needed

**Files typically involved**:
- `apps/web/src/components/Sidebar.tsx`
- `apps/web/src/components/Sidebar.logic.ts`
- `apps/web/src/components/Sidebar.logic.test.ts`

**Example commit sequence**:
```
Edit main component file (e.g., Sidebar.tsx)
Edit or add logic/test files for the component
Update supporting utility or style files as needed
```

### Git Service Or Action Enhancement

Enhances or refactors Git service layers or related actions, updating both implementation and test files across server and web.

**Frequency**: ~2 times per month

**Steps**:
1. Edit Git service/manager/core implementation files
2. Edit or add corresponding test files
3. Update related web components or API integration files

**Files typically involved**:
- `apps/server/src/git/Layers/GitCore.ts`
- `apps/server/src/git/Layers/GitCore.test.ts`
- `apps/server/src/git/Layers/GitManager.ts`
- `apps/server/src/git/Layers/GitManager.test.ts`
- `apps/web/src/components/GitActionsControl.tsx`
- `apps/web/src/lib/gitReactQuery.ts`

**Example commit sequence**:
```
Edit Git service/manager/core implementation files
Edit or add corresponding test files
Update related web components or API integration files
```

### Release Or Package Version Bump

Prepares a new release or updates package metadata, typically updating multiple package.json files and lockfiles.

**Frequency**: ~2 times per month

**Steps**:
1. Update version or metadata in package.json files
2. Update lockfile (bun.lock)
3. Optionally update release workflow files

**Files typically involved**:
- `apps/web/package.json`
- `apps/server/package.json`
- `apps/desktop/package.json`
- `packages/contracts/package.json`
- `bun.lock`

**Example commit sequence**:
```
Update version or metadata in package.json files
Update lockfile (bun.lock)
Optionally update release workflow files
```

### Test And Logic Pair Update

Updates or adds logic files together with their corresponding test files, ensuring test coverage for new or changed logic.

**Frequency**: ~3 times per month

**Steps**:
1. Edit or add logic file
2. Edit or add corresponding test file

**Files typically involved**:
- `apps/web/src/composerDraftStore.ts`
- `apps/web/src/composerDraftStore.test.ts`
- `apps/web/src/session-logic.ts`
- `apps/web/src/session-logic.test.ts`

**Example commit sequence**:
```
Edit or add logic file
Edit or add corresponding test file
```


## Best Practices

Based on analysis of the codebase, follow these practices:

### Do

- Write tests using vitest
- Follow *.test.ts naming pattern
- Use camelCase for file names
- Prefer named exports

### Don't

- Don't skip tests for new features
- Don't deviate from established patterns without discussion

---

*This skill was auto-generated by [ECC Tools](https://ecc.tools). Review and customize as needed for your team.*
