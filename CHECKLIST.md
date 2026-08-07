# Repository review checklist

Apply proportionally; a support-only issue tracker does not need a source audit.

## Orientation

- [ ] Record purpose: source, API, library, issue tracker, binary/release index, or documentation.
- [ ] Record default branch, latest commit/release, supported Minecraft/Paper/Java versions, build system, and upstream links.
- [ ] Read README, contributing guide, security policy, license files, issue templates, and release notes.
- [ ] Distinguish maintained, dormant, placeholder, and archived repositories using evidence.

## Legal and repository hygiene

- [ ] Verify SPDX/license detection against actual files and relevant history.
- [ ] For forks, compare inherited license/notices and identify the fork point.
- [ ] Check bundled dependencies, copied code, binary artifacts, generated files, and attribution.
- [ ] Check whether README, build instructions, support policy, changelog, and contribution guidance match reality.
- [ ] Check branch protection-relevant CI, dependency update automation, reproducible builds, and release provenance where observable.

## Build and compatibility

- [ ] Build from a clean checkout with documented toolchains; record commands and results.
- [ ] Verify dependency versions and repositories; flag abandoned, vulnerable, snapshot, or unpinned inputs with evidence.
- [ ] Check current target APIs against official Paper documentation and exact-version Javadocs.
- [ ] Identify deprecated/internal/NMS/reflection use and whether it is isolated and version-gated.
- [ ] Preserve declared legacy support; propose compatibility shims or bounded version profiles instead of silent breakage.
- [ ] Keep blocking database, filesystem, compression, and network work off the server thread.

## Security and integrity

- [ ] Review command permissions, trust boundaries, parsing, path handling, serialization, SQL, HTTP, update/download logic, and secret handling.
- [ ] Review inventory/session identity and adversarial click/drag/hotbar/offhand/creative/quit/stale-session paths.
- [ ] Review custom-item identity, PDC/data-component preservation, provenance, and amount validation.
- [ ] Review economy/reward/trade/claim flows for atomicity, idempotency, retries, refunds, restart recovery, and duplication windows.
- [ ] Check dangerous defaults and fail-open behavior; do not treat platform protections as the only anti-abuse layer.
- [ ] Scan dependency and CI configuration, but manually validate tool output before creating a finding.

## Pull request history

- [ ] Prioritize merged external PRs touching authentication, permissions, commands, networking, persistence, economy/items, updates, reflection, build/release, or CI.
- [ ] Compare the entire merged diff and follow-up commits; inspect authorship and review context without treating unfamiliar contributors as suspicious.
- [ ] Test behavior when risk justifies it. Record evidence, not intent.

## Before proposing upstream contact

- [ ] Confirm against the latest upstream default branch and supported release.
- [ ] Search open/closed issues and PRs for duplicates or maintainer decisions.
- [ ] Minimize scope and include a practical fix or acceptance criteria.
- [ ] Remove secrets, personal data, proprietary material, and exploit-enabling detail.
- [ ] Get Floris' explicit approval for the exact destination and text.
- [ ] Submit one coherent item; record its URL and avoid piling on.
