
### Cleaning up Commits  (put all commits into one)
```ts
git rebase master -i // shows up in vscode and squash the rest

do  
	git mergetool // solve conflict in VS Code  
	git rebase --continue // close the editor that shows up and move onto next  
while (commits left to squash and merge)
	
git push -f // once done
```
  
### Updating from Master  
```ts
git checkout <branchName>  // (if not there already)  
                           // fix merge conflict if any (rare)  
git pull master -r         // pulls from master and updates feature branch at same time  
git push -f                // force push branch
```

### Updating from Master  
```ts
git checkout <masterName>     // (if not there already)  
git pull  
git checkout <branchName>     // (if not there already)  
// fix merge conflict if any (rare)  
git merge master            
git push
```

### If you updated your `.gitignore`
```ts
git rm --cached
git add --all
git commit -m 'blah'
git push
```
