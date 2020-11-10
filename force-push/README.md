## Force push to a remote

> :warning: **Use with extreme caution**

Commands to execute:
```git push -f origin branch_name```  
```git push --force origin branch_name```

Reasons to force push:
* local version is better than the remote version
* remote version went wrong and needs repair
* versions have diverged and merging is undesirable

> :warning: **Remember:** after you perform forced push, your collaborators need to run  
```git reset --hard origin/branch_name```  
in order to be up to date with remote and undo their features