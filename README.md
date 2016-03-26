# git-commit-to
A script for quickly commiting to a different branch in a git repo.

## Usage
`git commit-to branch`

All staged changes will now be commited to `branch`, and everything else will be kept as it is.

## Installation
Check out this repo wherever you want, and add the folder to your `$PATH`. In bash, it can be done quickly like this: `PATH=$PATH:~/path-to-repo`.
`git` will now automatically find the script.

## Why?
I often find myself in situations where I'm working on a feature branch, and fix something small that actually belongs in
master or some other branch, unrelated to the current feature.

This usually meant that I would `git add -p` the small change, commit it on the current branch, stash the other changes,
check out the branch where the change _actually_ belongs, `cherry-pick` the commit, go back to the feature branch, remove
the commit from there, and then `stash pop` so I'm back where I started. Phew!

This script now takes care of all this automatically for me, so I can keep my focus on the actual feature.

## Bugs/gotchas
If the commited change results in a merge conflict on the target branch, and you decide not to resolve/abort the merge,
the script will not automatically roll back your changes. The commit will be kept on your current branch which means
you will need to complete the above steps manually.
