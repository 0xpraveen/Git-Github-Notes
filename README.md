# Git and GitHub Command Cheat Sheet

This repository provides a concise reference guide for common Git and GitHub commands.


# Git

## 1. Basics Of Git 

| Command                  | Description                                                                                         |
|--------------------------|-----------------------------------------------------------------------------------------------------|
| `git init`               | Use `git init` to create a new git repository.                                                      |
| `git status`             | `git status` gives information on the current status of the git repository and its content.         |
| `git add file1 file2`   | Use `git add` to add specific files to the staging area.                                            |
| `git add .`              | Use `git add .` to stage all changes at once.                                                       |
| `git commit`             | Running `git commit` will commit all staged changes, opening a text editor for a commit message.    |
| `git commit -m "message"`| The `-m` flag allows passing an inline commit message without launching a text editor.              |

## 2. Commits In Details

| Command                    | Description                                                                                                 |
|----------------------------|-------------------------------------------------------------------------------------------------------------|
| `git commit -m 'message'`  | Use `git commit -m 'message'` to commit changes with an inline commit message.                                |
| `git add forgotten_file`   | Use `git add forgotten_file` to stage a file that was previously forgotten before committing.               |
| `git commit --amend`       | `git commit --amend` allows you to amend the previous commit. This is useful for adding changes or fixing a typo in the commit message without creating a new commit. Suppose you just made a commit and then realized you forgot to include a file! Or, maybe you made a typo in the commit message that you want to correct. Rather than making a brand new separate commit, you can "redo" the previous commit using the –amend option.

## 3. Working With Branches

| Command                         | Description                                                                                             |
|---------------------------------|---------------------------------------------------------------------------------------------------------|
| `git branch`                    | Use `git branch` to view your existing branches.                                                       |
| `git branch <branch-name>`      | Use `git branch <branch-name>` to make a new branch based upon the current HEAD.                        |
| `git switch <branch-name>`      | Once you have created a new branch, use `git switch <branch-name>` to switch to it.                     |
| `git checkout <branch-name>`    | We used `git checkout <branch-name>` to switch branches. Older tutorials use checkout instead of switch. Both now work. |
| `git switch -c <branch-name>`   | Use `git switch -c <branch-name>` to create a new branch and switch to it all in one go. Remember `-c` as short for "create". |
| `git branch -v`                 | Use the `-v` flag with `git branch` to view more information about each branch.                         |

## 4. Merging Branches

| Command                         | Description                                                                                             |
|---------------------------------|---------------------------------------------------------------------------------------------------------|
| `git switch master`             | To merge the bugfix branch into master, switch to or checkout the branch you want to merge the changes into (the receiving branch). |
| `git merge bugfix`              | Use the `git merge` command to merge changes from a specific branch into the current branch.            |
| `git branch -d bugfix`          | Deleting a Branch: Use `git branch -d bugfix` to delete the bugfix branch once it's merged successfully.|

## 5. Comparing Changes With Git Diff 

| Command                            | Description                                                                                                               |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------|
| `git diff`                         | Compare Staging Area and Working Directory: Without additional options, `git diff` lists all changes not staged for the next commit. |
| `git diff HEAD`                    | `git diff HEAD` lists all changes in the working tree since your last commit.                                             |
| `git diff --staged`                | `git diff --staged` or `git diff --cached` lists changes between the staging area and the last commit.                     |
| `git diff HEAD [filename]`         | View changes within a specific file by providing `git diff` with a filename.                                               |
| `git diff --staged [filename]`     | Similar to above, but specifically for changes staged for the next commit.                                                 |
| `git diff branch1..branch2`        | List changes between the tips of `branch1` and `branch2`.                                                                  |
| `git diff commit1..commit2`        | Compare two commits by providing their commit hashes.                                                                      |

## 6. The Ins and Outs of Stashing 

| Command                          | Description                                                                                                              |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| `git stash`                      | `git stash` is a super useful command to save changes that are not yet ready to commit. Stashes changes for later use. |
|                                  | [You can also use `git stash save` instead.]                                                                              |
| `git stash pop`                  | Use `git stash pop` to remove the most recently stashed changes and re-apply them to your working copy.                |
| `git stash apply`                | Use `git stash apply` to apply stashed changes without removing them from the stash.                                    |
| `git stash -u`                   | Use `git stash -u` to include untracked files in the stash.                                                              |
| `git stash list`                 | Run `git stash list` to view all stashes.                                                                                |
| `git stash apply stash@{2}`      | Apply a particular stash by specifying its index, e.g., `git stash apply stash@{2}`.                                    |
| `git stash drop stash@{2}`       | Delete a particular stash by its index, e.g., `git stash drop stash@{2}`.                                               |
| `git stash clear`                | To clear out all stashes, run `git stash clear`.                                                                         |

# Github

## 1. Basics 

| Command                              | Description                                                                                                                            |
|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| `git remote -v`                      | To view any existing remotes for your repository, run `git remote` or `git remote -v` (verbose, for more info).                      |
|                                      | This displays a list of remotes. If you haven't added any remotes yet, you won't see anything.                                        |
| `git remote add <name> <url>`        | To add a new remote, provide both a URL and a label to Git using `git remote add <name> <url>`.                                      |
| `git remote add origin <url>`        | When using the name "origin", it typically refers to a specific GitHub repository URL.                                                |
| `git push <remote> <branch>`         | To push work to GitHub, use `git push <remote> <branch>`. Specify the remote to push to and the local branch to push up to that remote. |
| `git push origin master`             | `git push origin master` tells Git to push the master branch to the origin remote (typically GitHub).                                   |

## 2. Fetching and Pulling 

| Command                                  | Description                                                                                                                                         |
|------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| `git branch -r`                          | View the remote branches that our local repository knows about.                                                                                      |
| `git branch`                             | Lists all local branches, indicating the currently active branch with an asterisk.                                                                   |
| `git switch puppies`                     | Creates a new local branch named "puppies" from the remote branch of the same name. Sets it up to track the remote branch `origin/puppies`.           |
| `git checkout --track origin/puppies`    | The new command `git switch` makes this easy to do! It used to be slightly more complicated using `git checkout`.                                   |
| `git fetch <remote>`                     | Fetches branches and history from a specific remote repository. Updates remote tracking branches.                                                  |
|                                          | For example, `git fetch origin` would fetch all changes from the `origin` remote repository.                                                        |
| `git fetch <remote> <branch>`            | Fetches a specific branch from a remote repository. For example, `git fetch origin master` retrieves the latest information from the `master` branch. |
| `git pull <remote> <branch>`             | Pulls changes from a remote branch into the current local branch.                                                                                    |
|                                          | For example, `git pull origin master` fetches the latest information from the `origin master` branch and merges it into the current branch.          |
| `git pull`                               | If run without specifying a particular remote or branch, Git assumes the following:                                                                  |
|                                          | - Remote defaults to `origin`.                                                                                                                      |
|                                          | - Branch defaults to the tracking connection configured for the current branch.                                                                      |

## 3. Rebasing  

| Command                              | Description                                                                                                                     |
|--------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| `git switch feature`                 | Switches to the `feature` branch.                                                                                               |
| `git rebase master`                  | Rebases the current branch onto `master`.                                                                                       |
| `git rebase -i HEAD~4`               | Runs `git rebase` in interactive mode, allowing for editing commits, reordering, dropping commits, etc. Specify the number of commits to rewrite. |

## 4. Tags  

| Command                                     | Description                                                                                                   |
|---------------------------------------------|---------------------------------------------------------------------------------------------------------------|
| `git tag`                                   | Prints a list of all tags in the current repository.                                                          |
| `git tag -l "*beta*"`                      | Searches for tags that match a particular pattern.                                                            |
| `git checkout <tag>`                        | Checks out the state of the repository at a particular tag.                                                   |
| `git tag <tagname>`                         | Creates a lightweight tag, referring to the commit that `HEAD` is pointing to by default.                     |
| `git tag -a <tagname>`                      | Creates a new annotated tag, allowing additional information to be added.                                    |
| `git tag <tagname> <commit>`                | Tags an older commit by providing its commit hash.                                                            |
| `git tag -f <tagname>`                      | Forcefully assigns a tag to a commit, overwriting if it already exists.                                       |
| `git tag -d <tagname>`                      | Deletes a tag.                                                                                                |
| `git push --tags`                           | Pushes tags to remote servers.                                                                               |
|                                             | By default, `git push` doesn't transfer tags. Use `--tags` option to push all tags to the remote server.      |

## 5. Hashing and Objects 

| Command                                           | Description                                                                                                      |
|---------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| `git hash-object <file>`                         | Generates the unique SHA-1 hash for data stored in the `.git/objects` directory.                                 |
| `echo 'hello' \| git hash-object --stdin`        | Uses content from stdin to generate a SHA-1 hash.                                                               |
| `echo 'hello' \| git hash-object --stdin -w`     | Writes the object to the Git database, rather than just outputting the key.                                      |
| `git cat-file -p <object-hash>`                  | Retrieves and pretty prints the contents of a Git object based on its hash.                                      |
| `git cat-file -p master^{tree}`                   | Prints out the tree object specified by the tip of the `master` branch.                                         |

## 6. Retrieving Lost Work 

| Name@{qualifier}                                 | Description                                                                                                     |
|---------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|
| `Name@{qualifier}`                               | Accesses specific Git references using this syntax, which can be passed to other commands like checkout, reset, and merge. |
| `git reflog master@{one.week.ago}`               | Accesses the reference log for the `master` branch from one week ago.                                           |
| `git checkout bugfix@{2.days.ago}`               | Checks out the state of the `bugfix` branch from two days ago.                                                  |
| `git diff main@{0} main@{yesterday}`             | Displays the difference between the `main` branch's state at time 0 and its state yesterday.                    |




### Contributing:
If you have suggestions for improving the cheat sheet or want to add new commands, please open an issue or submit a pull request. Your contributions are greatly appreciated!



