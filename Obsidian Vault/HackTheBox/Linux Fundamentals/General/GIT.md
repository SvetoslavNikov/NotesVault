2222222222222222222222222222222222222222222### HEAD
Head refers to the current working branch
head -> master - means you are working on the 

|**Command**|**Explanation**|
|---|---|
|`git status`|Shows the status of the working directory and staging area (modified, staged, untracked files).|
|`git log`|Displays the commit history (list of commits, with hash, author, and commit messages).|
|`git log --oneline`|Displays a simplified commit history with just commit hashes and messages, one per line.|
|`git diff`|Shows changes between the working directory and the index (staged files).|
|`git diff --staged`|Shows changes that have been staged (added to the index) but not yet committed.|
|`git add <file_name>`|Stages specific file(s) for the next commit.|
|`git add .`|Stages all changes (new, modified, deleted files) for the next commit.|
|`git checkout -b <branch-name>`|Creates and switches to a new branch.|
|`git switch -c <branch-name>`|Alternative to `git checkout -b`, creates and switches to a new branch.|
|`git checkout <branch-name>`|Switches to an existing branch.|
|`git switch <branch-name>`|Alternative to `git checkout`, switches to an existing branch.|
|`git merge <branch-name>`|Merges the changes from another branch into the current branch.|
|`git rm --cached <file-name>`|Removes a file from Git’s tracking but keeps it in the working directory.|
|`git restore <file-name>`|Discards changes in the working directory and restores a file to the last committed state.|
|`git reset --soft <commit-hash>`|Resets the HEAD to a specific commit, but keeps changes in the working directory and staging area.|
|`git reset --hard <commit-hash>`|Resets HEAD and the working directory to a specific commit, discarding all changes.|
|`git branch -d <branch-name>`|Deletes a local branch (safe, only if fully merged).|
|`git branch -D <branch-name>`|Force deletes a local branch, even if it’s unmerged.|
|`git push origin <branch-name>`|Pushes the local branch to the remote repository.|
|`git push --all`|Pushes all branches to the remote repository.|
|`git push --force`|Force-pushes changes to the remote repository (overwrites history, use with caution).|
|`git pull`|Fetches changes from the remote repository and merges them into the current branch.|
|`git clone <repository-url>`|Clones a repository from a remote source to your local machine.|
|`git tag <tag-name>`|Creates a lightweight tag at the current commit.|
|`git tag -a <tag-name> -m "message"`|Creates an annotated tag with a message.|
|`git push origin <tag-name>`|Pushes a specific tag to the remote repository.|
|`git push --tags`|Pushes all tags to the remote repository.|
|`q`|Exits the `git log` viewer.|
