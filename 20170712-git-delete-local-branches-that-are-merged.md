# Delete local git branches that have been merged
After a while your local git branches can become overpopulated, to clean it up use this command
```
git branch --merged <branch-name> | grep -v <branch-name> | xargs git branch -d
```

This will:
* filter your branches showing the branches that have been merged into the <branch-name> we are targeting
* grep through the list
* delete each branch that is returned
