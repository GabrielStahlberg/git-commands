# Essential git commands every developer should know.

## Config

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

## Repository

```shell
# Initialize a local repository
git init

# Clone remote repository
git clone repository-url

# Set remote repository 
git remote set-url origin repository-url

# Show remote repository url
git remote -v
```
## File status lifecycle

![Image of a representation of Git file status lifecycle](https://github.com/EricDosReis/git-commands/blob/master/git-file-status-lifecycle.jpg)

```shell
# Show files status
git status

# Add files to staging
git add file-path

# Add all files
git add -A

# Commit all files
git commit -m "Write a message describing your changes"

# Add all files to staging and commit
git commit -am "Write a message describing your changes"
```

## Viewing logs

```shell
# Show log
git log

# Show log with more info like branchs, merges, tags, etc ...
git log --decorate

# Show all log entries done by an especific author
git log --author="AuthorName"

# Show all authors with the quantity of commits and each commit message
git shortlog

# Show only authors and the quantity of commits
git shortlog -sn

# Show graph with all repository changes
git log --graph

# Show content of a commit
git show <hash>
```

## Viewing diffs

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
git branch branch-name

# Create new local branch and checkout
git checkout -b branch-name

# Push new local branch to remote
git push -u origin branch-name

# Push all new local branches to remote
git push --all origin

# Change current branch
git checkout branch-name

# Remove a local branch
git branch -d local-branch

# Remove a remote branch
git push origin --delete remote-branch

# List remote branches
git branch -r

# Merge a branch with the current branch
git merge branch-name
```
