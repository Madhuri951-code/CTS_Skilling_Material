Hands-on Lab: Using .gitignore to Ignore Unwanted Files
Objective
Explain Git Ignore.
Ignore unwanted files and folders using .gitignore.
Verify that ignored files are not tracked by Git.
Prerequisites
Git installed on the system.
Git configured with username and email.
A local Git repository.
A remote repository (GitHub/GitLab).
Step 1: Navigate to the Git Repository
Command
cd /c/Users/madhu/Documents/MyRepository
Output
madhu@MADHURIREDDY MINGW64 ~/Documents/MyRepository (master)
$
Step 2: Check Git Status
Command
git status
Output
On branch master

nothing to commit, working tree clean
Step 3: Create a .log File
Command
echo "Git Ignore Demo" > sample.log
Output
(No output)
Step 4: Create a Log Folder
Command
mkdir log
echo "Test File" > log/test.txt
Output
(No output)
Step 5: Check Git Status
Command
git status
Output
On branch master

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        log/
        sample.log

nothing added to commit but untracked files present

At this stage, Git detects both the .log file and the log folder.

Step 6: Create .gitignore
Command
touch .gitignore
Output
(No output)
Step 7: Edit .gitignore

Open the file.

notepad .gitignore

or

notepad++.exe .gitignore

Add the following content:

*.log
log/

Save and close the file.

Step 8: Verify Ignored Files
Command
git status
Output
On branch master

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        .gitignore

nothing added to commit but untracked files present

Notice that:

sample.log is ignored.
log/ folder is ignored.
Only .gitignore is shown.
Step 9: Add .gitignore
Command
git add .gitignore
Output
(No output)
Step 10: Check Status
Command
git status
Output
On branch master

Changes to be committed:

        new file:   .gitignore
Step 11: Commit Changes
Command
git commit -m "Added .gitignore to ignore log files and folders"
Sample Output
[master 4d8f9ab] Added .gitignore to ignore log files and folders
 1 file changed, 2 insertions(+)
 create mode 100644 .gitignore

(The commit ID such as 4d8f9ab will be different on your system.)

Step 12: Push to Remote Repository

If your branch is master

Command
git push origin master

If your branch is main

git push origin main
Sample Output
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 289 bytes | 289.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)

To https://github.com/username/repository.git
   7a2e8c1..4d8f9ab  master -> master
Step 13: Final Verification
Command
git status
Output
On branch master

nothing to commit, working tree clean
Verification
.gitignore File
*.log
log/
Ignored Files
sample.log
log/

These files are not displayed by git status, confirming that Git successfully ignores them.
