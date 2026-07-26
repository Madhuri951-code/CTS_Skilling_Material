# Hands-on Lab: Resolving Merge Conflicts in Git

## Objective

- Explain how to resolve conflicts during a merge.
- Implement conflict resolution when multiple users update the master branch, resulting in merge conflicts.

---

## Prerequisites

- Git installed and configured.
- Hands-on ID: **Git-T03-HOL_001** completed.
- Local Git repository.
- P4Merge tool configured with Git.

---

# Step 1: Verify the Master Branch is in a Clean State

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

# Step 2: Create a New Branch

### Command

```bash
git checkout -b GitWork
```

### Output

```text
Switched to a new branch 'GitWork'
```

---

# Step 3: Create `hello.xml`

### Command

```bash
echo "<message>Hello from GitWork Branch</message>" > hello.xml
```

### Output

```text
(No output)
```

---

# Step 4: Check Git Status

### Command

```bash
git status
```

### Output

```text
On branch GitWork

Untracked files:

        hello.xml

nothing added to commit but untracked files present
```

---

# Step 5: Add and Commit the File

### Command

```bash
git add hello.xml
git commit -m "Added hello.xml in GitWork branch"
```

### Sample Output

```text
[GitWork a2b7c31] Added hello.xml in GitWork branch
 1 file changed, 1 insertion(+)
 create mode 100644 hello.xml
```

---

# Step 6: Switch to the Master Branch

### Command

```bash
git checkout master
```

### Output

```text
Switched to branch 'master'
```

---

# Step 7: Create the Same File with Different Content

### Command

```bash
echo "<message>Hello from Master Branch</message>" > hello.xml
```

### Output

```text
(No output)
```

---

# Step 8: Commit the Changes

### Command

```bash
git add hello.xml
git commit -m "Added hello.xml in master"
```

### Sample Output

```text
[master b5d8e91] Added hello.xml in master
 1 file changed, 1 insertion(+)
 create mode 100644 hello.xml
```

---

# Step 9: View Commit History

### Command

```bash
git log --oneline --graph --decorate --all
```

### Sample Output

```text
* b5d8e91 (HEAD -> master) Added hello.xml in master
| * a2b7c31 (GitWork) Added hello.xml in GitWork branch
|/
* 7a2d3c4 Initial commit
```

---

# Step 10: View Differences Using Git Diff

### Command

```bash
git diff master GitWork
```

### Sample Output

```text
diff --git a/hello.xml b/hello.xml
index 4d3a7a2..5f8b9c1 100644
--- a/hello.xml
+++ b/hello.xml
@@ -1 +1 @@
-<message>Hello from Master Branch</message>
+<message>Hello from GitWork Branch</message>
```

---

# Step 11: View Differences Using P4Merge

### Command

```bash
git difftool master GitWork
```

### Output

```text
Launching P4Merge...
```

---

# Step 12: Merge the Branch

### Command

```bash
git merge GitWork
```

### Sample Output

```text
Auto-merging hello.xml
CONFLICT (add/add): Merge conflict in hello.xml
Automatic merge failed; fix conflicts and then commit the result.
```

---

# Step 13: Observe the Conflict Markup

### Command

```bash
cat hello.xml
```

### Output

```text
<<<<<<< HEAD
<message>Hello from Master Branch</message>
=======
<message>Hello from GitWork Branch</message>
>>>>>>> GitWork
```

---

# Step 14: Resolve the Conflict Using P4Merge

### Command

```bash
git mergetool
```

### Output

```text
Launching P4Merge...
```

Resolve the conflict and save the file.

---

# Step 15: Commit the Resolved File

### Command

```bash
git add hello.xml
git commit -m "Resolved merge conflict in hello.xml"
```

### Sample Output

```text
[master d3e9f21] Resolved merge conflict in hello.xml
```

---

# Step 16: Check Git Status

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

# Step 17: Ignore Backup Files

### Command

```bash
echo "*.bak" >> .gitignore
git add .gitignore
git commit -m "Updated .gitignore to ignore backup files"
```

### Sample Output

```text
[master e4f7d18] Updated .gitignore to ignore backup files
 1 file changed, 1 insertion(+)
```

---

# Step 18: List All Branches

### Command

```bash
git branch
```

### Output

```text
GitWork
* master
```

---

# Step 19: Delete the Merged Branch

### Command

```bash
git branch -d GitWork
```

### Output

```text
Deleted branch GitWork (was a2b7c31).
```

---

# Step 20: View Commit History

### Command

```bash
git log --oneline --graph --decorate
```

### Sample Output

```text
* e4f7d18 (HEAD -> master) Updated .gitignore to ignore backup files
* d3e9f21 Resolved merge conflict in hello.xml
* b5d8e91 Added hello.xml in master
* 7a2d3c4 Initial commit
```

---

# Verification

## Conflict Markup

```text
<<<<<<< HEAD
<message>Hello from Master Branch</message>
=======
<message>Hello from GitWork Branch</message>
>>>>>>> GitWork
```

## `.gitignore`

```text
*.bak
```

## Result

- Successfully created the `GitWork` branch.
- Created conflicting changes in both `master` and `GitWork`.
- Detected the merge conflict.
- Resolved the conflict using the P4Merge three-way merge tool.
- Committed the resolved changes.
- Updated `.gitignore` to ignore backup files.
- Deleted the merged branch.
- Verified the commit history and confirmed the working tree was clean.
