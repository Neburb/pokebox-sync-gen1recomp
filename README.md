# PokéBox Sync — public releases

This repository contains **public release artifacts only** for the private
[`Neburb/gen1recompmod-pokebox-sync`](https://github.com/Neburb/gen1recompmod-pokebox-sync)
project.

After the private source repository's CI succeeds on `main`, it dispatches a
publication request here. This repository's GitHub Action checks out the exact
private source commit, builds an installable ZIP with the public origin in its
manifest, and creates an immutable GitHub release containing only that ZIP and
its SHA-256 checksum.

The source code is intentionally not mirrored here.

## Release assets

Each release is tagged `vX.Y.Z` and contains:

- `pokebox_sync-X.Y.Z.zip`
- `sha256sums.txt`

The release notes link back to the exact private source commit.

## Maintainer setup

The workflows require the same fine-grained GitHub token in two repository
secrets. It needs read access to `Neburb/gen1recompmod-pokebox-sync` and
contents write access to this repository. Store it as `SOURCE_REPO_TOKEN` here
and as `RELEASE_REPO_TOKEN` in the private source repository. The token is used
only by GitHub Actions and is never written to the generated package.
