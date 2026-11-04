# Contributing

Open an issue before a change and link a short design for substantive additions.
Use a fork, a branch off fresh main and one change per PR, with exactly one
signed commit carrying `Closes #N` in its message. Write tests first and follow
the [code-contribution steps](docs/en/workflow.md#issue-to-merge). Use synthetic
examples and public sources. Keep English and Hebrew meaning aligned. State what
was actually tested.

A reviewer other than the author reviews the exact head. Merge only after that
PASS and all required CI checks succeed on that head; no bypass, force push or
self-approval substitute. A head change needs appropriate rereview; tell the
maintainer before changing a head under review. The designated maintainer
reproduces independently, squash-merges pinned to the reviewed SHA and verifies
post-merge checks.

Before public release scan staged files and all history, including commit
metadata. Never include real email addresses, phone numbers, certificate
fingerprints, keys, tokens, personal records, private quotas or actual messages.
Publish generic public-facing practices only, not product implementation internals.

Local check: `python3 scripts/check_docs.py`. Tests: `python3 -m unittest discover -s tests -v`.
No product onboarding code belongs in this docs-only first release.
