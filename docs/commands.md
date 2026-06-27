# Commands

pull-apart responds to two comment-based commands on GitHub pull requests.

---

## `/split-pr`

**Where:** Any comment on a pull request (not an issue) in a repository where the app is installed.

**What it does:**

1. Reacts to your comment with a 👍.
2. Classifies the changed files using an AI model:
   - **Single changed file** — returns two complete file versions: one with only refactor-style edits (constants, config, renames, formatting, comments) and one with only behavioral/logic edits.
   - **Two or more changed files** — assigns each file to the *refactor* bucket or the *main logic* bucket. If the model puts everything in one bucket, the app moves one file by heuristic so the split can always proceed.
3. Creates two branches from the PR's base commit and opens two new pull requests against the same base branch.

**Cooldown:** If `/split-pr` is called again on the same PR within **5 minutes**, the app replies with a comment explaining the wait instead of triggering a second split.

**Limitations:**

- Renames in single-file PRs are not yet supported.
- Binary files are rejected in single-file mode.
- Very large files may be rejected depending on the configured input size limit.

---
