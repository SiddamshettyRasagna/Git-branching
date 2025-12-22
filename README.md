# Git-branching

This documentation contains the concepts of Learn Git Branching.

# Learn Git Branching

Learn Git Branching is an interactive, browser-based learning platform that helps users understand how Git works internally through real-time visual diagrams, covering concepts such as commits, branches, HEAD, merging, and rebasing.
# Level-1
# 1.Introduction to Git Commits

### **What is Git Commit?**

A **Git commit** is a record that saves the current state of a project in a Git repository. It stores the changes made to files along with a message describing those changes, allowing Git to track the project’s history over time.


<img width="1920" height="910" alt="image" src="https://github.com/user-attachments/assets/2d683427-b061-44ce-9326-3aacdcd92029" />

# Commands Executed
```bash
git commit
```
```
git commit
```
This screenshot shows how commits are created in Git.

Each circle (C0, C1, C2, C3) represents a commit made one after another.

The (main*) label shows the current branch, and it points to the latest commit (C3).

Every time git commit is used, a new commit is added and the main branch moves forward.

This helps us understand how Git keeps track of changes.

# 2.Introduction to Git Branching

### **What is Git Branch?**

A branch in Git is like a separate workspace for your code. It allows you to work on new features or fixes without affecting the main code

### **What is Git Chechout?**

The git checkout command is used to switch between these branches, so your files and code update to match the branch you select.

<img width="1920" height="922" alt="Screenshot (108)" src="https://github.com/user-attachments/assets/04c430a4-adbb-4286-b449-1764e8f36bab" />

# Commands Executed
```bash
git branch bugfix
```
```
git checkout bugfix
```

This screenshot shows how to create and switch to a new branch in Git using Learn Git Branching.

The commits C0 and C1 are displayed, with C1 being the latest commit.

A new branch named bugfix has been created from commit C1 using git branch bugfix, and it has been checked out using git checkout bugfix.

The * symbol next to bugfix indicates that HEAD is currently on this branch.

The main branch still points to commit C1, but the active branch is now bugfix.

# 3.Introduction to Git Merging

### **What is Git Merging?**

Git merging is the act of combining changes from one branch into another branch so that both branches work exists together in a single branch.

<img width="1920" height="923" alt="Screenshot (106)" src="https://github.com/user-attachments/assets/b54d20c5-d13d-4e77-bd1f-698053f75965" />

# Commands Executed
```bash
git branch bugfix
```
```
git checkout bugfix
```
```
git commit
```
```
git checkout main
```
```
git commit
```
```
git merge bugfix
```

This screenshot illustrates the Merging in Git level from Learn Git Branching, showing how Git manages multiple branches and combines them. 

The circles labeled C0, C1, C2, C3, and C4 represent individual commits, with the history first moving linearly from C0 to C1 and then splitting into two paths. 

From commit C1, a new branch named bugfix is created and points to commit C2, while the main branch continues independently with commits C3 and C4. 

The label main* indicates that the main branch is currently checked out, with the * symbol showing that HEAD is pointing to main at commit C4. 

The curved lines in the diagram visually represent the divergence of the two branches and their integration through a merge.

# 4.Introduction to Rebase

### **What is Git Rebase**

Git rebase is the process of moving or replaying commits from one branch onto another branch, changing the base commit so the history becomes linear.

<img width="1920" height="921" alt="Screenshot (109)" src="https://github.com/user-attachments/assets/aede8db6-62ef-4e5b-9442-41b846379451" />

# Commands Executed
```bash
git branch bugfix
```
```
git checkout bugfix
```
```
git commit
```
```
git checkout main
```
```
git commit
```
```
git checkout bugfix
```
```
git rebase main
```

This screenshot shows how rebasing works in Git using two branches.

The circles (C0, C1, C2, C3) represent commits created at different times on different branches.

The main branch has its own commits, and the bugFix* label shows the branch where the bug fix work is done.

First, commits are made separately on the main and bugFix branches.

When the command git rebase main is used on the bugFix branch, Git takes the bug fix commit and places it on top of the latest commit of the main branch.

After rebasing, both branches contain the same changes, and the commit history becomes clean and straight.

This helps us understand how Git can organize commits neatly while keeping all changes.

The commit history begins linearly from C0 to C1, after which it splits into two branches. 

The main branch points to commit C3, while the bugfix* branch is currently checked out and points to C2, as indicated by the * symbol showing that HEAD is on the bugfix branch. 

The diagram shows that the bugfix commit has been moved and reapplied on top of the latest commit of the main branch, resulting in a straight, linear history. 

The renaming of the commit to C2′ visually represents that the commit was recreated during the rebase process.



# Level-2

# 1.Detach yo' HEAD

**Detach yo’ HEAD** means that you are no longer working on a branch.

Normally, **HEAD** points to a branch like **main** or **bugFix**.
In a detached HEAD state, **HEAD points directly to a commit** instead of a branch.

This usually happens when you checkout a specific commit.

In this state, you can look at old code or test something, but any new commit you make will not belong to a branch.

If you switch to another branch, those commits can be lost unless you create a new branch.

This helps us understand why staying on a branch is important when making changes.

<img width="1918" height="913" alt="Screenshot 2025-12-22 222846" src="https://github.com/user-attachments/assets/6b07bb5d-8645-4e3f-9a43-f2981d5619a9" />

# Command Executed

```bash
git checkout C4
```

This screenshot shows what happens when HEAD is detached in Git.

The commits (C0, C1, C2, C3, C4) show the history of the project.

At first, HEAD is normally connected to a branch like main or bugFix.

When the command
git checkout C4
is used, Git moves HEAD directly to commit C4.

Now, HEAD is not pointing to any branch, it is pointing only to that commit.

The branches (main and bugFix) stay where they were and do not move.

This state is called detached HEAD.

It helps us understand how Git can look at any old commit without changing branch history.

# 2.Relative Refs (^) 

Remembering full commit hashes in Git is hard and annoying because they are very long.

In real projects, you don’t see a picture of commits, so you use git log to find commit hashes.

The good thing is, Git does not need the full hash.
You can type only the first few characters, as long as they are unique.

Still, using hashes is not very convenient.
That’s why Git provides relative references.

Relative references let you move around commits starting from something easy to remember, like HEAD or a branch name.

There are two simple relative references:

^ → moves one commit back

~<number> → moves multiple commits back

This makes it much easier to move through commit history without typing long hashes.

<img width="1913" height="901" alt="Screenshot 2025-12-22 224122" src="https://github.com/user-attachments/assets/146ccdcc-2fc6-4a19-980c-bd397c1069f9" />

# Commands Executed

```bash
git checkout bugFix
```
```
git checkout C3
```
In these screenshot  
Git checkout bugFix moves you to the bugFix branch.

Git checkout C3 moves HEAD to commit C3, not to a branch, so this is called detached HEAD.

The ^ symbol means go to the previous commit.
