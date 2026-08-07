# Versioning and snapshots

The canonical release identity is stored in `VERSION` and repeated near the top of `README.md`.

## Numbering

- `VERSION` uses semantic versioning and changes only for a deliberate milestone.
- `BUILD` is a repository-wide, zero-padded sequence. Increment it exactly once for every completed task that changes tracked hub content.
- `DATE` is the completion date in `Europe/Amsterdam`, formatted as `YYYY-MM-DD`.
- `TAG` is immutable and follows `v<VERSION>-build.<BUILD>`.
- Read-only research or conversation that produces no tracked change does not create an empty build.

Each published build consists of one reviewed commit on the hub's main branch plus an annotated Git tag. Never move, overwrite, or reuse a published build tag.

## Completion procedure

1. Read `VERSION` before starting and check the latest matching Git tag.
2. Make and verify the scoped changes without staging unrelated work.
3. Increment `BUILD` once and update `DATE` and `TAG` in `VERSION`.
4. Synchronize the version line in `README.md`.
5. Commit the task, create the annotated tag, then push the commit and tag to `mrfdev/ZripsRepos`.
6. Verify that the worktree is clean and the local branch matches the remote.

## Inspecting or rolling back

List snapshots:

```bash
git tag --list 'v*-build.*' --sort=-version:refname
```

Inspect an old snapshot without changing the main branch:

```bash
git switch --detach v1.0.0-build.001
```

Return to current work:

```bash
git switch main
```

For a published rollback, prefer a new commit that reverts the unwanted commit, followed by a new build number and tag. Do not force-push main or move an existing snapshot tag.
