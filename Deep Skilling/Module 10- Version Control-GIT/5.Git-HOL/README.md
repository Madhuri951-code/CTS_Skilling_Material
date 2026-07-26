# Hands-on Lab: Clean Up and Push Back to Remote Git

## Objective

- Explain how to clean up and push changes back to the remote Git repository.
- Execute the steps involved in cleaning up the local repository and pushing changes to the remote repository.

---

## Prerequisites

- Git installed and configured.
- Hands-on ID: **Git-T03-HOL_002** completed.
- Local Git repository connected to a remote GitHub/GitLab repository.

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

# Step 2: List All Available Branches

### Command

```bash
git branch -a
```

### Sample Output

```text
* master
  remotes/origin/master
```

### Observation

The `*` symbol indicates the currently active branch.

---

# Step 3: Pull the Latest Changes from the Remote Repository

### Command

```bash
git pull origin master
```

### Sample Output

```text
From https://github.com/username/MyRepository
 * branch            master     -> FETCH_HEAD
Already up to date.
```

### Observation

The local repository is synchronized with the remote repository.

---

# Step 4: Push Pending Changes to the Remote Repository

### Command

```bash
git push origin master
```

### Sample Output

```text
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 412 bytes | 412.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)

To https://github.com/username/MyRepository.git
   a1b2c3d..d4e5f6a  master -> master
```

### Observation

The pending commits have been successfully pushed to the remote repository.

---

# Step 5: Verify the Changes in the Remote Repository

### Command

Open your GitHub or GitLab repository in a web browser and verify that the latest commit appears in the commit history.

### Expected Result

```text
Latest Commit:

Resolved merge conflict in hello.xml
Updated .gitignore to ignore backup files
```

---

# Final Verification

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

## Available Branches

```text
* master
  remotes/origin/master
```

## Latest Commit

```text
d4e5f6a Updated .gitignore to ignore backup files
```

## Result

- Verified that the `master` branch was in a clean state.
- Listed all available local and remote branches.
- Pulled the latest changes from the remote repository.
- Successfully pushed the pending commits to the remote repository.
- Verified that the latest changes were reflected in the remote GitHub/GitLab repository.
- Confirmed that the working tree was clean using the `git status` command.
