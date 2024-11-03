# Working with Git
## Installation and Configuration

* Use Homebrew to update git on Mac

        $ brew install git

* To find the git version on your system, use:

        $ git --version

* Configure global variables:

        $ git config --global user.name "username"
        $ git config --global user.email email_address
        $ git config --global init.defaultBranch main

* If you want to check your configuration settings:
    
        $ git config --list

### Getting Help

* If you want to get help while using Git:

        $ git help <verb>
        $ git <verb> help

* A more concise help page:
        $ git <verb> -h

## Initializing a Repository

* Go to the directory and command: 

        $ git init

* This creates a new subdirectory named .git. Next, add the files into git:

        $ git add .
        $ git commit -m 'message'

* Similarly to git add . you can write

        $ git add --all
        $ git add -A

* Next, using the following command to see the action done.

        $ git log
        $ git log --oneline

## Git Environment

* **Commit Hash**: Each commit in Git has a unique ID called a commit hash.
* **Branches**: Branches are alternate versions of your project. The current branch is indicated by the head.
* **Git Environments**: Git has three main environments:
    * **Working Environment**: Where files reflect the last commit.
    * **Staging Environment**: A temporary area where files are queued before committing.
    * **Commit** : The final state where changes are recorded with a new commit hash.

* **File States**:
    * **Tracked Files**: Files that existed in the previous commit.
    * **Untracked Files**: New files added since the last commit.
    * **Modified Files**: Tracked files that have been changed.
    * **Staged Files**: Files moved to the staging environment.

* **Git Status Command**: Used to check the current state of files and branches.

        $ git status
    
    short status

        $ git status -s 

* **Restore Command**: Used to discard changes or move files out of staging.

    If a file is staged, command the following to make it back to modified but unstaged

        $ git restore --staged file

    If a file is modified, command the following to make it back to unmodified

        $ git restore .
    This command do nothing with untracked files.
