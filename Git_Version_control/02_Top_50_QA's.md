✅ **Git & Version Control: Top 50 Interview Questions and Answers**

These questions are tailored for beginners to intermediate DevOps or developer roles, with simple yet comprehensive explanations.

---

### 1. **What is Git?**

Git is a distributed version control system that helps track changes in source code during software development. It allows multiple developers to work collaboratively.

---

### 2. **What is version control?**

Version control is a system that records changes to a file or set of files over time so that you can recall specific versions later.

---

### 3. **What is the difference between Git and GitHub?**

* **Git**: Version control tool used locally on your system.
* **GitHub**: Cloud-based hosting service for Git repositories with collaboration features.

---

### 4. **What is a repository in Git?**

A repository (repo) is a storage location for your code and its history. It can be local (on your computer) or remote (like GitHub).

---

### 5. **What are the types of Git repositories?**

* **Local repository**: Exists on your computer.
* **Remote repository**: Stored on services like GitHub, GitLab, or Bitbucket.

---

### 6. **How do you initialize a Git repository?**

```bash
git init
```

This creates a `.git` directory and initializes a new Git repo.

---

### 7. **How do you clone a repository?**

```bash
git clone <repo-url>
```

This downloads the remote repo to your local system.

---

### 8. **What is a commit in Git?**

A commit is a snapshot of your project at a specific point in time. Commits include a message and track what has changed.

---

### 9. **How do you check the status of your Git repo?**

```bash
git status
```

Shows changes to be committed, staged, or unstaged.

---

### 10. **How do you add files to staging?**

```bash
git add <file>
```

Or to add all:

```bash
git add .
```

---

### 11. **How do you commit changes?**

```bash
git commit -m "Your commit message"
```

---

### 12. **How do you view commit history?**

```bash
git log
```

---

### 13. **What is the difference between staging and committing?**

* **Staging**: Prepares files to be committed.
* **Committing**: Saves a snapshot of staged changes.

---

### 14. **How do you push changes to a remote repo?**

```bash
git push origin <branch-name>
```

---

### 15. **How do you pull updates from a remote repo?**

```bash
git pull
```

Fetches and merges changes from the remote repo.

---

### 16. **What is a branch in Git?**

A branch is a parallel version of your code where you can develop features independently.

---

### 17. **How do you create a new branch?**

```bash
git branch <branch-name>
```

---

### 18. **How do you switch branches?**

```bash
git checkout <branch-name>
```

Or:

```bash
git switch <branch-name>
```

---

### 19. **How do you create and switch to a branch?**

```bash
git checkout -b <branch-name>
```

---

### 20. **How do you merge branches?**

Switch to the branch you want to merge into and run:

```bash
git merge <other-branch>
```

---

### 21. **What is a merge conflict?**

A merge conflict happens when two branches change the same part of a file differently. Git cannot automatically resolve it.

---

### 22. **How do you resolve merge conflicts?**

Open the conflicted files, decide what changes to keep, then:

```bash
git add <file>
git commit
```

---

### 23. **How do you delete a branch?**

```bash
git branch -d <branch-name>
```

For force delete:

```bash
git branch -D <branch-name>
```

---

### 24. **What is a remote in Git?**

A remote is a version of your project hosted online (e.g., GitHub).

---

### 25. **How do you list remotes?**

```bash
git remote -v
```

---

### 26. **How do you add a new remote?**

```bash
git remote add origin <url>
```

---

### 27. **How do you remove a remote?**

```bash
git remote remove <name>
```

---

### 28. **What is `git fetch`?**

`git fetch` downloads changes from the remote but doesn’t merge them.

---

### 29. **What is the difference between `git fetch` and `git pull`?**

* `git fetch`: Downloads changes.
* `git pull`: Downloads and merges changes.

---

### 30. **How do you rename a branch?**

```bash
git branch -m old-name new-name
```

---

### 31. **How do you stash changes in Git?**

```bash
git stash
```

Saves uncommitted changes for later use.

---

### 32. **How do you apply a stash?**

```bash
git stash apply
```

---

### 33. **How do you list stashes?**

```bash
git stash list
```

---

### 34. **How do you delete a stash?**

```bash
git stash drop
```

---

### 35. **How do you create a tag in Git?**

```bash
git tag v1.0
```

---

### 36. **How do you push a tag to remote?**

```bash
git push origin v1.0
```

---

### 37. **How do you delete a tag?**

```bash
git tag -d v1.0
```

---

### 38. **How do you revert a commit?**

```bash
git revert <commit-id>
```

---

### 39. **How do you reset to a previous commit?**

```bash
git reset --hard <commit-id>
```

Be careful — this deletes later commits.

---

### 40. **How to ignore files in Git?**

Create a `.gitignore` file and list file patterns to exclude.

---

### 41. **What is HEAD in Git?**

`HEAD` refers to the current commit or branch you’re working on.

---

### 42. **What is `git cherry-pick`?**

It lets you apply a commit from one branch onto another.

```bash
git cherry-pick <commit-id>
```

---

### 43. **What is a fork?**

A fork is a copy of a repository that allows you to freely experiment without affecting the original.

---

### 44. **What is a pull request (PR)?**

A pull request proposes changes from your branch to another branch in a repository (usually remote like GitHub).

---

### 45. **What is Git rebase?**

Rebase moves or combines a sequence of commits to a new base commit.

```bash
git rebase <branch>
```

---

### 46. **What is the difference between rebase and merge?**

* **Merge**: Preserves history.
* **Rebase**: Rewrites history for a linear timeline.

---

### 47. **How do you undo changes in a file?**

```bash
git checkout -- <file>
```

---

### 48. **How do you view the difference between commits or branches?**

```bash
git diff <commit1> <commit2>
```

---

### 49. **What is `.git/config` used for?**

It contains configuration specific to your repo — like remotes and user details.

---

### 50. **How do you check who made what changes?**

```bash
git blame <file>
```

Shows line-by-line history with authors.

---
