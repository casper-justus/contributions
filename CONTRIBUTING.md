# Contributing

Thank you for your interest in contributing! Contributions are welcome in the form of bug reports, workflow improvements, new randomization strategies, and documentation fixes.

## Getting Started

1. **Fork** the repository and create a new branch from `main`:
   ```bash
   git checkout -b feat/your-feature-name
   ```
2. Make your changes to `.github/workflows/activity.yml`.
3. Test the workflow by triggering it manually from the **Actions** tab on your fork.
4. Open a **Pull Request** against `main` with a clear description of what changed and why.

## What You Can Contribute

- 🎲 **Randomization improvements** — better dice roll logic, weighted distributions, day-of-week patterns
- ⏰ **Schedule tweaks** — multiple daily triggers, timezone-aware scheduling
- 💬 **Commit message variety** — random commit message pools to make history look more natural
- 📚 **Documentation** — clearer setup guides, FAQ, troubleshooting tips
- 🐛 **Bug fixes** — workflow failures, push permission issues, Actions minute optimizations

## Pull Request Guidelines

- Keep PRs focused — one change per PR
- Use clear commit messages (e.g. `feat: add random commit message pool`)
- Ensure the workflow passes a manual `workflow_dispatch` run before submitting

## Reporting Issues

When reporting a bug, please include:
- The workflow run URL from the Actions tab
- The step that failed and the error message
- Whether the repo is public or private

## Code of Conduct

Be respectful and constructive. Everyone is welcome regardless of experience level.
