# pull-apart — Documentation

This repository contains the official documentation for **pull-apart**, a GitHub App that splits an oversized pull request into two focused PRs — one for refactor/cleanup changes and one for behavioral/logic changes.

Browse the `docs/` folder for guides covering installation, configuration, usage, and self-hosting.

---

## Release Notes

### v0.1.0

- Initial release.
- Webhook verification and GitHub App authentication via installation token.
- `/split-pr` comment trigger with thumbs-up reaction and follow-up comment linking the two new PRs.
- **`@pull-apart /close` command:** Comment on any PR opened by the app to close it and delete its head branch automatically. The command is silently ignored on PRs the app did not open.
