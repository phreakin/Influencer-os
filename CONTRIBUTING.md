# Contributing to InfluenceOS

Thank you for your interest in contributing to InfluenceOS!  
We welcome contributions that improve modularity, reliability, security, and developer experience.

---

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [Branch Naming](#branch-naming)
- [Commit Messages](#commit-messages)
- [Pull Request Guidelines](#pull-request-guidelines)
- [Module Standards](#module-standards)
- [Testing Requirements](#testing-requirements)
- [Security](#security)
- [Reporting Issues](#reporting-issues)

---

## Code of Conduct

All contributors are expected to uphold a professional, respectful, and inclusive environment.  
Harassment, discrimination, or abusive behavior of any kind will not be tolerated.

---

## Getting Started

1. Fork the repository
2. Clone your fork locally
3. Create a new branch from `main`
4. Make your changes following the standards below
5. Open a Pull Request against `main`

---

## Development Setup

```bash
# 1. Clone the repository
git clone https://github.com/phreakin/Influencer-os.git
cd Influencer-os

# 2. Install dependencies
npm install

# 3. Configure environment variables
cp .env.example .env
# Edit .env with your local settings

# 4. Start services via Docker Compose
docker compose up -d

# 5. Run tests
npm test

# 6. Start the development server
npm run dev
```

---

## Branch Naming

Use descriptive, kebab-case branch names prefixed by type:

| Prefix      | Purpose                          |
|-------------|----------------------------------|
| `feat/`     | New feature or module            |
| `fix/`      | Bug fix                          |
| `docs/`     | Documentation only               |
| `refactor/` | Code refactoring, no logic change|
| `test/`     | Adding or updating tests         |
| `chore/`    | Build, tooling, or CI changes    |

**Example:** `feat/engagement-campaign-module`

---

## Commit Messages

Follow the [Conventional Commits](https://www.conventionalcommits.org/) spec:

```
<type>(scope): short description

[optional body]

[optional footer]
```

**Examples:**
```
feat(engagement): add campaign scheduling service
fix(auth): resolve JWT token expiry edge case
docs(contributing): update branch naming conventions
```

---

## Pull Request Guidelines

Every PR must:

- Target the `main` branch
- Use **one‑word folder names** for new modules
- Include **unit and integration tests**
- Include **documentation** (inline and/or markdown)
- Include **audit logging** for all state mutations
- Include **risk integration** where applicable
- Pass all CI checks before requesting review
- Be scoped to a single concern (one feature, one fix)

### PR Description Template

```markdown
## Summary
<!-- What does this PR do? -->

## Changes
<!-- List of key changes -->

## Testing
<!-- How was this tested? -->

## Checklist
- [ ] Tests added/updated
- [ ] Documentation updated
- [ ] Audit logging included
- [ ] Risk scoring considered
- [ ] No unrelated changes
```

---

## Module Standards

InfluenceOS modules must be:

| Property         | Requirement                                      |
|------------------|--------------------------------------------------|
| **Isolated**     | No hidden cross-module dependencies              |
| **Typed**        | Full TypeScript types — no `any`                 |
| **Versioned**    | Semantic versioning for all public APIs          |
| **Auditable**    | All mutations emit audit log events              |
| **Risk-aware**   | Integration with the Risk Engine where relevant  |
| **API-first**    | REST + webhook exposure for every capability     |
| **Folder name**  | Single lowercase word (e.g., `engagement`)       |

---

## Testing Requirements

All contributions must include:

- **Unit tests** — isolated logic validation  
- **Integration tests** — cross-service interactions  
- **Contract tests** — API surface stability  
- **Security tests** — access control and input validation  
- **Audit-log validation** — verify audit events are emitted correctly  

Run the full test suite before opening a PR:

```bash
npm test
```

---

## Security

- Never commit secrets, credentials, or tokens
- All inputs must be validated and sanitized
- Report security vulnerabilities privately via GitHub Security Advisories — **do not open a public issue**
- Follow the principle of least privilege for all new roles and permissions

---

## Reporting Issues

- **Bugs:** Open a [GitHub Issue](https://github.com/phreakin/Influencer-os/issues) with a clear reproduction case
- **Feature requests:** Open a GitHub Discussion or submit a PR
- **Security vulnerabilities:** Use GitHub Security Advisories (private disclosure)

---

Thank you for helping build InfluenceOS. 🚀
