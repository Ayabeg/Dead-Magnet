# Connected Acquisition Systems — Central Work Log

This is the coordination log for the three connected acquisition systems:

1. **Dead Magnet** — public lead-magnet experiences, submissions, delivery, attribution, and conversion events.
2. **EvoCRM Outbound** — consent-aware prospect eligibility, campaigns, sequences, delivery events, replies, follow-ups, and reporting.
3. **Dead Enrichment** — imports, normalization, provenance, verification, CRM detection, scoring, retries, and operator workflows.

The implementation currently lives in the existing shared EvoCRM application rather than in these three empty project repositories. That preserves one CRM source of truth and avoids copying a complete Laravel application into three repositories that currently have no source history. The central coordination log is kept here because `Dead-Magnet` is the lead-magnet project and the protocol identifies it as the preferred coordination point.

## Audit snapshot

- **Audit date:** 2026-10-23.
- **Audit scope:** local history, working trees, branches, remotes, worktrees, and GitHub remote refs for the three named repositories, the existing EvoCRM implementation repository, and the supplied 50k reference repository.
- **EvoCRM local repository:** `/home/mia-aya/Documents/Codex/EvoCrm-ayabeg-copy`.
- **EvoCRM remote:** `https://github.com/Ayabeg/EvoCrm.git`.
- **EvoCRM local branch:** `main` at `58d00a84a6bbdaaec1c72298a6f763c2939609cc`.
- **EvoCRM local-only history at audit:** 222 commits beyond the refreshed remote common ancestor `ff3a1aa4`; the remote `main` had one newer commit, `b772e134`.
- **EvoCRM uncommitted changes:** exactly four user-owned modified files; they were preserved and not staged: `app/Support/ListViewConfig.php`, `resources/js/evo/data/crm-list/cells.tsx`, `resources/js/pages/crm/tickets/ticket-columns.tsx`, and `tests/Feature/SupportQueueTest.php`.
- **Publication decision:** direct push to EvoCRM `main` was unsafe because of divergence. The existing local history was published without rewriting history to `codex/acquisition-verified-20261023`.
- **Verified published tip:** `58d00a84a6bbdaaec1c72298a6f763c2939609cc` on `https://github.com/Ayabeg/EvoCrm/tree/codex/acquisition-verified-20261023`.
- **Dead-Magnet, outbound-system, and Lead-enrichment-system:** each local clone was on an unborn `main` branch with no files outside `.git`; GitHub reported no remote heads or tags for any of them.
- **50k reference:** `https://github.com/Awaisali36/50k-lead-generation-system`, clean at `f3037f0dd72979e9fc06c6d3f543c5af15fe4822` on `main`; it was used for workflow-boundary inspiration only. Its n8n/Airtable/Apify/Gemini implementation was not copied into EvoCRM.

## Development history

Status values follow the requested protocol. A commit is marked `PUSHED_AND_VERIFIED` only when the remote ref was checked with `git ls-remote` and matched the local commit or published branch tip. The EvoCRM branch tip verification also proves that the listed ancestor commits are reachable from GitHub; it does not claim that EvoCRM `main` contains them.

### AUDIT-001 — repository and history audit

- **Date/time:** 2026-10-23T11:59:26+01:00.
- **Repository:** all scoped repositories listed above.
- **Branch:** EvoCRM `main`; empty project clones on unborn `main`; 50k reference `main`.
- **Feature/task:** reconstruct the actual state before publication.
- **Summary:** inspected local commits, uncommitted and untracked files, branches, remotes, worktrees, local divergence, and GitHub remote refs. Mapped the completed three-system work to EvoCRM because the three named project repositories contain no implementation.
- **Important files changed:** none; audit only.
- **Tests/checks:** repository status, branch/worktree inspection, local-only commit count, `git ls-remote` for all five remotes, and divergence calculation. Result: no untracked files in EvoCRM; four preserved user edits; 222 local-only EvoCRM commits before publication; no remote heads in the three empty project repositories; 50k reference clean and synchronized.
- **Commit:** none; read-only audit.
- **GitHub:** not applicable.
- **Push verification:** not applicable.
- **Dependencies:** none.
- **Known limitations:** historical work was performed in EvoCRM, not in the three named empty repositories; the original per-step timestamps and exact file lists are preserved in EvoCRM's project documentation where available.

### PUB-001 — publish the existing EvoCRM implementation history

- **Date/time:** 2026-10-23.
- **Repository:** `https://github.com/Ayabeg/EvoCrm`.
- **Branch:** `codex/acquisition-verified-20261023`.
- **Feature/task:** publish completed local work without rewriting or force-pushing remote `main`.
- **Summary:** reviewed the divergence, performed a push dry run, then published the existing local `main` tip. The remote `main` remains untouched; the new branch contains the 222 local-only commits as one reachable history.
- **Important files changed:** all files already committed in the local EvoCRM history; the four uncommitted user files were not included.
- **Tests/checks:** push dry run succeeded; actual push succeeded; local tip and remote branch ref were compared. Local and remote both returned `58d00a84a6bbdaaec1c72298a6f763c2939609cc`.
- **Commit:** `58d00a84a6bbdaaec1c72298a6f763c2939609cc` — `docs: record transactional mail preflight`.
- **GitHub:** https://github.com/Ayabeg/EvoCrm/commit/58d00a84a6bbdaaec1c72298a6f763c2939609cc
- **Push verification:** `PUSHED_AND_VERIFIED`; `refs/heads/codex/acquisition-verified-20261023` matches the local tip exactly.
- **Dependencies:** AUDIT-001.
- **Known limitations:** the branch is not merged into remote `main`; the remote `main` contains one newer commit and must be reconciled through a normal review/merge process.

### PUB-002 — publish and verify the central work log

- **Date/time:** 2026-10-23.
- **Repository:** `https://github.com/Ayabeg/Dead-Magnet`.
- **Branch:** `main`.
- **Feature/task:** publish the required central work-tracking document.
- **Summary:** committed the audit inventory, cross-repository mapping, historical implementation summary, verification evidence, current statuses, outstanding work, and repository state in `WORK_LOG.md`.
- **Important files changed:** `WORK_LOG.md` only.
- **Tests/checks:** `git diff --check` and staged diff review passed; the push completed; local and remote `main` refs were compared.
- **Commit:** `2a26f5153fc41bd6f5739a3f375909edf53d92a3` — `docs: add connected acquisition work log`.
- **GitHub:** https://github.com/Ayabeg/Dead-Magnet/commit/2a26f5153fc41bd6f5739a3f375909edf53d92a3
- **Push verification:** `PUSHED_AND_VERIFIED`; remote `main` exactly matches the local commit.
- **Dependencies:** AUDIT-001 and PUB-001.
- **Known limitations:** the log’s own follow-up entry is this next documentation commit; the three standalone project repositories remain empty pending an explicit extraction decision.

### PUB-003 — verify the central log's final status

- **Date/time:** 2026-10-23.
- **Repository:** `https://github.com/Ayabeg/Dead-Magnet`.
- **Branch:** `main`.
- **Feature/task:** finish the required work-log update after the initial publication.
- **Summary:** recorded the verified follow-up commit and corrected the repository table to the current central-log tip.
- **Important files changed:** `WORK_LOG.md` only.
- **Tests/checks:** `git diff --check`, staged diff review, push, and local-versus-remote hash comparison passed.
- **Commit:** `5b3b9907bc5e8ae0d2b3ec1e0e2558310f9faa35` — `docs: verify central work log publication`.
- **GitHub:** https://github.com/Ayabeg/Dead-Magnet/commit/5b3b9907bc5e8ae0d2b3ec1e0e2558310f9faa35
- **Push verification:** `PUSHED_AND_VERIFIED`; remote `main` exactly matches this commit.
- **Dependencies:** PUB-002.
- **Known limitations:** no implementation source has been added to the three empty standalone repositories.

### HIST-001 — shared acquisition foundation and documentation

- **Repository/branch:** `https://github.com/Ayabeg/EvoCrm`, `main` history published on `codex/acquisition-verified-20261023`.
- **Status:** `PUSHED_AND_VERIFIED` through PUB-001.
- **Summary:** shared workspace-scoped CRM integration, provenance, consent, suppression, funnel events, data-model documentation, architecture documentation, implementation roadmap, progress log, and testing/acceptance documentation.
- **Representative commits:** `02cac89f` (release documentation), `1e61cd7c` (acquisition release report), `46661ae7` (reliability and boundary hardening), `3d578579` (funnel event uniqueness migration), `a561bdb0` (race-safe subject funnel events).
- **GitHub commits:** https://github.com/Ayabeg/EvoCrm/commit/02cac89f3f81046510e518104e1c11f0be4b1fa5, https://github.com/Ayabeg/EvoCrm/commit/46661ae7c6f706b3f56a9afde1a944a7006f6093, https://github.com/Ayabeg/EvoCrm/commit/3d5785794fdd7e5442aa5dc76bf5a775aab13d48, https://github.com/Ayabeg/EvoCrm/commit/a561bdb04e3c8e800ede9419b8134c903ac37470
- **Tests/evidence:** documented connected workflow gates, migration idempotency checks, Pint, TypeScript, browser smoke, and security review evidence in EvoCRM `docs/final-report.md` and `docs/progress-log.md`.
- **Dependencies/limitations:** uses existing EvoCRM entities rather than creating competing data sources; live provider credentials, deployment secret rotation, and legal review remain external gates.

### HIST-002 — Dead Enrichment ingestion, provider orchestration, and data quality

- **Repository/branch:** EvoCRM; published through PUB-001.
- **Status:** `PUSHED_AND_VERIFIED` through PUB-001.
- **Summary:** incomplete-row retention, CSV and existing-record ingestion, normalization, deterministic re-import behavior, provider adapters, evidence/provenance, retries with backoff, partial-result preservation, robots enforcement, CRM signature detection, modular email verification, address-bound verification projection, duplicate-safe processing, and explainable configurable scoring.
- **Representative commits:** `dd39717c` (retry transient enrichment failures), `b7510d47` (public CRM signatures), `ed59f1b5` (modular email verification), `93b93be9` (configurable verifier adapter), `dea586ed` (robots policy enforcement), `0fecd9b6` (configurable scoring), `cd4ac573` (score-rule input hardening), `5438a835`/`fe929a47`/`d821eef2` (verification and partial-result safety).
- **GitHub commits:** https://github.com/Ayabeg/EvoCrm/commit/dd39717c493e253d26d0acc1b8cd9c1d7f60221b, https://github.com/Ayabeg/EvoCrm/commit/b7510d478ce93f135d186f7a2fffae8ce074dde9, https://github.com/Ayabeg/EvoCrm/commit/ed59f1b5f02dc55246125d16001206a0e2ee80aa, https://github.com/Ayabeg/EvoCrm/commit/93b93be99cc5520b8eb93e443532f6ab6f2550b2, https://github.com/Ayabeg/EvoCrm/commit/dea586dadc515ff13c9c90df5bad680aa78edc90, https://github.com/Ayabeg/EvoCrm/commit/0fecd9b624bf8869e2fee46f3658b40112dc224f
- **Tests/evidence:** provider, retry, partial-result, verifier, robots, and scoring gates are recorded in EvoCRM documentation; the latest connected acquisition gate was 173 tests / 1,217 assertions passed.
- **Dependencies/limitations:** provider-backed mailbox-level verification remains blocked until an approved provider is configured; unknown/catch-all/invalid states remain fail-closed by default.

### HIST-003 — EvoCRM Outbound eligibility, campaigns, execution, replies, and reporting

- **Repository/branch:** EvoCRM; published through PUB-001.
- **Status:** `PUSHED_AND_VERIFIED` through PUB-001.
- **Summary:** explicit consent policy, conservative verification eligibility, suppression rechecks, editable campaigns, templates and preview, durable campaign expansion, per-campaign and workspace-timezone caps, idempotent send claims, provider lifecycle events, reply ingestion/classification, follow-up stop conditions, interested-reply tasks, sanitized HTML, and evidence-aware reporting.
- **Representative commits:** `0332daa5` (explicit consent policy), `207b3d7e` (fail-closed verification), `b15b3d6d` (editable campaigns), `67b24b2c` (daily caps), `3d7798b2`/`0e3b0660` (workspace cap isolation and timezone), `0764a179` (durable large-campaign expansion), `7252050c` (provider lifecycle events), `83cac271` (worker send claims), `754928d9` (idempotent reply ingestion), `098f30c2` (reply classification/tasks), `24e91025` (HTML sanitization), `07618298` (evidence-aware reporting).
- **GitHub commits:** https://github.com/Ayabeg/EvoCrm/commit/0332daa595c93bfa13d0b2b523d98cbd3986213, https://github.com/Ayabeg/EvoCrm/commit/207b3d7e367c1ba17bdb33035f246725ffb2fbb6, https://github.com/Ayabeg/EvoCrm/commit/b15b3d6d9917f0f8d8e945525e5ac54f04272c8e, https://github.com/Ayabeg/EvoCrm/commit/67b24b2c067d2c4af068a178bf1420a89d06c533, https://github.com/Ayabeg/EvoCrm/commit/0764a179ecea15eae17274a23d9893325c0097a4, https://github.com/Ayabeg/EvoCrm/commit/7252050caf8d6d9fec4b2031b7ac7d548846fdee, https://github.com/Ayabeg/EvoCrm/commit/07618298d98c350c314522b3ddb1b02364b971d8
- **Tests/evidence:** outbound lifecycle, cap, reply, suppression, reporting, and connected workflow results are recorded in EvoCRM documentation; the latest full PHP regression was 1,382 tests with 1,381 passed, 36,054 assertions, and 1 skipped.
- **Dependencies/limitations:** transactional delivery and provider event semantics still require deployment credentials and a controlled test mailbox; no live campaign was sent.

### HIST-004 — Dead Magnet Lead Leakage Calculator and conversion path

- **Repository/branch:** EvoCRM; published through PUB-001.
- **Status:** `PUSHED_AND_VERIFIED` through PUB-001.
- **Summary:** transparent calculator inputs and reset behavior, public responsive page, validation, duplicate-safe submissions, distinct delivery/marketing/enrichment consent, shared CRM handoff, queued result delivery with honest failure states, demo request and signed booking attribution, consent-gated analytics, and engagement events.
- **Representative commits:** `3bbd5e21` (calculator reset), `7761eb55` (contact-field rendering), `9335676b` (engagement events), `c75b6c48` (public analytics consent), `0fe30c6f` (signed unsubscribe links), `f8ca0d77`/`58e83570` (signed booking attribution), `cf0268a1` (demo conversion reporting), `aaa61631` (visit throttling), `fc9bedf4`/`45aae861` (public delivery error boundaries).
- **GitHub commits:** https://github.com/Ayabeg/EvoCRM/commit/3bbd5e21a7ef960b9ef8e9a24df8e730ac8efc13, https://github.com/Ayabeg/EvoCRM/commit/9335676b7bf4fead81cec13b66a58a18e946536e, https://github.com/Ayabeg/EvoCRM/commit/c75b6c4836f35de0494ad0ab820d1be26f45e44e, https://github.com/Ayabeg/EvoCRM/commit/58e83570494b1a421068105017132af5211dd09f, https://github.com/Ayabeg/EvoCRM/commit/cf0268a10a414d8da198efc16ac362921079489d, https://github.com/Ayabeg/EvoCRM/commit/aaa61631fd9426e5bd12f1a59056b5f3b3e310f6
- **Tests/evidence:** public desktop and 390px mobile smoke tests passed; signed booking, calculator, inbound, and funnel gates are recorded in EvoCRM documentation.
- **Dependencies/limitations:** outbound enrollment remains separate from lead-magnet submission and requires explicit consent plus all ordinary eligibility and suppression checks.

### HIST-005 — bounded processing and diagnostic redaction

- **Repository/branch:** EvoCRM; published through PUB-001.
- **Status:** `PUSHED_AND_VERIFIED` through PUB-001.
- **Summary:** 100-row resumable contact/deal import pages, 250-contact durable outbound expansion, stale-worker completion guards, and shared diagnostic redaction across SMTP, WhatsApp/SMS, bulk actions, enrichment, imports, lead capture, URL capture, Meta webhooks, and scheduled reports.
- **Representative commits:** `6a794282` (resumable imports), `f926376a` (large outbound audience chunking), `721d2645`/`5439c977`/`27980623`/`28ba56d3`/`be408b57`/`83288f63`/`39aa616d`/`0eca2b25` (diagnostic redaction series), `f1b82522` (shell and localization test alignment).
- **GitHub commits:** https://github.com/Ayabeg/EvoCRM/commit/6a794282075347cde7b9cef665a74e2361710134, https://github.com/Ayabeg/EvoCRM/commit/f926376afb8159ba13e70de81e63bb073dc1cad0, https://github.com/Ayabeg/EvoCRM/commit/0eca2b25a9a58231d72bddbe24184c1b39f16ab7, https://github.com/Ayabeg/EvoCRM/commit/f1b825221513600203190cb3f85d8b9ee116989d
- **Tests/evidence:** latest connected acquisition gate 173 tests / 1,217 assertions; latest full PHP regression 1,382 tests / 1,381 passed / 36,054 assertions / 1 skipped; TypeScript, Vite build, Prettier, ESLint, Pint, and `git diff --check` passed. Existing build warnings are documented.
- **Dependencies/limitations:** four unrelated user edits remain outside this publication and must not be staged by future work.

### REFERENCE-001 — supplied 50k lead-generation repository

- **Repository:** `https://github.com/Awaisali36/50k-lead-generation-system`.
- **Status:** `PUSHED_AND_VERIFIED` as an external reference at `f3037f0dd72979e9fc06c6d3f543c5af15fe4822`; no changes made.
- **Use:** informed bounded, staged processing and scale-conscious queue design only.
- **Not adopted:** its n8n/Airtable/Apify/Gemini architecture was not copied into EvoCRM and no fake provider results were introduced.

## Current status

| Area | Status | Evidence / location |
|---|---|---|
| Shared acquisition model and service boundaries | `PUSHED_AND_VERIFIED` | EvoCRM branch tip `58d00a84`; `docs/architecture.md`, `docs/data-model.md` |
| Dead Enrichment core | `PUSHED_AND_VERIFIED` locally; live provider verification `BLOCKED` | EvoCRM enrichment code and connected tests |
| EvoCRM Outbound core | `PUSHED_AND_VERIFIED` locally; live delivery verification `BLOCKED` | EvoCRM outbound code and lifecycle tests |
| Dead Magnet core | `PUSHED_AND_VERIFIED` in shared EvoCRM implementation | EvoCRM public calculator, CRM handoff, delivery, and funnel tests |
| End-to-end local workflows | `PUSHED_AND_VERIFIED` | connected acquisition gates and browser smoke evidence |
| Security/privacy hardening | `PUSHED_AND_VERIFIED` with documented partial/complete review scopes | EvoCRM final report security entries |
| Release readiness | `BLOCKED` | live provider credentials, deployment `APP_KEY` rotation, and legal review for consentless cold outreach remain external |
| Three named standalone repositories | `NEEDS_REVIEW` | all are empty on GitHub; extraction into separate applications requires an explicit architecture decision |

## Outstanding work

- [ ] Reconcile the published EvoCRM branch with remote `main` through normal review/merge; do not force-push.
- [ ] Decide whether the three empty repositories should remain coordination shells or receive separately deployable extractions. Do not duplicate the Laravel application without that decision.
- [ ] Configure approved provider credentials and a controlled test mailbox for live email verification and transactional-mail delivery checks.
- [ ] Rotate deployment `APP_KEY` in the deployment environment; local source was not changed for this external operation.
- [ ] Obtain legal/product sign-off before enabling any consentless cold-outreach configuration; safe defaults remain consent-required.
- [ ] Resolve or explicitly accept the remaining release-readiness limitations documented in EvoCRM's current roadmap and final report.
- [ ] Keep the four pre-existing user-owned EvoCRM working-tree edits separate from future commits.

## Repository status

| Repository | Local state | GitHub state verified at audit | Publication status |
|---|---|---|---|
| `https://github.com/Ayabeg/EvoCrm` | `main` at `58d00a84`; four preserved user edits | remote `main` at `b772e134`; published branch at `58d00a84` | `PUSHED_AND_VERIFIED` on `codex/acquisition-verified-20261023`; `main` intentionally unchanged |
| `https://github.com/Ayabeg/Dead-Magnet` | `main` at `5b3b9907` | `main` at `5b3b9907` | `PUSHED_AND_VERIFIED`; central log published |
| `https://github.com/Ayabeg/outbound-system` | unborn `main`, no files | no remote heads or tags | no implementation source; no commit made |
| `https://github.com/Ayabeg/Lead-enrichment-system` | unborn `main`, no files | no remote heads or tags | no implementation source; no commit made |
| `https://github.com/Awaisali36/50k-lead-generation-system` | clean `main` at `f3037f0` | `main` at `f3037f0` | reference-only; no changes made |

## Source documentation

The detailed implementation and verification evidence remains in the published EvoCRM history:

- [`docs/final-report.md`](https://github.com/Ayabeg/EvoCRM/blob/codex/acquisition-verified-20261023/docs/final-report.md)
- [`docs/progress-log.md`](https://github.com/Ayabeg/EvoCRM/blob/codex/acquisition-verified-20261023/docs/progress-log.md)
- [`docs/implementation-roadmap.md`](https://github.com/Ayabeg/EvoCRM/blob/codex/acquisition-verified-20261023/docs/implementation-roadmap.md)
- [`docs/architecture.md`](https://github.com/Ayabeg/EvoCRM/blob/codex/acquisition-verified-20261023/docs/architecture.md)
- [`docs/data-model.md`](https://github.com/Ayabeg/EvoCRM/blob/codex/acquisition-verified-20261023/docs/data-model.md)
- [`docs/testing-and-acceptance.md`](https://github.com/Ayabeg/EvoCRM/blob/codex/acquisition-verified-20261023/docs/testing-and-acceptance.md)
