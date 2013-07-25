# References:
Bash cheat sheet: http://www.tuxfiles.org/linuxhelp/linuxcommands.html
- It says Linux, but the commands are all Bash commands.
Git book: http://git-scm.com/book
Git for Windows: http://git-scm.com/downloads

note: “$” precedes commands for git bash

# Set up Git:
$ git config --global user.name “Chris Williams”
$ git config --global user.email “christopher.williams@kaplan.com”

GitHub tracks links your commits to your account by email address, so use the same one as your GitHub account.

Change the text editor if you don't want to use Vim!
$ git config --global core.editor "'C:\Program Files\Sublime Text 2\sublime_text.exe' -w"
note: The -w flag is necessary for Sublime to work correctly with git.

# Setting up a repo:
Step 1:
Add a .gitignore file to the project.
- This will tell git which files to not include in version control. Add it first so git won’t include unneeded files or sensitive data.
- GitHub has a few .gitignore files here: https://github.com/github/gitignore

Step 2:
- cd to project folder then do:
$ git init
- this sets up git in the current folder
$ git add .
- this adds all the files in the current folder to the list of files to be commited
$ git commit -m “initial commit”

Step 3: Put the code on GitHub.
$ git remote add origin <repo url>
$ git push origin master

# Cloning an existing repository to your machine:
$ git clone <repo url>

# Useful commands
$ git help
$ git status
$ git diff
$ git diff --cached
$ git log
$ git log -p
$ git log --stat

# Working with Git:
Pull changes from GitHub
$ git pull origin <branch name>
Make your changes
$ git add .
- or $ git add <filename> // for a specific file
$ git commit -m “changed some things”
when done do:
$ git push origin <branch name> // origin is the location to push to

# changing the most recent commit
$ git commit --amend

# renaming/moving or deleting files
$ git mv <oldlocation/oldname.txt> <newlocation/newname.txt>
$ git rm <filename>

# Branching
$ git branch
- lists all branches
$ git branch <new branch name>
- creates a new branch
$ git checkout <branch name>
- switch to branch

# Merging
Make sure you're on the branch that you want to merge INTO
$ git merge <branch to merge from>
- But if there's a conflict we have to use a resolve it!
- This can be done manually with a text editor
- or with a merge tool
- or abort the merge with $ git merge --abort
