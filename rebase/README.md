## Rebase commits

- Take commits from a branch and replay them at the end of another branch
- Useful to integrate recent commits without merging
- Maintains a cleaner, more linear project history
- Ensures topic branch commits apply cleanly

Rebase current branch to tip of master
`git rebase master`
Rebase new_feature to tip of master
`git rebase master new_feature`

Useful for visualizing branches
`git log --graph --all --decorate --oneline`
Return commit where topic branch diverges
`git merge-base master new_feature`
