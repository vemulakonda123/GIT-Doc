#AUTHOR:
#
```
git add .
git commit -m "ok"
git remote set-url origin https://<token>@github.com/<username>/<repo>
```
```
git branch -m main master
git fetch origin
git branch -u origin/master master
git remote set-head origin -a
```
```
git log
git show 02kkjdi..
```
### Edit files are at staging area than use reset command 
```
git add .
git status
git reset Head file.txt
git status
this file will be moved to workspace
```

```
git branch
git branch new-branch
git checkout new-branch
git checkout -b new-branch
git branch -d <branch_name>   #delete branch
git branch -m <old_branch_name> <new_branch_name>
git merge <branch_name>
git log --graph --oneline --decorate --all




```
