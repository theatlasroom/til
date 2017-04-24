# Git merge: Specifying changes to keep in a merge conflict
When you are resolving merge conflicts and you have too many files to fix, but also know exactly which set of changes you want to keep, you can tell git to accept all of either **your** changes or the **other** changes.

`git checkout --theirs # checkout the new work that is being added`
`git checkout --ours # checkout the work from the shared history`

## Gotcha: rebasing
The changes that we think of as theirs or owns may swap around when doing a rebase. [More info on rebasing theirs/ours](https://git-scm.com/docs/git-checkout#git-checkout---ours).
## Links
* [Keep either file in merge conflicts](http://gitready.com/advanced/2009/02/25/keep-either-file-in-merge-conflicts.html)
