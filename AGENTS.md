# ZripsRepos project instructions

## Version and snapshot discipline

- Before changing tracked hub content, read `VERSION` and `VERSIONING.md`.
- A completed task that changes tracked hub content must increment `BUILD` exactly once, update `DATE` using the current date in `Europe/Amsterdam`, update `TAG`, and synchronize the version line near the top of `README.md`.
- Keep `BUILD` zero-padded to at least three digits and never reuse a build number.
- Do not change the semantic `VERSION` merely because the build increments. Change it only for an explicitly requested or clearly approved milestone.
- Read-only work with no tracked content change does not create an empty build.
- After verifying the scoped changes, commit them together with the version metadata, create the annotated tag recorded in `VERSION`, and publish the commit and tag to `mrfdev/ZripsRepos` when the task authorizes publication.
- Never move or overwrite a published build tag. Correct a published mistake with a new commit, build number, and tag.
- Do not stage, commit, or tag unrelated user work. If unrelated changes prevent a clean snapshot, report that instead of claiming a completed build.

## External-write boundary

- The snapshot workflow applies only to this `mrfdev/ZripsRepos` review hub.
- Continue to follow `POLICY.md`: never open, modify, or comment on a Zrips issue, pull request, branch, repository, or other upstream resource without Floris explicitly approving the exact external action.

## Documentation factuality

- Treat all public-facing prose as untrusted until it passes the documentation evidence gate in `POLICY.md` and `CHECKLIST.md`.
- After drafting a README, guide, issue, or pull-request description, perform a separate claim-by-claim factual review against current source, configuration, manifests, history, test results, and authoritative project pages.
- Never invent or infer features, commands, permissions, placeholders, dependencies, compatibility, build success, support routes, credits, or versions merely because they are plausible.
- Clearly distinguish public-source facts, released-binary behavior, maintainer statements, runtime verification, and inference. Do not assume source and published artifacts match.
- Remove, qualify, or label unverified claims before presenting a draft as ready. Keep concise evidence paths, commands, citations, or a claim-to-source matrix in the local work record.
