## Getting more out of Git

@jakerella


Git is not a centralized VCS but a distributed VCS. You can push and pull from any repo

#### Remotes

A remote is anything outside of the local repo.  The remote could be on the same machine, network, or even on a website

`origin` is a convention for the default remote


`git branch -a` shows all branches
`git branch -vv` shows local branches and what they track


`git branch --no-merged` shows branches not merged in
`git diff master..stuff` shows differences from the branch

#### Data integrity

Git uses snapshots.  Every commit is a snapshot of everything in the repository at that time.  The commit hash is almost always unique because its hashed from what the code looks like at that time.

Fix commit message with `git commit --amend`.  If you do this, the commit hash will be different.  Be super careful with amend.

`git reflog` will show amended commits where `git log` doesn't.

Amend will also allow you to add files that you forgot about.

Modify an older commit with `git rebase --interactive`, edit changes and commit with `--amend` then `git rebase --continue`

#### Undoing chnages

`git checkout <filename>` will undo changes to a file you were working on which isn't staged.  It won't remove the new files though.
`git reset HEAD <filename>` will unstage things

After things are committed its harder to undo it.

`git reset --soft` moves marker but doesn't affect staging or working areas
`git reset --mixed` moves marker and only affects staging area
`git reset --hard` resets all versions

- HEAD^ move back one commit from HEAD
- HEAD~x move back x commits from HEAD
- HEAD@{i} move back to reflog index i

#### Stash

`git stash` is great for tucking away something you are in the middle of.
`git stash --include-untracked` pulls in files that aren't in the repo yet.

Make sure your commits are atomic in the sense that they aren't broken


log filters:

- `--no-merges`
- `--author="jakerella"`
- `--before="2014-07-01"`
- `-- src/js/`
- `-S foobar`

#### git bisect

`git bisect` dissects the log.

#### merge, rebase, and cherry-pick

Merging fast forwards when there are no divergent changes.  Start on master, split off on feature branch, make commits, mergin back to master just fast-fowards
