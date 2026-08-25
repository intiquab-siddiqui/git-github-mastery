# Git Basics

Hands-on Git practice using an AWS EC2 instance.

##git user configuration 

git needs username and email to indentify who creates commits. 

### confihure user name 

bash 
git config --global usr.name "your name"

configure your email
git config --global user.email "your email"

check configuration 

git config --global user.name
git config --gloabl user.email

OR

git config --global --list

## 1. Create a Git Repository

```bash
git init

Initializes the current directory as a Git repository.

2. Check Repository Status
git status

Shows the current branch, modified files, staged files, and untracked files.

3. Stage Changes
git add README.md

Stages a specific file.

git add .

Stages all changes in the current directory.

4. Commit Changes
git commit -m "Initial Git practice"

Creates a snapshot of the staged changes in Git history.

5. View Commit History
git log

Shows detailed commit history.

git log --oneline

Shows a compact commit history.

6. Connect Local Repository to GitHub
git remote add origin <repository-url>

Connects the local repository to a remote repository named origin.

7. Check Remote Repository
git remote -v

Shows the fetch and push URLs of the remote repository.

8. Push Changes to GitHub
git push -u origin master

Pushes the local master branch to GitHub and sets the upstream branch.

After the upstream is configured:

git push

is usually enough.

Git Workflow

Working Directory
       ↓
   git add
       ↓
 Staging Area
       ↓
  git commit
       ↓
 Git Repository
       ↓
   git push
       ↓
    GitHub

Commands Practiced

git init
git status
git add
git commit
git log
git log --oneline
git remote add origin
git remote -v 
git push



##Branching practice

tgis section was created on the feature-branching
 branch.


## Merge Conflict Practice

This line was created on the conflict-practice branch.
