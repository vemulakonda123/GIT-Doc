#AUTHOR:
#
```
git add .
git commit -m "ok"
git remote -v
git remote add origin https://github.com/vemulakonda123/GIT-Doc.git
git remote set-url origin https://<token>@github.com/<username>/<repo>
git push -u origin main 
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
###Set default editor:
git config --global core.editor "editor_name"
###Set merge tool:
git config --global merge.tool "tool_name"
Sets the default merge tool to be used when resolving merge conflicts. Replace "tool_name" with the name of the merge tool you want to use (e.g., vimdiff, meld, kdiff3, etc.).
###Set alias:
git config --global alias.<alias_name> "command"
Creates a custom alias for a Git command. For example:
git config --global alias.co checkout
This creates an alias co for the checkout command.
###List all configurations:
git config --list
Displays all configurations currently set in Git, including user information, aliases, and more.
###View a specific configuration:
git config <key>
Displays the value of a specific configuration key. For example:
git config user.name
This displays the configured user name.
###Edit the Git configuration file directly:
git config --global --edit
Opens the Git configuration file in your default text editor, allowing you to make manual changes.
```

```
##Git troubleshooting commands
git status: This command shows the status of the working directory and staging area. It helps identify which files are staged, unstaged, or untracked.

git log: Use this command to view the commit history of the repository. It provides information about commits, including commit hashes, authors, dates, and commit messages.

git diff: This command shows the differences between the changes in the working directory and the staging area. It helps identify what changes have been made to files.

git diff --staged: Use this command to see the differences between the changes in the staging area and the last commit. It helps verify what changes are staged for the next commit.

git remote -v: This command lists the remote repositories associated with the local repository. It helps verify the URLs of remote repositories.

git remote show <remote_name>: Use this command to get more information about a specific remote repository, such as the remote branches and the URL.

git reflog: This command displays a log of all the git actions that have been performed in the repository, including commits, merges, resets, etc. It can be helpful in recovering lost commits or branches.

git reset --hard HEAD: This command resets the current branch to the last commit, discarding any changes in the working directory and staging area. Be cautious when using this command as it can result in the loss of uncommitted changes.

git clean -n: This command shows a preview of the untracked files in the working directory that are not being ignored by Git. It helps identify which files would be removed by running git clean -f.

git fsck: Use this command to perform a filesystem check on the Git repository. It helps identify any integrity issues with the repository objects.

git bisect: This command helps find the commit that introduced a bug by performing a binary search through the commit history. It requires marking known "good" and "bad" commits to narrow down the problematic commit.
```
