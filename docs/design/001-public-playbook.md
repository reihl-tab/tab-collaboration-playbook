# 001 - Public collaboration playbook

Status: proposed. Issue: #1. Scope: documentation only.

## Goal

Make the public-facing working agreement between an owner, Instinct and Tab
repeatable without publishing private operational details. A reader should be
able to follow the numbered setup checklist, identify missing capabilities and
stop at a real approval or provider limitation instead of guessing.

## Decisions

- English and Hebrew guides cover the same setup, handoff and review gates.
- Separate public provider facts from our recommended protocol and untested steps.
- The agent leads setup; the owner's routine manual work is at most opening Tab.
  Provider-required consent, identity checks and unavailable capabilities are
  explicit exceptions, not things this documentation promises to bypass.
- Use only synthetic placeholders. Keep identities, certificates, credentials,
  private records and real communications out of the repository and its history.
- S/MIME protects email content. It is not a website TLS/SSL certificate, does
  not prove legal identity at mailbox-validation level and grants no authority.
- No executable onboarding, production integration, calls, account creation,
  certificate enrollment or email transmission is part of this change.
- Basic documentation/security checks are allowed as repository maintenance;
  they are not a product implementation or an onboarding integration.
- Issue per change, small PRs, independent exact-head review, green CI and a
  normal merge. Never let an author self-certify independent review.

## Alternatives

Reusing a private coordination repository would mix working records with a
public guide. This dedicated repository instead contains only publishable
methodology and public sources. A provider-specific automation script would
claim unsupported capabilities, so the first release uses checked instructions
and explicit capability probes rather than inventing endpoints.

## Verification and release

Check local links, required sections, forbidden private-data patterns, workflow
permissions and source dates. Scan the staged inventory and all git history.
Obtain independent review on the exact head. Keep the repository private until
its public-safe inventory is reviewed and scanned. Public CI must succeed before
normal merge. A provider challenge or unsupported operation is a blocked step,
not successful setup. Never change billing to make checks run.

## Limitations

No new user has been enrolled through this guide. Tab's public pages do not
establish a universal mailbox provisioning API or a universal S/MIME integration.
Live provider UI can change. The guide must report those unknowns plainly.
