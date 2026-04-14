
# Using `copilot-instructions.md`

## Project Overview
This project provides universal, modular Copilot instructions for all major languages, frameworks, and architectures. It is security-focused, project-aware, and extensible. Inspired by best practices from [awesome-copilot-agents](https://github.com/Code-and-Sorts/awesome-copilot-agents), [copilot-security-instructions](https://github.com/Robotti-io/copilot-security-instructions), [agentmd](https://github.com/mikiships/agentmd), and [RuleForge](https://github.com/he-yufeng/RuleForge).

This file provides workspace-specific rules for Copilot and Copilot Chat, covering language, framework, architecture, test, and security modules. It is modular, security-focused, and project-aware.

## Quick Usage
- Place `copilot-instructions.md` at the repository root (already in this workspace).
- Copilot/Chat will read it as a reference. For guaranteed activation, copy it to `.vscode/copilot-instructions.md`.

### Quick Start
```bash
# Copy to your repo root
cp copilot-instructions.md <your-repo>/
# (Optional) For VS Code auto-activation
cp copilot-instructions.md <your-repo>/.vscode/copilot-instructions.md
```

## Features
- Modular: Language, Framework, Architecture, Test, and Security modules auto-activate when relevant.
- Table of Contents for easy navigation.
- Changelog and references for maintainability.

## Supported Languages & Frameworks
- Python (PEP 8, pytest, Django)
- TypeScript/JavaScript (ESLint, Prettier, React, Next.js, Node/Express)
- PHP (Laravel)
- Rust
- Go
- C#

## Example Frontmatter
```yaml
---
scope: project
applyTo:
	- '**/*.py'
	- '**/*.ts'
	- '**/*.js'
	- '**/*.php'
	- '**/*.rs'
	- '**/*.go'
	- '**/*.cs'
description: |
	Universal Copilot instructions for all major languages, frameworks, and architectures. Modular, security-focused, and project-aware. See README.md for usage.
version: 2.0
lastUpdated: 2026-04-14
author: github.com/your-username
---
```

## How to Apply These Instructions
- Reference `copilot-instructions.md` in your prompts for Copilot/Chat.
- Optional modules (Framework, Architecture, Test, Security) are auto-activated if relevant files/frameworks are detected or if you reference them in your prompt.
- Update the changelog at the bottom of the file for major changes.

## Best Practices
- Commit the file to the repository so collaborators and CI bots use the same rules.
- Use small, focused edits and update the changelog when rules change.
- Prefer examples in the same repo language to show the expected style.

## Anti-Patterns to Avoid
- Do not add dependencies without justification.
- Do not commit secrets, credentials, or environment-specific paths.
- Do not skip CI checks or disable linting rules.
- Do not change project structure without consensus.

## Troubleshooting
- If Copilot seems unaware of the file, move it to `.vscode/copilot-instructions.md` or restart the editor window.
- For fine-grained activation, add YAML frontmatter or workspace-specific settings that your Copilot extension supports.

## Limitations & Customization
- These instructions are a strong starting point but should be tailored to your project's unique needs.
- Detection is based on file extensions and conventions, not deep code analysis.
- Review and update the file as your stack evolves.

## References
- [awesome-copilot-agents](https://github.com/Code-and-Sorts/awesome-copilot-agents)
- [copilot-security-instructions](https://github.com/Robotti-io/copilot-security-instructions)
- [agentmd](https://github.com/mikiships/agentmd)
- [RuleForge](https://github.com/he-yufeng/RuleForge)
- [OWASP Top Ten](https://owasp.org/www-project-top-ten/)

## Contributing
Contributions are welcome! Open an issue or pull request to suggest improvements, add new language/framework modules, or report problems.
