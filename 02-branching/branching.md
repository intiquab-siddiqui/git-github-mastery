
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



Delete a local branch ⭐

After merging a feature branch:

git branch -d feature-branching

This means:

Delete the local branch because its work has already been merged.

There is also:

git branch -D feature-branching

-D force deletes it even if Git thinks it hasn't been merged.

We'll practice this safely.

. Rename a branch ⭐

You mentioned this earlier, and we haven't practiced it yet.

git branch -m old-name new-name

For example:

git branch -m feature-branching feature-login

. See remote branches ⭐

git branch -r

Shows branches that Git knows about on the remote:

origin/master


origin/feature-branching

. See ALL branches ⭐

git branch -a

Shows:

Local branches
+
Remote branches

. Delete a remote branch ⭐

After a feature is merged, you may want to remove the remote feature branch:

git push origin --delete feature-branching

This deletes the branch from GitHub, not your local branch.

10. Compare branches ⭐

Very useful before merging:

git diff master..feature-branching

This lets you inspect differences between the two branches.

11. Check which branch contains a commit

Later, this is useful:

git branch --contains <commit-id>

It tells you which branches contain that commit.

🧠 One important concept: local vs remote branches

This is worth understanding before conflicts:

EC2 LOCAL                         GITHUB

master             ───────────→   origin/master
feature-login      ───────────→   origin/feature-login


