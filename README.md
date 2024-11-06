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

## Ignoring Files
* **Purpose of Ignoring Files**: Prevents tracking of sensitive information like passwords, API keys, and local settings.
* **.gitignore File**: Created at the root level of the project to specify files or patterns to ignore.
* **Common Ignored Files**:

        .DS_Store for macOS
        .vscode/ folder for Visual Studio Code settings
        node_modules for NPM projects
        Custom files like authentication.js for tokens and keys
        notes/
        **/*-todo.md

* **Git Behavior**: Ignored files are not uploaded to GitHub and are grayed out in Git status.
* **Global Ignore File**: Can be set up for multiple projects using a config variable.

        $ git config --global core.excludesfile [file]
* **Clearing Cache**: Use the following command to clear cached files if .gitignore is updated after commits.

        $ git rm -r --cached . 
        $ git add .
        $ git commit -m 'clear cache'

## Difference between Commits:

* **Using git diff**: The following command shows the differences between files, highlighting changes such as deletions and additions.

        $ git diff

    If you want to compare staged changes to your last commit:
        $ git diff --staged

* **Handling large changes**: For extensive changes, using Visual Studio Code's source control editor can make it easier to view and manage differences.

* **Comparing commits**: You can compare a file to its state at any previous commit using git diff and the commit hash.

* **Git Lens extension**: For frequent comparisons between branches and checkpoints, the Git Lens extension in Visual Studio Code is recommended.

## Deleting and Renaming Files

#### Deleting a file

* **Direct Deletion**: You can delete a file directly from the file system or using Visual Studio Code. Git will track this deletion and you need to stage and commit it.

* **Git RM Command**: Using the following command, the file is deleted and the deletion is automatically staged.

        $ git rm <file>, 

#### Restoring Files:
* **Git Restore Command**: Use the following command to bring back a deleted file. For staged deletions, use git restore --staged <file>.

        $ git restore <file> 

#### Renaming Files:

* **Direct Renaming**: Renaming a file directly in the file system is tracked by Git as a deletion of the old file and addition of the new file.
Git MV Command: Use the following command to rename a file, which stages the change automatically.

        $ git mv <old_name> <new_name> 

## Changing History

* **Amending Commits**: You can amend the last commit to include additional changes without creating a new commit, keeping your commit history clean.
* To add changes to the last commit, command with new messages or no new messages,

        $ git commit --amend
        $ git commit --amend -m 'New commit message'
        $ git commit --amend --no-edit


* **Resetting**: The git reset command allows you to move back to a previous commit, either keeping changes (--soft) or discarding them (--hard).

        $ git restore <commit>
        $ git restore --hard <commit>

* **Rebasing**: Rebasing lets you take commits from one branch and apply them to another, effectively rewriting the commit history to make it cleaner or to reorder commits.

        $ git rebase <branch>/<commit>
        $ git rebase --interactive <branch>/<commit>
        $ git rebase - i HEAD-#
        $ git rebase -i --root

## Branches

* **Creating Branches**: Branches allow you to create different versions of your code to experiment with new features without affecting the stable version. 
* To see current branches, command

        $ git branch

* To copy a new brach command git switch -c or the older git checkout -b to create a new branch.

        $ git switch -c NAME
        $ git checkout -b NAME

* **Managing Branches**: You can switch between branches using git switch and view all branches with git branch. After making changes in a branch, use git add and git commit to save those changes.

* **Merging Branches**: To merge changes from one branch into another, switch to the target branch and use git merge. 

        $ git merge <branch>

* **Deleting Branches**: After merging, it's a good practice to delete the feature branch using git branch -d.

        $ git branch --delete NAME
        $ git branch -d NAME
        $ git branch -D 

### Git FLow
* Developers do the following flow on real projects:
    * Feature/fix branch
    * Make changes
    * Merge to master
    * Delete old branch

## Merging Conflicts

* **Understanding Merge Conflicts**: Merge conflicts occur when changes are made to the same part of a file in different branches. This typically happens when multiple people are working on the same project.

* **Resolving Conflicts** : The video demonstrates how to resolve merge conflicts using Visual Studio Code, which provides helpful indicators to choose between conflicting changes.

* **Best Practices**: It’s important to decide which changes to keep and manually adjust the code to resolve conflicts, ensuring that the final version is correct and consistent.

## Stashing and Cleaning

* **Git Stash**: Temporarily stores changes so you can work on something else without losing your current progress. Commands include git stash, git stash list, git stash apply, and git stash pop.

* To store changes, use the command

        $ git stash

* To see the stored changes, use the command

        $ git stash list

* The following command allows you to apply a stash set of changes.

        $ git stash apply <index>

* The following command remove the git stash from the list

        $ git stash pop

* **Git Clean**: Removes untracked files and directories from your working directory. Use git clean -n to preview what will be removed and git clean -df to execute the clean.

        $ git clean -n
        $ git clean -d
        $ git clean -f

# GitHub

* GitHub as a Collaborative Platform: GitHub is an online service that allows developers to work together, often referred to as a social coding website.

* Core Functions: It provides tools for tracking changes, assigning issues, and deploying code. It also includes project management tools like Kanban boards.

* Setting Up and Using GitHub: Key actions include setting up a remote repository, pushing local changes to GitHub, and fetching and pulling changes from the remote repository.

## Pushing to GitHub

* Setting Up Remotes: Use git remote add <name> <URL> to connect your local project to a remote repository. Commonly, the remote name is "origin".

        $ git remote add <name> <URL>


* Pushing Changes: Use git push to move files from your local machine to GitHub. The first push requires the -u option to set the upstream branch.

        $ git push -u origin main
        $ git push --all
        $ git branch --set-upstream-to <origin/remote-branch>

* Managing Remotes: You can list, remove, and rename remotes using commands like git remote -v, git remote remove <name>, and git remote rename <old-name> <new-name>.

## Github Options

* **Branch Management**: You can manage branches directly in GitHub, including creating, editing, and deleting branches.

* **File Management**: GitHub allows you to edit files, add new files, and organize them into directories.

* **Tags and Topics**: You can add tags to your projects to make them easier to find and add topics to help others discover your work.

* **Issues and Pull Requests**: Use issues to track tasks and pull requests to approve changes made by others.

* **GitHub Pages**: Host your website for free using GitHub Pages, which allows you to serve static sites directly from a GitHub repository.

## Github Workflow

* **Branch-Based Workflow**: GitHub Flow is a branch-based workflow where the main branch contains the current version of the code. Changes are made in feature branches, which are copies of the main branch.

* **Feature Branches**: To modify the code, you create a feature branch. This allows you to work on new features or changes without affecting the main branch.

* **Commits and Pushes**: Changes are made in the feature branch, committed, and then pushed back to the feature branch. Each commit should be an isolated and complete change.

## Pull Requests

* **Pull Requests**: When ready, you create a pull request to merge changes from the feature branch back into the main branch. This allows for feedback and code review from others.

* **Code Review and Feedback**: Reviewers can leave comments, feedback, and suggestions on the pull request. This collaborative process helps ensure code quality.

* **Merging Changes**: Once the pull request is approved, the changes are merged into the main branch. This process may involve reviewing differences between the feature branch and the main branch.

* **Deleting Feature Branches**
: After merging, the feature branch can be deleted to indicate the process is complete.

## Pull Requests Features

* **Creating a Pull Request**: You can initiate a pull request directly on GitHub by editing a file, previewing changes, and proposing the changes to create a new branch.

* **Managing Pull Requests**: Pull requests allow you to have conversations, add comments, and assign reviewers to discuss and approve changes before merging them into the main branch.

* **Project Management Features**: GitHub provides tools like labels, milestones, and issue linking to manage and track pull requests effectively.

* **Comparing Branches**: You can compare different branches to see changes before and after a pull request, allowing flexibility in viewing various branches.

* **Draft Pull Requests**: These serve as placeholders for work-in-progress, enabling discussions and comments before the final review.

* **Review Process**: Pull requests facilitate conversations, comments, and reviews, with options to assign reviewers and use tools like GitGuardian for security checks.

* **Resolving Comments**: You can address comments made during the review by editing the code and marking the conversation as resolved.

* **Pushing Updates**: After making changes, commit and sync your updates to the repository to reflect the resolved issues.

* **Merging Pull Requests**: Once all comments are addressed and changes are committed, you can merge the pull request to finalize the review process.

## CodeOwners

* **Creating a CODEOWNERS File**: You can create a CODEOWNERS file in your repository to assign ownership of files and directories to specific users.

* **Branch Protection**: You can set branch protection rules to require pull requests and approvals before merging changes, enhancing security and control.

* **Automatic Notifications**: The assigned owners will automatically receive notifications for any changes, ensuring they are involved in the review process.

## Organizing Projects

* **Collaborators**: You can invite others to work on your project, enhancing collaboration.

* **Issues**: Create and manage issues to track tasks and bugs, using labels and milestones for better organization.

* **Projects**: Use GitHub projects to visualize and manage the progress of your work, with options like Kanban boards for effective project management.

## Repository Insights

* **Insights Tab**: Provides detailed information about the repository, including activity, contributors, and community standards.

* **Graphs and Metrics**: Displays various metrics such as merge pull requests, additions and deletions, and traffic sources.

* **Community Standards**: Shows how the repository compares to GitHub's recommended community standards and allows you to create necessary files.

* **Dependency Management**: Features like Dependabot help track and update project dependencies.

* **Forks and Stars**: Information on forks, stars, and watchers, indicating the repository's popularity and engagement.

## GitHub Shortcuts

* **Question Mark (?)**: Displays a list of most shortcuts, which are context-sensitive.

* **Slash (/)**: Used for searching within repositories, also context-sensitive.

* **Command Palette**: Accessed with Command + K on Mac or Control + K on Windows, providing a powerful search and navigation tool.

* **Period (.)**: Opens the repository in a lightweight editor at github.dev.

* **Feature Preview**: Allows you to enable and test upcoming GitHub features.

## Synching GitHub and local repository

* **git clone**: Copies a GitHub repository to your local hard drive.

        $ git clone <URL>

* **git fetch**: Downloads information from the remote repository to your local repo without merging it.

        $ git fetch

* **git pull**: Combines fetching and merging data from the remote repository to your local version.

        $ git pull

* **Branch Management**: Commands like git branch -a and using Visual Studio Code to manage and switch between branches.

* **Releases**: Creating official versions of your project using GitHub releases for specific versions of your code.