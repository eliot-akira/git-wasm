# `git-wasm`

This is a fork of [`wasm-git`](https://github.com/petersalomonsen/wasm-git) to merge new features from other forks and pull requests; and further develop the library to enable replacing the use of the `git` CLI in practical contexts.

#### From `rraab-dev/master` [#99](https://github.com/petersalomonsen/wasm-git/pull/99)

- Docker build: Added `Dockerfile` and `docker_cleanup_and_build.sh`
- Updated `libgit2` from version 1.7.1 to 1.8.1
  * Added method `writeArrayToMemory` manually to `post.js`
  * Removed `git_error_clear()` call in `examples/checkout.c`
- Added new commands
  * examples/branch.c: List local and remote branches. Delete local branches.
  * examples/log-last-commit-of-branch.c: Log info about latest commit of a branch.
  * examples/rebase.c: Interactive rebase functionality.
- Changed commands
  * examples/push.c: Does have an optional parameter --force for force pushing. (Needed after a rebase.)
  * examples/fetch.c: Does now --prune by default.
  * examples/init.c: Change default branch to main.
  * examples/diff.c: Added --full-file-content option which allows printing old_file and new_file content if available.
- Added HTTP basic auth for authentication with password or pat.
