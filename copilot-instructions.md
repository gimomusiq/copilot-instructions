---
scope: project
applyTo: '**/*.{py,ts,js,php,rs,go,cs}'
description: |
  Universal Copilot instructions for all major languages, frameworks, and architectures. Modular, security-focused, and project-aware. See README.md for usage.
version: 2.0
lastUpdated: 2026-04-14
author: github.com/gimomusiq
---

# 🚦 Copilot Universal Instructions 

# Table of Contents
1. [Core Principles](#core-principles)
2. [Output Discipline](#output-discipline)
3. [Universal Style Guidelines](#universal-style-guidelines)
4. [Code Quality](#code-quality)
5. [Safety](#safety)
6. [Architecture (Universal)](#architecture-universal)
7. [Testing](#testing)
8. [Documentation](#documentation)
9. [Refactoring](#refactoring)
10. [Project-Aware Behavior](#project-aware-behavior)
11. [Language Modules](#language-modules-auto-activated)
12. [Framework Modules](#framework-modules-optional-auto-activated)
13. [Architecture Modules](#architecture-modules-optional-auto-activated)
14. [Test Modules](#test-modules-optional-auto-activated)
15. [Security Module](#security-module-optional-owasp-aligned)
16. [Limits](#limits)
17. [Changelog](#changelog)
18. [References](#references)
# --- FRAMEWORK MODULES (optional, auto-activated) ---

# --- ARCHITECTURE MODULES (optional, auto-activated) ---

# --- TEST MODULES (optional, auto-activated) ---

# --- SECURITY MODULE (optional, OWASP-aligned) ---

# --- END LANGUAGE MODULES ---

# --- CHANGELOG ---

- 2026-04-14: Major audit, deduplication, and modularization. Added table of contents, activation guidance, changelog, and references.

# --- REFERENCES ---

- [awesome-copilot-agents](https://github.com/Code-and-Sorts/awesome-copilot-agents)
- [copilot-security-instructions](https://github.com/Robotti-io/copilot-security-instructions)
- [agentmd](https://github.com/mikiships/agentmd)
- [RuleForge](https://github.com/he-yufeng/RuleForge)
- [OWASP Top Ten](https://owasp.org/www-project-top-ten/)

# --- SECURITY MODULE (optional, OWASP-aligned) ---

## Input Validation
- Validate all user input
- Reject or sanitize unsafe data
- Enforce strict types and formats

**Example:**
```python
# Do:
def is_valid_email(email: str) -> bool:
  return re.match(r"^[^@]+@[^@]+\.[^@]+$", email) is not None
# Don't:
def is_valid_email(email): return True
```

## Authentication & Authorization
- Never expose sensitive data
- Enforce least privilege
- Validate permissions on every protected action

**Example:**
```js
// Do:
if (!user.hasPermission('edit')) return res.status(403).send('Forbidden');
// Don't:
// Assume user is allowed without checking
```

## Data Protection
- Never log secrets or sensitive information
- Use secure storage for credentials
- Avoid hardcoding secrets

**Example:**
```php
// Do:
$dbPassword = getenv('DB_PASSWORD');
// Don't:
$dbPassword = 'supersecret';
```

## Secure Coding
- Prevent SQL injection (use prepared statements/ORM)
- Prevent XSS (escape output, sanitize input)
- Prevent CSRF (tokens, same-site cookies)
- Prevent command injection (never pass raw input to shell commands)

**Example:**
```python
# Do:
cursor.execute('SELECT * FROM users WHERE id = %s', (user_id,))
# Don't:
cursor.execute(f'SELECT * FROM users WHERE id = {user_id}')
```

## Error Handling
- Do not leak internal details in error messages
- Log errors securely without exposing sensitive data

**Example:**
```go
// Do:
log.Printf("error: %v", err)
http.Error(w, "Internal server error", 500)
// Don't:
http.Error(w, err.Error(), 500)
```

## Dependencies
- Avoid adding new dependencies unless explicitly requested
- Prefer well-maintained, widely used libraries
- Avoid outdated or unmaintained packages
# --- FRAMEWORK MODULES (optional, auto-activated) ---

## React (JS/TS)
- Use functional components and hooks
**Example (React):**
```jsx
// Do:
function MyButton({ onClick }) {
  return <button onClick={onClick}>Click</button>;
}
// Don't:
class MyButton extends React.Component { /* ... */ }
```

## Next.js
- Use server components when appropriate
**Example (Next.js):**
```js
// Do:
export default function Page() { /* server component */ }
// Don't:
export default function Page() { useEffect(...); /* unnecessary client code */ }
```

## Laravel (PHP)
- Follow Laravel conventions (controllers, models, requests, resources)
**Example (Laravel):**
```php
// Do:
public function store(StoreUserRequest $request) { /* ... */ }
// Don't:
public function store(Request $request) { /* validation in controller */ }
```

## Django (Python)
- Follow Django’s MTV structure
**Example (Django):**
```python
# Do:
class UserView(FormView): ...
# Don't:
def user_view(request): # logic in view
```

## Node/Express
- Keep routes thin; move logic to services
**Example (Express):**
```js
// Do:
router.post('/user', async (req, res) => {
  await userService.create(req.body);
  res.sendStatus(201);
});
// Don't:
router.post('/user', (req, res) => { /* all logic here */ });
```
# ---
# 🚦 Copilot Universal Instructions
## Core Principles
Copilot must produce output that:
- Adapts to project language, style, and conventions


## Output Discipline
- Give concrete, actionable answers only
- No speculation or fabricated details
- Explicitly state when something is unknown
- If multiple options: give top 2–3 with a brief reason
- Ask for clarification if the request is ambiguous
- Ask for clarification when the request is ambiguous.
- Use clear, meaningful names
- Respect language and ecosystem conventions
- Use clear, meaningful names for variables and functions.
- Keep functions small and single-responsibility
- Avoid duplication (DRY)
- Prefer pure functions where possible
- Avoid unnecessary global state
- Use clear error messages (no internal details)
- Prefer pure functions where feasible.
- Use clear error messages without leaking internal details.

## Safety

## Safety
- Always validate input and use safe defaults
- Prevent SQL injection, XSS, CSRF, command injection
## Architecture (Universal)
- Separate domain logic from infrastructure
- Keep modules small and understandable
- Use clear boundaries between layers
- Prefer dependency injection over tight coupling
- Write extensible, not over-engineered, code
- Separate domain logic from infrastructure.

## Testing
- Write tests for realistic scenarios and edge cases
- Use arrange–act–assert structure
- Keep tests fast, stable, deterministic
- Avoid unnecessary mocks; use real components when possible
- Use examples matching the codebase
- Avoid long theory; document only what adds value
- Avoid unnecessary mocks; use real components when practical.

## Refactoring
- Improve readability without changing behavior
- Remove dead code
- Simplify complex expressions
- Split large functions into smaller units
- Keep style and structure consistent
- Document only what adds value.


## Project-Aware Behavior 
- Detect the active language and follow project conventions (lint, format, patterns)
- Analyze existing code and match its style
- Use dependencies/frameworks correctly
- Do not suggest new libraries unless explicitly asked
- Only activate language modules when relevant

## Project-Aware Behavior 
Copilot must automatically:

# --- LANGUAGE MODULES (auto-activated) ---
- detect the active programming language

## TypeScript / JavaScript Module (auto-activate for .ts/.tsx/.js/.jsx)
- Use modern ES/TS features
- Prefer async/await over callbacks
- Use explicit types; avoid `any`
- Respect `tsconfig`, `eslint`, `prettier`
- Do not suggest new dependencies unless asked

**Example (TypeScript):**
```ts
// Do:
async function fetchData(url: string): Promise<Response> {
  return await fetch(url);
}
// Don't:
function fetchData(url) {
  return fetch(url).then(...);
}
```


## Python Module (auto-activate for .py)
- Use idiomatic Python (PEP 8)
- Prefer clear functions over inline logic
- Use type hints where useful
- Avoid unnecessary classes; keep it simple
- Follow project structure and imports

**Example (Python):**
```python
# Do:
def add(a: int, b: int) -> int:
    return a + b
# Don't:
def add(a, b): return a+b
```
- Use modern ES/TS features.

## PHP Module (auto-activate for .php)
- Use modern PHP (7.4+ or 8+)
- Respect PSR standards
- Use clear namespaces
- Avoid magic methods unless necessary
- Prefer dependency injection

**Example (PHP):**
```php
// Do:
namespace App\Service;
class UserService {}
// Don't:
class user_service {}
```
## Python Module (auto-activate for .py)

## Rust Module (auto-activate for .rs)
- Use idiomatic Rust (ownership, borrowing, `Result`)
- Avoid unnecessary `clone`s
- Use clear error handling
- Keep modules small and logical
- Use crates only when explicitly requested

**Example (Rust):**
```rust
// Do:
fn parse_num(s: &str) -> Result<i32, std::num::ParseIntError> {
    s.parse()
}
// Don't:
fn parse_num(s: String) -> i32 { s.parse().unwrap() }
```


## Go Module (auto-activate for .go)
- Use idiomatic Go (simple, explicit)
- Avoid over-engineering
- Use clear error handling (`if err != nil`)
- Keep packages small and logical

**Example (Go):**
```go
// Do:
if err := doThing(); err != nil { return err }
// Don't:
doThing()
```
- Avoid magic methods unless necessary.

## C# Module (auto-activate for .cs)
- Use modern C# features
- Respect project conventions (naming, structure)
- Use `async/await` correctly
- Keep classes small and single-responsibility

**Example (C#):**
```csharp
// Do:
public async Task<int> GetValueAsync() => await Task.FromResult(42);
// Don't:
public int getvalueasync() { return 42; }
```
- Avoid unnecessary `clone`s.
- Use clear error handling.
- Keep modules small and logical.

# --- END LANGUAGE MODULES ---
- Use crates only when explicitly requested.

## Limits
- No invented APIs, libraries, types, or methods
- No assumptions about project structure unless explicitly provided
- Do not generate code that depends on unknown or non-existent systems
- No output inconsistent with the existing codebase
- Use clear error handling (`if err != nil`).
- Keep packages small and logical.

## C# Module (auto-activate for .cs)
- Use modern C# features.
- Respect project conventions (naming, structure).
- Use `async/await` correctly.
- Keep classes small and single-responsibility.

# ---------------------------------------------------------
# END LANGUAGE MODULES
# ---------------------------------------------------------

## Limits
- No invented APIs, libraries, types, or methods.
- No assumptions about project structure unless explicitly provided.
- Do not generate code that depends on unknown or non-existent systems.
- No output that is inconsistent with the existing codebase.
