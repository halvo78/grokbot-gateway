# Contributing

This repository is part of Eli Halvorson's estate and follows the estate
agent contribution contract (`~/workspace/AGENTS.md`, the working-tree
record; this file is its GitHub-facing summary).

## Standing rules

- **Contributor, never approver.** AI agents draft and open pull requests;
  a human understands and defends every changed line before anything
  merges. Agents never merge, force-push, rewrite history, or commit
  directly to `main`/`master`.
- **No orphan work.** Every change links the issue, certification item,
  programme register, or ledger entry it answers.
- **Evidence at delivery.** PRs carry the estate PR template: what, why,
  evidence (test commands + results re-run at delivery time), and an
  explicit **what was NOT done** list. Green claims are timestamped and
  re-verified — never carried forward from an earlier run.
- **Bugs:** a fix ships a reproducer and a regression test named for the
  bug that fails before the fix. If a fix cannot be regression-tested
  (external/provider-side cause), the PR says so and why.
- **Secrets:** never commit credentials, tokens, keys, or session material
  — by value, in any file, log, or comment. Suspect an exposure? Stop and
  follow `SECURITY.md`.
- **Provenance:** agent contributions are labelled
  `Assisted-by: LLM [<tools/models>]` and marked agent-drafted. No
  `Signed-off-by` from an AI — only humans certify.

## Workflow

1. Open or find the issue first (use the templates — blank issues are
   disabled).
2. Branch from the default branch; keep the change to the linked scope.
3. Open the PR with the template filled in, including the NOT-done list.
4. A human reviews and merges. Agents do not merge, including their own
   PRs, and do not close other people's PRs.

## Ask-first classes

Changes to auth/credentials/sandboxing, scheduled-job definitions,
shared ledgers other lanes read, anything that spends money, and this
contract itself are propose-only: open the issue or PR and wait for a
human ruling.

*Canonical template set: `org/github-all-20261123/templates/` in the
estate workspace. Assisted-by: LLM [Muse], agent-drafted 2026-11-23.*
