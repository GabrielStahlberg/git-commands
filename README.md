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
mkdir project-name

# Enter the project folder
cd project-name

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
git add file-name

# Add all files to the staging area
git add -A
```

### Unmodified status
Files tracked by Git but not modified.

```shell
# Unstage a file
git rm --cached file-name
```

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

# Show only authors and the amount of commits of each
git shortlog -sn

# Show a graph with all repository changes
git log --graph

# Show all commit content
git show c0mmit-h4sh
```
