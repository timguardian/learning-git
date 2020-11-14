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

### Merging vs Rebasing

- Two ways to incorporate changes from one branch into another branch
- Similar ends, but the means are different

Merging

- Adds a merge commit
- Nondestructive
- Complete record of what happened and when
- Easy to undo
- Logs can become cluttered, non-linear

Rebasing

- No additional merge commit
- Destructive: SHA changes, commits are rewritten
- No longer a complete record of what happened and when
- Tricky to undo
- Logs are cleaner, more linear

> :warning: **The Golden Rule of Rebasing**  
> Thou shalt not rebase a public branch

- Rebase abandons existing, shared commits and creates new, similar commits instead
- Collaborators would see the project history vanish
- Getting all collaborators back in sync can be a nightmare

How to Choose?

- Merge to allow commits to stand out or to be clearly grouped
- Merge to bring large topic branches back into master
- Rebase to add minor commits in master to a topic branch
- Rebase to move commits from one branch to another
- Merge anytime the topic branch is already public and being used by others (The Golden Rule of Rebasing)

Rebase onto other branches  
`git rebase --onto newbase upstream branch`  
Example: `git rebase --onto master ecommerce new_feature`

Undo a Rebase

- Can undo simple rebases
- Rebase is destructive
- SHAs, commit messages, change sets, and more
- Undoing complex rebases may lose data

Undo, unless ORIG_HEAD has changed again:  
`git reset --hard ORIG_HEAD`  
Undo by rebasing to former merge-base SHA:  
`git rebase --onto 9291f0c88 master new_feature`
