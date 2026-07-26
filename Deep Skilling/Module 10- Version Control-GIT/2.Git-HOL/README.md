# Hands-on Lab: Using `.gitignore` to Ignore Unwanted Files

## Objective

- Explain Git Ignore.
- Ignore unwanted files and folders using `.gitignore`.
- Verify that ignored files are not tracked by Git.

---

## Step 1: Navigate to the Git Repository

### Command

```bash
cd /c/Users/madhu/Documents/MyRepository
```

### Output

```text
madhu@MADHURIREDDY MINGW64 ~/Documents/MyRepository (master)
$
```

---

## Step 2: Check Git Status

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

## Step 3: Create a `.log` File

### Command

```bash
echo "Git Ignore Demo" > sample.log
```

### Output

```text
(No output)
```

---

## Step 4: Create a `log` Folder

### Command

```bash
mkdir log
echo "Test File" > log/test.txt
```

### Output

```text
(No output)
```

---

## Step 5: Check Git Status

### Command

```bash
git status
```

### Output

```text
On branch master

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        log/
        sample.log

nothing added to commit but untracked files present
```

### Observation

At this stage, Git detects both the `.log` file and the `log` folder.

---

## Step 6: Create `.gitignore`

### Command

```bash
touch .gitignore
```

### Output

```text
(No output)
```

---

## Step 7: Edit `.gitignore`

### Command

Open the file using Notepad:

```bash
notepad .gitignore
```

**OR**

```bash
notepad++.exe .gitignore
```

Add the following content to the `.gitignore` file:

```text
*.log
log/
```

Save and close the file.

---

## Step 8: Verify Ignored Files

### Command

```bash
git status
```

### Output

```text
On branch master

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        .gitignore

nothing added to commit but untracked files present
```

### Observation

- `sample.log` is ignored.
- `log/` folder is ignored.
- Only `.gitignore` is displayed.

---

## Step 9: Add `.gitignore`

### Command

```bash
git add .gitignore
```

### Output

```text
(No output)
```

---

## Step 10: Check Git Status

### Command

```bash
git status
```

### Output

```text
On branch master

Changes to be committed:

        new file:   .gitignore
```

---

## Step 11: Commit Changes

### Command

```bash
git commit -m "Added .gitignore to ignore log files and folders"
```

### Sample Output

```text
[master 4d8f9ab] Added .gitignore to ignore log files and folders
 1 file changed, 2 insertions(+)
 create mode 100644 .gitignore
```

> **Note:** The commit ID (for example, `4d8f9ab`) will be different on your system.

---

## Step 12: Push to the Remote Repository

### If your branch is `master`

#### Command

```bash
git push origin master
```

### If your branch is `main`

#### Command

```bash
git push origin main
```

### Sample Output

```text
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 289 bytes | 289.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)

To https://github.com/username/repository.git
   7a2e8c1..4d8f9ab  master -> master
```

---

## Step 13: Final Verification

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

## `.gitignore` File

```text
*.log
log/
```

## Ignored Files

```text
sample.log
log/
```

## Result

The `sample.log` file and the `log/` directory are not displayed when running the `git status` command. This confirms that Git successfully ignores them according to the rules specified in the `.gitignore` file.
