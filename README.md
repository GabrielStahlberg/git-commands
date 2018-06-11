# Some importants commands for working with Git

This content is a synthesis of all that I learn about versioning with Git.

## Initial user Git config

```shell
# Define global user name
git config --global user.name "YourUserName"

# Define global user email
git config --global user.email "your@email.com"

# Define Git main editor
# your-favorite-editor = shortcut for your favorite editor (atom in my case)
git config --global core.editor your-favorite-editor

# Show all global configs
git config --list

# Show some specific config
git config user.name
```

## Initialize a Git repository

```shell
# First create a folder for your project
mkdir <project>

# Enter the project folder
cd <project>

# Initialize Git repository
git init

# Show Git hidden folder
ls -la
```
## Git file status lifecycle

![Image of a representation of Git file status lifecycle](https://github.com/EricDosReis/git-commands/blob/master/git-file-status-lifecycle.jpg)

```shell
# Show files status
git status
```

### Untracked status
Files that are not being tracked by Git.

```shell
# Add a file to the staging area
git add <file>

# Add all files to the staging area
git add -A
```

### Unmodified status
Files tracked by Git but not modified.

### Modified status
Files tracked by Git and modified. All modified files must be added to the staging area again:

```shell
git add -A
```

### Staged status
Files prepared to be committed.

```shell
# Commit all staged changes
git commit -m "Write a message describing your changes"

# Add all files to staging area and commit
git commit -am "Write a message describing your changes"
```

After the commit all the committed files return to the unmodified status.

## Viewing logs

```shell
# Show the log
git log

# Show the log with more informations like branchs, merges, tags, etc ...
git log --decorate

# Show all log entries done by an especific author
git log --author="AuthorName"

# Show all authors with the amount of commits and each commit message
git shortlog

# Show only authors and the amount of commits from each
git shortlog -sn

# Show a graph with all repository changes
git log --graph

# Show content of an especified commit
git show <hash>
```

## Viewing differences

```shell
# Show all modifications before commit
git diff

# Show names of modified files before commit
git diff --name-only
```

## Undoing things

```shell
# Return a file to a previous state
git checkout <file>

# Reset files changes
git checkout .

# Checkout in a commit
git checkout <commit-hash>

# Remove untracked files
git clean -f -d

# Untrack a file from staging area
git reset HEAD <file>

# Reset a commit
# Back files to the staged status
git reset --soft <penultimate-commit-hash>

# Back files to the modified status
git reset --mixed <penultimate-commit-hash>

# Kill committed files
git reset --hard <penultimate-commit-hash>
```

## Managing branches

```shell
# Create new local branch
git branch <branch>

# Create new local branch and checkout
git checkout -b <branch>

# Push new local branch to remote
git push -u origin <branch>

# Change current branch
git checkout <branch>

# Remove a local branch
git branch -d <local-branch>

# Remove a remote branch
git push origin --delete <remote-branch>

# Sync local branch list
git fetch -p 

# Merge a branch with the current branch
git merge <branch>
```
