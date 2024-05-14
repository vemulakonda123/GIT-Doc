#AUTHOR:
## initial command in github
![image](https://github.com/vemulakonda123/GIT-Doc/assets/50296141/545bcaca-beb3-41bc-85ab-e869498f5d38)



```
echo "# filerep" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main -----------renamming the name of master
git remote add origin https://github.com/vemulakonda123/filerep.git
git push -u origin main
```
```
git add .
git commit -m "ok"
```
```
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
##when conflict occures than make changes use this command
```
git merge --abort
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


## git tag

Sure, let me provide you with some examples of how to use Git tags:

1. **Creating Lightweight Tags:**

   You can create a lightweight tag in Git simply by providing a name for the tag. Lightweight tags are essentially pointers to specific commits.

   ```bash
   git tag v1.0
   ```

   This command creates a lightweight tag named `v1.0` pointing to the current commit.

2. **Creating Annotated Tags:**

   Annotated tags are like lightweight tags, but they store extra information such as tagger name, email, date, and a tagging message. 

   ```bash
   git tag -a v1.0 -m "Release version 1.0"
   ```

   This command creates an annotated tag named `v1.0` with the message "Release version 1.0".

3. **Pushing Tags to Remote:**

   By default, Git doesn't push tags to the remote repository. You need to explicitly push tags if you want them to be available in the remote repository.

   ```bash
   git push origin v1.0
   ```

   This command pushes the tag `v1.0` to the remote repository named `origin`.

4. **Deleting Tags:**

   To delete a tag, use the `-d` option followed by the tag name.

   ```bash
   git tag -d v1.0
   ```

   This command deletes the tag `v1.0` from your local repository.

5. **Deleting Tags from Remote:**

   To delete a tag from the remote repository, you need to push an empty tag with the same name.

   ```bash
   git push origin :refs/tags/v1.0
   ```

   This command pushes an empty tag named `v1.0` to the remote repository, effectively deleting it.

6. **Listing Tags:**

   You can list all tags in your repository using the `git tag` command.

   ```bash
   git tag
   ```

   This command lists all tags in your local repository.

7. **Checkout a Specific Tag:**

   You can checkout a specific tag to inspect the code at that particular version.

   ```bash
   git checkout v1.0
   ```

   This command checks out the code at the commit pointed to by the tag `v1.0`. You'll be in a "detached HEAD" state, meaning any changes you make won't be on a branch.

These are some common examples of how to use Git tags. Tags are useful for marking significant points in your project's history, such as releases or milestones.
