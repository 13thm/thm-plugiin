# /project:review

Project-specific code review command.

## Description

Performs a comprehensive code review of the current changes or specified files.

## Usage

```
/project:review [path]
```

## Parameters

- `path` (optional): Specific file or directory to review
- If no path provided, reviews all staged changes

## What It Checks

- Code style compliance
- Security vulnerabilities
- Performance issues
- Test coverage
- Documentation completeness

## Examples

```
/project:review
/project:review src/components/
/project:review src/utils/helper.js
```

## Notes

- Requires at least one file to review
- Provides specific, actionable feedback
- Suggests improvements when applicable
