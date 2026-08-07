# Review and publication policy

## 1. Authority and upstream actions

This hub is read-only toward Zrips repositories by default. Codex may inspect public code, history, issues, pull requests, releases, and documentation; build and test local checkouts; and draft local reports.

Codex must stop for explicit approval before any external write, including opening or commenting on an issue or pull request, pushing a branch or fork, contacting a maintainer, publishing a vulnerability, or changing content on zrips.net. Approval for one action does not authorize later actions.

## 2. Public repository boundary

Safe to publish after review:

- links and commit hashes for already-public material;
- reproducible, non-sensitive maintenance findings;
- license and documentation observations;
- proposed patches that respect the upstream license;
- high-level status, methodology, and checklists.

Never publish here:

- credentials, tokens, private correspondence, personal/server data, or paid plugin binaries;
- decompiled or reconstructed proprietary source;
- third-party code copied without compatible licensing and attribution;
- uncoordinated exploit details, working abuse payloads, or precise bypass instructions;
- claims of compromise, malicious intent, or a backdoor without strong verified evidence.

Ambiguous material goes in the ignored `private/` directory until reviewed.

## 3. Finding lifecycle

Use these states: `lead` → `reproduced` → `confirmed` → `drafted` → `approved` → `submitted` → `resolved`.

- `lead`: something worth checking; not ready to report.
- `reproduced`: behavior observed with recorded versions and steps.
- `confirmed`: impact, affected scope, and current upstream state independently checked.
- `drafted`: a concise maintainer-facing proposal exists.
- `approved`: Floris explicitly approved the exact external action and text.
- `submitted`: external URL and date recorded.
- `resolved`: fixed, rejected with rationale, duplicate, or no longer applicable.

Public files should normally contain only confirmed or safely worded maintenance leads. Security-sensitive leads remain private.

## 4. Priority

- `P0 Critical`: active exploitation, credential/code execution, destructive data loss, or reliable duplication with broad impact. Handle privately and immediately.
- `P1 High`: serious security/integrity bug, recurring corruption, major license/compliance risk, or breakage on a currently supported platform.
- `P2 Medium`: meaningful reliability, compatibility, performance, API, build, or documentation issue.
- `P3 Low`: contained cleanup, minor quality-of-life improvement, or low-impact modernization.

Priority combines impact, confidence, affected users, current relevance, exploitability, and remediation cost. Popularity alone does not raise priority.

## 5. Evidence and tone

Every proposed report identifies the repository, exact commit/version, environment, observed behavior, expected behavior, reproduction or source path, impact, confidence, and a narrowly scoped remedy. Separate observed facts from inference.

Write as a helpful peer: neutral, specific, short, and easy to act on. Avoid generated bulk changes, speculative accusations, style-only rewrites, and demands. Check for an existing report or fix immediately before submission.

## 6. Documentation accuracy and anti-slop gate

Every README, guide, issue draft, pull-request description, and other public-facing proposal must receive a separate factual review after drafting and before approval. Fluent prose is not evidence, and AI-generated text is never accepted on confidence alone.

- Trace each factual claim to the exact current source, configuration, manifest, history, test result, or authoritative project page that supports it.
- Verify commands, arguments, permissions, defaults, placeholders, dependencies, supported versions, features, build steps, installation paths, downloads, credits, and support routes individually when they are mentioned.
- Distinguish what was observed in public source, reproduced at runtime, stated by the maintainer, or inferred. Qualify the wording when evidence covers only one of those scopes.
- Never assume that a public checkout, published binary, website, release, or development branch contains identical behavior or versions. Record or disclose relevant mismatches.
- Do not claim that a build or test succeeds unless it was actually run against recorded inputs. Describe missing build tooling and unverified runtime behavior honestly.
- Prefer durable links and dynamic badges over copied counts or versions that will drift. Date any unavoidable snapshot data.
- Remove filler, guessed capabilities, invented examples, unsupported compatibility claims, and plausible-sounding details that cannot be backed up.
- If a claim cannot be verified, omit it, mark it clearly as unverified, or request maintainer confirmation before proposing publication.

The factual review must be visible in the local work record through source paths, commands, citations, or a concise evidence matrix. A draft does not advance to `approved` until this gate passes.

## 7. Licensing

Record the detected repository license, relevant file paths, inherited/fork history, and uncertainty. Do not infer permission merely because source is visible. License findings are informational until original history and authoritative license text are checked. Preserve notices and attribution in any proposed patch.

This review hub itself has no outbound license yet; choose one deliberately before public collaboration or reuse is invited.
