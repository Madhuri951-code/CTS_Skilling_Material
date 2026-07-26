# Hands-on Lab: Branching and Merging in Git

## Objective

- Explain branching and merging in Git.
- Explain how to create a branch request in GitLab.
- Explain how to create a merge request in GitLab.
- Create a branch, make changes, and merge it with the master branch.

---

## Prerequisites

- Git installed and configured.
- P4Merge tool installed and configured with Git.
- Local Git repository.
- Remote GitHub/GitLab repository.

---

# Branching

## Step 1: Create a New Branch

### Command

```bash
git branch GitNewBranch
```

### Output

```text
(No output)
```

---

## Step 2: List All Local and Remote Branches

### Command

```bash
git branch -a
```

### Output

```text
* master
  GitNewBranch
  remotes/origin/master
```

### Observation

The `*` symbol indicates the currently active branch.

---

## Step 3: Switch to the New Branch

### Command

```bash
git checkout GitNewBranch
```

### Output

```text
Switched to branch 'GitNewBranch'
```

---

## Step 4: Create a New File

### Command

```bash
echo "This is my new branch." > branch.txt
```

### Output

```text
(No output)
```

---

## Step 5: Add the File

### Command

```bash
git add branch.txt
```

### Output

```text
(No output)
```

---

## Step 6: Commit the Changes

### Command

```bash
git commit -m "Added branch.txt in GitNewBranch"
```

### Sample Output

```text
[GitNewBranch 5b7f2a1] Added branch.txt in GitNewBranch
 1 file changed, 1 insertion(+)
 create mode 100644 branch.txt
```

> **Note:** The commit ID will be different on your system.

---

## Step 7: Check Git Status

### Command

```bash
git status
```

### Output

```text
On branch GitNewBranch

nothing to commit, working tree clean
```

---

# Merging

## Step 8: Switch Back to the Master Branch

### Command

```bash
git checkout master
```

### Output

```text
Switched to branch 'master'
```

---

## Step 9: View Differences Between Master and Branch

### Command

```bash
git diff master GitNewBranch
```

### Sample Output

```text
diff --git a/branch.txt b/branch.txt
new file mode 100644
index 0000000..8f3d6c1
--- /dev/null
+++ b/branch.txt
@@ -0,0 +1 @@
+This is my new branch.
```

### Observation

The output shows the differences between the `master` branch and the `GitNewBranch` branch.

---

## Step 10: View Visual Differences Using P4Merge

### Command

```bash
git difftool master GitNewBranch
```

### Output

```text
Launching P4Merge...
```

### Observation

P4Merge opens and visually displays the differences between the two branches.

---

## Step 11: Merge the Branch into Master

### Command

```bash
git merge GitNewBranch
```

### Sample Output

```text
Updating a4d9e82..5b7f2a1
Fast-forward
 branch.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 branch.txt
```

---

## Step 12: View Commit History

### Command

```bash
git log --oneline --graph --decorate
```

### Sample Output

```text
* 5b7f2a1 (HEAD -> master, GitNewBranch) Added branch.txt in GitNewBranch
* a4d9e82 Added .gitignore
* c6a72e1 Initial commit
```

### Observation

The commit history is displayed in a graphical format showing the merged branch.

---

## Step 13: Delete the Branch

### Command

```bash
git branch -d GitNewBranch
```

### Output

```text
Deleted branch GitNewBranch (was 5b7f2a1).
```

---

## Step 14: Verify Branch Deletion

### Command

```bash
git branch
```

### Output

```text
* master
```

---

## Step 15: Check Git Status

### Command

```bash
git status
```

### Output

```text
On branch master

nothing to commit, working tree clean
```

---

# Verification

## Branches Before Merge

```text
* master
  GitNewBranch
```

## Branches After Merge

```text
* master
```

## Commit History

```text
* 5b7f2a1 (HEAD -> master) Added branch.txt in GitNewBranch
* a4d9e82 Added .gitignore
* c6a72e1 Initial commit
```

## Result

- Successfully created a new branch named `GitNewBranch`.
- Added a new file and committed the changes.
- Compared the differences between the `master` branch and `GitNewBranch`.
- Viewed the visual differences using P4Merge.
- Successfully merged `GitNewBranch` into the `master` branch.
- Verified the commit history after merging.
- Deleted the merged branch.
- Confirmed that the working directory is clean using the `git status` command.
