
### Cleaning up Commits  (put all commits into one)
`git rebase master -i` // shows up in vscode and squash the ones I don't want to show up

do  
    `git mergetool` // solve conflict in VS Code  
    `git rebase --continue` // close the editor that shows up and move onto next commit  
while (commits left to squash and merge)

`git push -f` // once done

  
### Updating from Master  
`git checkout <branchName>`     // (if not there already)  
// fix merge conflict if any (rare)  
`git pull master -r`               // pulls from master and updates feature branch at same time  
`git push -f`                           // force push branch

### Updating from Master  
`git checkout <masterName>`     // (if not there already)  
`git pull`  
`git checkout <branchName>`     // (if not there already)  
// fix merge conflict if any (rare)  
`git merge master            
`git push