# Residence GPL lineage and release-hygiene review

- **Status:** confirmed maintenance finding; no GPL violation established
- **Priority:** `P2` compliance and release hygiene
- **Reviewed:** 2026-08-07
- **Current upstream:** `Zrips/Residence` at `151e4dc6d906245d32f00b842b921fd02ed0fd39`
- **Current public binary inspected:** Residence `6.0.2.4`
- **Scope:** public Git history, current source tree, official public download, embedded jar metadata, and authoritative GPL guidance

This is a technical provenance and distribution review, not legal advice. A lawyer familiar with open-source licensing should decide any disputed legal question.

## Result

Residence is clearly descended from GPLv3-covered Residence code, and its current repository and official `6.0.2.4` jar both still carry the GPLv3 text. Charging for a GPL-covered copy is permitted, so Residence being sold on SpigotMC is not by itself a license problem.

The current evidence does **not** justify accusing Zrips of a GPL violation. It does justify a focused maintenance recommendation because the license is hidden below the repository root, its canonical text was edited in 2017, the README and Maven metadata do not state the license, and release `6.0.2.4` has no matching Git tag. These make the applicable rights and corresponding-source revision harder to identify than necessary.

## Evidence

| Question | Evidence | Assessment |
|---|---|---|
| Is the current project a continuation of the original Residence project? | GitHub identifies `Zrips/Residence` as forked from `bekvon/Residence`; the current history contains the original commits; Zrips' first commit, `217192b5f5d0a7c1e037a6e4d4890dcf58cc2c4e`, modifies many inherited core classes. | Confirmed. |
| Was GPLv3 present before Zrips maintained the project? | Original commit `bc2875fa3be7cfe3770ff53c8904731083f48cf8` from 2011 says “added GPL licence” and adds `LICENCE.txt`; that commit is an ancestor of current `master`. | Confirmed. |
| Does the current source contain a license? | The full text is at `src/main/resources/LICENSE`. There is no root `LICENSE`, `COPYING`, or equivalent. | Present but poorly surfaced. |
| Does the distributed jar contain the license? | Official `Residence6.0.2.4.jar`, SHA-256 `f324fc2cafcaf24cce78dbc3634d2db86ae93bdf61c5c6ef51d631cbebf387f3`, contains `/LICENSE`. Its license SHA-256 exactly matches the current source file: `bc61af0274b3c7117b8b73133e11d9a4b7da962ed329e2ada12c2e34c63f57d9`. The binary was inspected only in temporary storage and is not retained in this hub. | Confirmed positive compliance signal. |
| Is matching source publicly available? | The jar and current `pom.xml` both identify version `6.0.2.4`. Commit `313e88a13389415351b8552e428c3844d82ea3d6` records the version increase seconds after the jar's embedded Maven build timestamp. Current `master` has a later, unreleased code change but retains the same version. | Public source exists, but the exact binary-to-source mapping is probable rather than proven. |
| Is release `6.0.2.4` tagged? | Remote tags include `6.0.2.2` and `6.0.2.3`; no `6.0.2.4` tag was present on 2026-08-07. | Confirmed release-hygiene gap. |
| Is the GPL text verbatim? | Merged PR [#17](https://github.com/Zrips/Residence/pull/17) replaced three placeholders inside the GPL's own “How to Apply” appendix with Residence/Zrips text. The license itself says verbatim copying is allowed but changing the license document is not. | The project notice should be separated from an unmodified canonical license copy. |
| Is the license visible in normal project metadata? | The root README does not state the license, `pom.xml` has no `<licenses>` section, and GitHub does not surface a repository license from the nested resource file. | Confirmed discoverability gap. |

The pre-Zrips history contains many contributor identities, not only the original maintainer. The README's statement that the original author permitted continued premium development is useful context, but it is not enough public evidence to conclude that all inherited contributions were separately relicensed. The safe public assumption remains that inherited GPL-covered code stays GPL-covered unless the relevant copyright holders granted additional rights.

## Relevant GPL points

- GPLv3 sections 4–6 require notices and a copy of the license when covered source or object code is conveyed, and require qualifying access to Corresponding Source for object-code distribution.
- Modified versions conveyed under the GPL must remain licensed under the GPL as a whole, subject to any separately obtained permissions.
- The GPL permits charging any price for copies. A recipient may redistribute a legitimately received GPL copy, with or without charging.
- A moving public branch is helpful but is weaker release evidence than an immutable tag tied to the distributed binary.

Authoritative references:

- [GNU GPLv3 license text](https://www.gnu.org/licenses/gpl-3.0.html)
- [GNU GPL FAQ](https://www.gnu.org/licenses/gpl-faq.html)
- [GNU guidance for checking possible violations](https://www.gnu.org/licenses/gpl-violation.html)
- [Principles of Community-Oriented GPL Enforcement](https://sfconservancy.org/copyleft-compliance/principles.html)
- [Original `bekvon/Residence` repository](https://github.com/bekvon/Residence)
- [Current `Zrips/Residence` repository](https://github.com/Zrips/Residence)
- [Official Residence binary index](https://www.zrips.net/Residence/)

## Recommended approach

### 1. Ask privately before proposing a public compliance claim

Because Floris is already on good terms with Zrips, start with a short private message. Lead with the positive findings: the source is public, the current jar includes the GPL, and paid distribution is allowed. Ask for clarification instead of asserting illegality:

1. Was `6.0.2.4` built from the source state recorded by commit `313e88a13389415351b8552e428c3844d82ea3d6`?
2. Is the intended license GPL version 3 only, or version 3 or later?
3. Would Zrips welcome a small PR that makes the existing GPL status and release-source mapping unambiguous?

Do not ask Zrips to disclose private agreements. If separate relicensing permission exists, a simple maintainer confirmation may be enough to choose the correct public wording, while legal counsel can review anything more complicated.

### 2. Offer one narrow repository-hygiene PR

Subject to the maintainer's answers, propose a single focused patch:

- place an unmodified canonical GPLv3 text at root as `LICENSE`;
- keep that same file packaged at `/LICENSE` in the jar through Maven instead of maintaining an independently editable duplicate;
- add a short README “License” section identifying the chosen GPL variant and preserving original-project credit;
- add Maven `<licenses>` metadata using the confirmed identifier;
- keep project-specific copyright and attribution in a separate `NOTICE`, `COPYRIGHT`, or README section rather than editing the GNU license document;
- add a release checklist requiring an immutable version tag and a source link for every published binary.

The PR should not attempt to rewrite historical authorship, declare that Zrips owns all code, add restrictions on redistribution, or offer a legal opinion.

### 3. Validate before submission

- Confirm the final wording against Zrips' answer and the latest default branch.
- Confirm the root license is detected as the intended GPL variant.
- Build the project from a clean checkout if practical.
- Inspect the resulting jar and verify `/LICENSE` is byte-for-byte the canonical root file.
- Verify the README, POM, packaged jar, GitHub metadata, download page, and release tag do not contradict one another.
- Search again for an existing issue or PR immediately before submission.

### 4. Escalate only if stronger evidence appears

Reclassify this to `P1` only if a distributed binary lacks the license or qualifying Corresponding Source, its actual source materially differs from what is published, or recipients are subjected to an additional restriction incompatible with the GPL. Record the exact artifact and terms first. Prefer private, education-oriented contact; public accusations or legal escalation are inappropriate on the present evidence.
