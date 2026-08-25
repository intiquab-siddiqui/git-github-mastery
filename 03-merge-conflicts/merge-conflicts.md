# Git Merge Conflicts

A merge conflict happens when Git cannot automatically combine changes from two branches.

## Why Do Merge Conflicts Happen?

A conflict can occur when two branches modify the same part of the same file differently.

Example:

```text
master
   |
   ● Previous commit
   |
   ├── Master changes the same line
   |
   └── conflict-practice changes the same line
             |
             ↓
          git merge
             |
             💥 CONFLICT





Conflict Markers

When a conflict occurs, Git adds markers to the file:

<<<<<<< HEAD
Change from the current branch
=======
Change from the incoming branch
>>>>>>> conflict-practice
Meaning
<<<<<<< HEAD

Marks the beginning of the current branch's version.

=======

Separates the two versions.

>>>>>>> conflict-practice

Marks the end of the incoming branch's version.

How to Resolve a Conflict
1. Check the conflict
git status
2. Open the conflicted file
nano commands.md
3. Choose the correct content

Remove the conflict markers:

<<<<<<<
=======
>>>>>>>

and keep the final content you want.

4. Stage the resolved file
git add commands.md

This tells Git that the conflict has been resolved.

5. Complete the merge
git commit -m "Resolve merge conflict in commands.md"
6. Verify
git status

Expected:

nothing to commit, working tree clean
7. Push the resolved merge
git push
Abort a Merge

If you want to cancel a merge before completing it:

git merge --abort

This returns the repository to the state it was in before the merge started.

Conflict Resolution Workflow


Create conflicting changes
          ↓
     git merge
          ↓
       💥 Conflict
          ↓
     git status
          ↓
    Edit the file
          ↓
    Remove markers
          ↓
       git add
          ↓
     git commit
          ↓
   Conflict resolved
          ↓
       git push


Hands-On Practice

In this lab, a conflict was intentionally created by modifying the same section of commands.md differently on master and conflict-practice.

The conflict was resolved manually, staged with git add, completed with a merge commit, and push to github...
