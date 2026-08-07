# ZripsRepos review hub

An unofficial, independent workspace for careful review of public repositories maintained by [Zrips](https://github.com/Zrips/). The goal is to prepare concise, evidence-backed maintenance suggestions without flooding maintainers or publishing exploitable details.

This repository is a review index, not a fork or redistribution of Zrips projects. Local upstream checkouts live under `upstreams/` and are intentionally ignored by Git. Each project keeps its own Git history and remote.

## Ground rules

- Nothing is submitted upstream without Floris reviewing and explicitly approving it.
- Draft findings are not facts. Reproduce, verify, and check current upstream state first.
- Potential vulnerabilities stay out of this public repository until responsibly disclosed and safe to publish.
- Prefer a small number of high-impact, maintainer-friendly reports over bulk lint or cosmetic churn.
- Preserve each upstream project's license, contribution rules, supported versions, and coding style.
- Do not commit plugin JARs, decompiled proprietary code, credentials, server data, crash dumps, or personal information.

Start with [POLICY.md](POLICY.md), then use [CHECKLIST.md](CHECKLIST.md) and the matching file under `repositories/`.

## Layout

```text
ZripsRepos/
├── POLICY.md                 public/private and upstream-action rules
├── CHECKLIST.md              reusable review checklist
├── INVENTORY.md              repository scope and activity tiers
├── knowledge/                reusable, verified cross-project lessons
├── repositories/<name>/      public-safe notes and per-project queue
├── templates/                finding and upstream-proposal templates
├── upstreams/<name>/         ignored independent Git clones
└── private/                  ignored embargoed/security material
```

## Status

Initial workspace setup. No security conclusion, issue, pull request, or endorsement is implied by a repository being listed here.
