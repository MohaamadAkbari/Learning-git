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
        