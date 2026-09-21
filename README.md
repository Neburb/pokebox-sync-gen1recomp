# PokéBox Sync — public releases

This repository contains **public release artifacts only** for the private
[`Neburb/gen1recompmod-pokebox-sync`](https://github.com/Neburb/gen1recompmod-pokebox-sync)
project.

The source repository builds a reproducible `.modpkg` package for each pushed
commit and dispatches a publication request here. This repository's GitHub
Action checks out the exact private source commit, runs the release verifier,
and creates an immutable GitHub release containing only the generated package
and its SHA-256 checksum.

The source code is intentionally not mirrored here.

## Release assets

Each release is tagged `commit-<full-source-sha>` and contains:

- `pokebox-sync-<full-source-sha>.modpkg`
- `SHA256SUMS`

The release notes link back to the exact private source commit.

## Maintainer setup

The workflows require a fine-grained GitHub token with:

- read access to `Neburb/gen1recompmod-pokebox-sync`;
- contents write access to this repository.

Store it as `SOURCE_REPO_TOKEN` in this public repository and as
`RELEASE_REPO_TOKEN` in the private source repository. The token is used only
by GitHub Actions and is never written to the generated package.
