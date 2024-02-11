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
```
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
##Set default editor:
git config --global core.editor "editor_name"
##Set merge tool:
git config --global merge.tool "tool_name"
Sets the default merge tool to be used when resolving merge conflicts. Replace "tool_name" with the name of the merge tool you want to use (e.g., vimdiff, meld, kdiff3, etc.).
##Set alias:
git config --global alias.<alias_name> "command"
Creates a custom alias for a Git command. For example:
git config --global alias.co checkout
This creates an alias co for the checkout command.
##List all configurations:
git config --list
Displays all configurations currently set in Git, including user information, aliases, and more.
##View a specific configuration:
git config <key>
Displays the value of a specific configuration key. For example:
git config user.name
This displays the configured user name.
##Edit the Git configuration file directly:
git config --global --edit
Opens the Git configuration file in your default text editor, allowing you to make manual changes.

```
