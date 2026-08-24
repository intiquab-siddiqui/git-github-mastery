
# Git Branching

Branching allows us to create a separate line of development without directly changing the main branch.

## Check branches

```bash
git branch


Shows local branches. * indicates the current branch.

Create and switch to a branch

Older method:

git checkout -b feature-branching

Modern method:

git switch -c feature-branching

Both create the branch and switch to it.

Switch branches

git switch master

Switches to the master branch.

Make changes

Edit a file, then check:

git status

Stage changes

git add .

Moves changes to the staging area.

Commit changes

git commit -m "Update commands.md on feature branch"

Creates a commit on the current branch.

View branch and commit information

git log --oneline --decorate

Shows compact commit history with branch, HEAD, and tag references.

Push a new branch to GitHub

git push -u origin feature-branching

Pushes the local branch to GitHub and establishes upstream tracking.

After that:

git push
Merge a branch

First switch to the branch that should receive the changes:

git switch master

Then merge:

git merge feature-branching

Push the merged changes

git push

Branching Workflow

master
   |
   | create branch
   ↓
feature-branching
   |
   | edit → add → commit
   ↓
push to GitHub
   |
   ↓
switch to master
   |
   ↓
git merge feature-branching
   |
   ↓
git push
   |
   ↓
GitHub master




Important Concept

The branch receiving the merge must be the branch we are currently on.

Example:

git switch master
git merge feature-branching

This means:

"Merge feature-branching into master."
