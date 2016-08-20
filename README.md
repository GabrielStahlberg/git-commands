# Some importants commands for working with Git

This content is a synthesis of all that I learn about versioning and Git.

## Initial user Git config

```
# Define global user name
git config --global user.name "Your Name"

# Define global user email
git config --global user.email "your@email.com"

# Define Git main editor
# your-favorite-editor = shortcut for your favorite editor (atom in my case)
git config --global core.editor your-favorite-editor

# See all global configs
git config --list

# See some specific config
git config user.name
```

## Initializing a Git repository

```
# First create a folder for your project
mkdir project-name

# Enter the project folder
cd project-name

# Initialize Git repository
git init

# See Git hidden folder
ls -la
```
